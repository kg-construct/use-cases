# USE CASE Genomics (Lung Cancer) BY TIB/SDM

## Context

Precision oncology and personalized medicine rely on the accurate integration and interpretation of genomic data including variants to allow individualized treatment selection, diagnosis, prediction, and prognosis. This use case tries to provide a view of processing and semantification that are required in order ot integrate genomic open source data and create a KG. 

## Challenges

1. Data required to be pre-processed in order to be compatible with URI standards
2. In some cases NLP tools are needed to be applied in order to annotate data and extract information from texts
3. Beside entity recognition, further id reresentations are required to be created in order to link genomic data that are represented in different accepted standard formats. 
4. Manual curation by experts are needed in order to provide mapping between different concepts in data sources and concepts in the ontology.

## Resources

- Website: https://github.com/SDM-TIB/LungCancerGenomicKG
- Data: https://cancer.sanger.ac.uk/cosmic , https://civicdb.org/home , https://www.oncokb.org/
- Mappings: https://github.com/SDM-TIB/LungCancerGenomicKG/tree/master/mapping
- Output: RDF triples are created using https://github.com/SDM-TIB/SDM-RDFizer

