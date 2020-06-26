# Covid-on-the-Web Dataset BY University Côte d'Azur, Inria, CNRS

## Context
*Covid-on-the-Web Dataset* is an RDF dataset that provides two main knowledge graphs produced by analyzing the scholarly articles of the [COVID-19 Open Research Dataset (CORD-19)](https://www.semanticscholar.org/cord19) [1], a resource of articles about COVID-19 and the coronavirus family of viruses:
- the *CORD-19 Named Entities Knowledge Graph* describes named entities identified and disambiguated by NCBO BioPortal annotator, Entity-fishing and DBpedia Spotlight. 
- the *CORD-19 Argumentative Knowledge Graph* describes argumentative components and PICO elements (Patient/Population/Problem, Intervention, Comparison, Outcome) extracted from the articles by the [Argumentative Clinical Trial Analysis](http://ns.inria.fr/acta/) platform (ACTA).


## Challenges
1. Generate a consistent KG from multiple inputs: CORD-19 corpus, named entities extraction tools, ACTA. Each input comes with its own format that requires adapting of the KG generation pipeline.
2. Huge amount a JSON data to process: 50M+ named entities (extracted from 50K+ articles) to describe in RDF. Our mapping tool generates RDF in memory before saving the result. Needs fine-tuning to keep acceptable memory/cpu/time usage. A streaming mode would be more appropriate.
3. Input JSON documents require pre-processing (cleanup of erroneous characters, filtering) that we have done using MongoDB, but having everything in the mapping description would avoid too many steps.
4. Frequent updates of CORD-19 require regular update of the KGs
5. Specific iteration needs in the JSON-to-RDF mapping

## Resources
- Website: https://github.com/Wimmics/CovidOnTheWeb
- Data: [SPARQL endpoint](https://covid19.i3s.unice.fr/sparql), download: see website
- Mappings: [Morph-xR2RML](https://github.com/frmichel/morph-xr2rml/), an implementation of the [xR2RML mapping language](http://i3s.unice.fr/~fmichel/xr2rml_specification.html) for MongoDB databases. Mapping files: https://github.com/Wimmics/CovidOnTheWeb/tree/master/src/xR2RML
- Ontology: BIBO, Dublin Core, FABIO, FOAF, Web Annotations Ontology, PROV-O, Schema.org, Argument Interchange Format, Argument Model Ontology, SIOC Argumentation Module
- Output: we experiment with several visualization tools to display the co-occurrence network of named entities (e.g. co-occurence of a cancer and a virus of the coronavirus family). Examples [with a specific lib](https://github.com/Wimmics/CovidOnTheWeb/blob/master/doc/mgexplorer-1.png) called MGexplorer, or [with Jupyter Notebooks](https://github.com/Wimmics/CovidOnTheWeb/blob/master/doc/R4.JPG)
