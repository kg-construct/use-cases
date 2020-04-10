# USE CASE DBpedia BY IDLAB

## Context

We tried to change the custom DBpedia mapping rules that were partially defined in a custom wiki syntax and partially hardcoded in the DBpedia EF.

## Challenges

1. Define the data transformation - extract them from the DBpedia EF
2. Process many small data documents, ie many wiki pages each one containing a small set of data
3. Fully analyze the DBpedia EF source code to understand how the mappings should look like

## Resources

- Papers:
  - B. De Meester, W. Maroy, A. Dimou, R. Verborgh, and E. Mannens, “Declarative Data Transformations for Linked Data Generation: the case of DBpedia,” 2017, pp. 33–48, doi: 10.1007/978-3-319-58451-5_3.
  - W. Maroy et al., “Sustainable Linked Data Generation: The Case of DBpedia,” 2017, pp. 297–313, doi: 10.1007/978-3-319-68204-4_28.
- Data: <https://www.wikipedia.org/>
- Mappings: <http://mappings.dbpedia.org/rml_mappings-201705.zip>
- Ontology: <https://wiki.dbpedia.org/services-resources/ontology>
- Output: Materialization using [RMLMapper](https://github.com/RMLio/RML-Mapper) (RDF dump)
