# USE CASE: COMPILE-TIME KNOWLEDGE GRAPH CONSTRUCTION BY QUICUE

## Context

The [apercue.ca](https://github.com/quicue/apercue) project uses
[CUE](https://cuelang.org) — a constraint language with lattice-based type
semantics — to construct, validate, and serialize knowledge graphs entirely at
compile time. Graph building, SHACL validation, and JSON-LD output happen in a
single `cue export` invocation with no mapping language, no runtime pipeline,
and no triplestore.

Traditional KG construction requires a multi-stage pipeline:

```
Source Data → Mapping (R2RML/RML) → RDF Store → SHACL Validation → Serialization
```

CUE collapses this to:

```
Source Data (CUE structs) → cue export -e <projection>
```

The "mapping" is CUE type unification. The "validation" is CUE constraint
resolution. The "serialization" is JSON-LD context injection. All three happen
during evaluation — there is no separate step for any of them.

Each resource declares `@type` (a struct-as-set of semantic categories) and
`depends_on` (typed dependency edges). A `#Graph` pattern computes topology,
depth, roots, leaves, ancestors, dependents, and impact sets from these
declarations alone:

```cue
"analysis-code": {
    name:       "analysis-code"
    "@type":    {Process: true}
    depends_on: {"sensor-dataset": true}
}
```

The same typed graph simultaneously produces output in 14 W3C specifications
(SHACL, PROV-O, OWL-Time, DCAT, ODRL, EARL, SKOS, Dublin Core, JSON-LD,
schema.org, org, Verifiable Credentials, Activity Streams, and apercue's own
vocabulary).

## Challenges

1. **Declarative mapping without a mapping language.** R2RML and RML define
   explicit source-to-target mappings. CUE replaces this with type unification:
   a resource that satisfies `#Graph.resources[string]` IS a graph node. The
   mapping is the type constraint itself. This raises questions about how
   declarative KG construction should be characterized when there is no
   separate mapping artifact.

2. **Validation as a construction-time guarantee, not a post-hoc check.**
   SHACL validation typically runs after KG construction. In CUE, constraints
   are part of the type lattice — an invalid graph cannot be constructed
   (unification produces bottom `_|_`). The `sh:ValidationReport` is a
   projection of a graph that has already passed validation by existing at all.
   This inverts the usual validate-after-construct pattern.

3. **Provenance without a provenance store.** The `#ProvenanceTrace` pattern
   computes PROV-O output from the dependency structure. `prov:wasDerivedFrom`
   edges are dependency edges. Provenance is not annotated — it is structurally
   computed. This challenges the assumption that provenance requires separate
   recording infrastructure.

4. **Incremental construction via file addition.** Adding a resource means
   adding a `.cue` file. CUE unification merges it into the existing graph.
   There is no import step, no migration, no re-indexing. The graph extends
   by structural composition. This differs from both batch and streaming
   approaches to KG construction.

5. **Performance ceiling on transitive operations.** CUE does not memoize
   recursive struct references. Transitive closure (ancestors, dependents,
   impact sets) becomes exponential on diamond DAGs beyond ~40 nodes,
   requiring precomputation via external tools. This is a real constraint
   on the approach.

## Resources

- **Website:** [apercue.ca](https://apercue.ca)
- **Data:** Five-node research publication pipeline (ethics approval → sensor
  data → analysis → paper → peer review); 41-node project charter
  (self-modeling)
- **Mappings:** CUE type definitions in `vocab/` and `patterns/` packages —
  63 pattern definitions across 13 files
- **Ontology:** JSON-LD `@context` mapping CUE fields to Dublin Core, PROV-O,
  SHACL, SKOS, OWL-Time, DCAT, ODRL, EARL, schema.org, org
- **Tool(s):** [CUE](https://cuelang.org) v0.15.4, Python toposort for
  precomputation, D3.js for visualization
- **Output:** JSON-LD 1.1 with W3C vocabulary terms; SHACL validation reports;
  PROV-O provenance traces; OWL-Time scheduling intervals; DCAT catalogs
- **Source code:** [github.com/quicue/apercue](https://github.com/quicue/apercue) (Apache 2.0)
- **Full evidence:** [W3C core report](https://github.com/quicue/apercue/blob/main/w3c/core-report.md) — 14 specs, computed JSON evidence
