# Madrid Public Transport - Ontology Engineering Group

## Context
Transmodel is the European Reference Data Model for Public Transport. It provides a conceptual model of common public transport concepts and data structures that can be used to build many different kinds of public transport information system such as timetabling, fares, operational management, real-time data, journey planning. The General Transit Feed Specification (GTFS) is a de-facto standard developed by Google for the description of public transport schedules, routes, fares, etc. and publish open data in the web by transport authorities. National Access Point (NAP) aims to have an entry point of transport data for each EU member following the Transmodel vocabulary.


## Challenges
1. Optional columns and files in source model (GTFS)
2. Many relations among input sources (join-conditions)
3. Application of CSVW constraints and FnO to manage heterogeneity (only in Virtualization with Morph-CSV atm)
4. Query tabular data sources


## Resources
- Website: http://sprint-transport.eu/ and https://www.snap-project.eu/
- Data: any GTFS file like the ones at https://datos.crtm.es/
- Mappings: https://github.com/oeg-upm/gtfs-bench/tree/master/mappings  
- Ontology: https://github.com/OpenTransport/linked-gtfs/blob/master/spec.md (to be replaced by Transmodel)
- Output: 
	- Option 1: Materialization using [SDM-RDFizer](https://github.com/SDM-TIB/SDM-RDFizer) (RDF dump)
	- Option 2: Virtualization using [Morph-CSV](https://github.com/oeg-upm/morph-csv) (SPARQL result set)