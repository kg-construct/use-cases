# USE CASE BERD BY Mannheim University Library ([UBM](https://www.bib.uni-mannheim.de))

## Context

**Motivation.** German company data are spread over many providers, registers and time spans. 
The company identifiers in Germany are sadly famous for their lack of uniqueness, inconsistent 
representations and multiple registrations per legal entity 
([see OpenCorporates blog](https://blog.opencorporates.com/2019/02/19/wait-what-the-problems-of-company-numbers-in-germany-and-how-were-handling-them)).
The modern data were scraped and processed by [OpenCorporates](https://opencorporates.com). 
The main historical datasets were digitized and processed by [Mannheim University Library](https://www.bib.uni-mannheim.de/en/teaching-and-research/research-data-center).

**Goal.** Create a knowledge graph-based research infrastructure for German company datasets in order to improve access to German Business, Economic and Related Data (BERD).

**Software.** We chose [Wikibase](https://wikiba.se) for creating and maintaining a knowledge graph.

## Challenges

1. Data integration
2. Data quality: non-unique identifiers & OCR-ed data
3. Scaling a Wikibase-based knowledge graph

## Resources

- Websites:
  * [BERD@BW](https://www.berd-bw.de)
  * [BERD@NFDI](https://www.berd-nfdi.de)
- Data:
  * [Historical](https://www.bib.uni-mannheim.de/en/teaching-and-research/research-data-center) - unstructured and semi-structured datasets
  * [Modern](https://offeneregister.de) - OpenCorporates dataset
- Tools:
  * [bbw](https://github.com/UB-Mannheim/bbw) - semantic annotator for tabular data
  * [RaiseWikibase](https://github.com/UB-Mannheim/RaiseWikibase) - a tool for speeding up data integration and knowledge graph construction using Wikibase
