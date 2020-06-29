# Bridging Knowledge Graphs and Web APIs - University Côte d'Azur, Inria, CNRS

## Context
Over 20.000 Web APIs are registered on programmableweb.com but most of them are closed silos coming with proprietary interfaces with no semantic description. Too bad since they offer huge amonts of useful data, but require the developement of ad-hoc connectors. 
Therefore, we need methods and tools to integrate those APIs with existing knowledge graphs.

Several use cases are foreseen:
- "simple" translation of Web APIs content into RDF
- dynamic enrichment of LOD resources with what can be gathered from Web APIs
- comparison of data from multiple Web APIs to assess multiple points of views about a certain topic (We have a running example in the biodiversity domain where concensus is not always easy to reach, that uses SPARQL queries to compare taxonomic  information from ~20 APIs).
- bring resources locked behind Web APIs into the LOD knowledge graphs

The SPARQL micro-service architecture (see [associated tool](https://github.com/frmichel/resources/blob/master/tools.md#tool-9)) is a proposition towards this end: leverage Web APIs while benefiting from the Web of Data ecosystem: query Web APIs with SPARQL, assign dereferencable URIs, exploit federated SPARQL queries, etc.


## Challenges

- Assist service designer in mapping the Web API result to an RDF representation
- Deal with evolving Web APIs / interface breaks
- Make such APIs discoverable, actionable and composable at webscale. In this regard, SPAQRL micro-services propose the autmatic markup of HTML documentation as http://schema.or/Dataset to allow webscale discoverability, e.g. with Google Dataset Search, and SHACL description to allow for automatic composition.


## Resources
- Website: https://github.com/frmichel/sparql-micro-service
- Mappings: SPARQL construct
- Ontology: anything you like
- Output: https://sparql-micro-services.org/
