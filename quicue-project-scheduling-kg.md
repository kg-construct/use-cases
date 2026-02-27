# USE CASE: PROJECT SCHEDULING KNOWLEDGE GRAPHS BY QUICUE

## Context

The [apercue.ca](https://github.com/quicue/apercue) project implements project
scheduling — critical path method (CPM), milestone evaluation, gap analysis, and
test planning — as CUE type constraints that produce a knowledge graph.

A `#Charter` declares required resources, types, and completion gates. A
`#GapAnalysis` pattern unifies the charter against a `#Graph` and computes what
is missing. `cue vet` fails if the project is incomplete. The result is a
scheduling KG where project management concerns (milestones, dependencies,
slack, critical path) are W3C vocabulary terms, not proprietary fields.

```cue
#Charter: {
    scope: {
        total_resources:    int
        required_resources: {[string]: true}
        required_types:     {[string]: true}
    }
    gates: [...#Gate]
}
```

The same 5-node research publication pipeline used across all apercue
submissions produces a 285-day critical path with forward/backward scheduling
passes, OWL-Time interval output, and SHACL validation reports for gate
completion.

## Challenges

1. **Encoding scheduling as a knowledge graph, not alongside one.** Project
   schedules are typically stored in proprietary formats (MS Project, Jira) and
   optionally linked to KGs. In CUE, the schedule IS the graph — each resource
   has `time:hasBeginning`, `time:hasEnd`, `time:hasDuration` as OWL-Time
   intervals, plus `apercue:slack` and `apercue:isCritical` extensions.
   Critical path computation is a graph traversal, not a separate tool.

2. **Gap analysis as constraint violation.** A gate requiring
   `{sensor-dataset: true, ethics-approval: true}` is a set membership check.
   Missing resources produce `sh:conforms: false`. This means project
   incompleteness is a SHACL validation failure — the same mechanism used for
   data quality in standard KG validation. The question: should KG-Construct
   consider project management artifacts as a KG construction target?

3. **Multi-domain scheduling from a single pattern.** The same `#CriticalPath`
   pattern has been applied to research data management (5 nodes), IT
   infrastructure (30 nodes), university curricula (12 courses), and
   construction project management (18 work packages). The pattern is
   domain-agnostic — only the resource declarations change. This suggests
   scheduling KGs are a reusable construction pattern, not a domain-specific
   application.

4. **EARL test reports from smoke test definitions.** Test plans produce
   `earl:Assertion` entries with `earl:passed` / `earl:failed` outcomes.
   Smoke tests defined in CUE become part of the scheduling KG — they are
   resources with dependencies, durations, and critical path positions.
   Testing infrastructure becomes part of the project graph.

5. **Performance ceiling.** As with all apercue patterns, CPM recursive
   fixpoint computation times out on graphs exceeding ~38 nodes. The
   `#CriticalPathPrecomputed` variant uses Python-precomputed topology to
   work around this CUE evaluation constraint.

## Resources

- **Website:** [apercue.ca](https://apercue.ca)
- **Data:** Five-node research pipeline (CPM: 285-day duration, 0 slack);
  41-node self-charter (8 phase gates, all satisfied)
- **Mappings:** `#Charter`, `#GapAnalysis`, `#CriticalPath`,
  `#CriticalPathPrecomputed`, `#SinglePointsOfFailure` in `patterns/` package
- **Ontology:** OWL-Time (`time:Interval`, `time:Duration`, `time:Instant`),
  SHACL (`sh:ValidationReport`), EARL (`earl:Assertion`), Dublin Core
  (`dcterms:requires`)
- **Tool(s):** [CUE](https://cuelang.org) v0.15.4, Python toposort for
  precomputation, D3.js for Gantt and graph visualization
- **Output:** OWL-Time scheduling intervals; SHACL gate-completion reports;
  EARL test assertions; CPM summary (critical path, slack, duration)
- **Source code:** [github.com/quicue/apercue](https://github.com/quicue/apercue) (Apache 2.0)
- **Full evidence:** [W3C core report](https://github.com/quicue/apercue/blob/main/w3c/core-report.md)
