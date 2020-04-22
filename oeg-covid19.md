# COVID19 KG From Scientific Literature - Ontology Engineering Group

## Context
We want to create a catalog of medicines used to combat COVID-19, according to scientific literature, through the use of Artificial Intelligence and Citizen Science techniques.

## Challenges
1. Data comes from NLP tools and is stored in SOLR databases
2. Parallel defintion of the Ontology (not aligned with source data)
3. Normalization steps (many multivalue columns)
4. Flexible pipeline for continuos changes

## Resources
- Website: https://drugs4covid.oeg-upm.net/EN
- Data: http://librairy.linkeddata.es/data/#/covid/query
- Mappings: https://github.com/oeg-upm/drugs4covid19-kg/blob/master/mapping05042020.yaml
- Ontology: https://w3id.org/def/DRUGS4COVID19
- Output (using [SDM-RDFizer](https://github.com/SDM-TIB/SDM-RDFizer)):
![pipeline](images/oeg-covid.png?raw=true)

