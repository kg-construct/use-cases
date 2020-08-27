# Kadaster Data Platform

## Context
[Kadaster](https://www.kadaster.nl/about-us), the Dutch cadastre, land registry and mapping agency, is responsible for publishing several Dutch key registry datasets. Kadaster has developed a data platform for the publishing of data in a variety of ways, including as RDF linked data, GraphQL and as RESTful APIs.
The data platform's services are offered to other government organizations to publish their data as Linked Data or RESTful APIs.

## Challenges
1. Manipulating source data to generate correct IRIs
2. Reprojecting input geometry data
3. Size of the data
4. Variety of schemas

## Resources

### BAG - Key Registry Addresses and Buildings
The BAG is the Dutch Key registry of addresses and buildings.

Kadaster has published this dataset as linked data.

- Website: https://bag.basisregistraties.overheid.nl
- Data: GML data according to BAG Extract
- Mappings: RML
- Ontology: http://bag.basisregistraties.overheid.nl/def/bag
- Tool(s) (transformation/access tool but also mapping generator tools): [CARML](https://github.com/carml/carml)
- Output (you could have several outputs with different features, figures with the workflow are also welcome): RDF

### BRK-DKK - Open Cadastral map
The BRK is the Dutch Key registry for Cadastral information. The DKK is a subset of this dataset that contains open data. This dataset includes geographical features such as parcel geometries, that are used to create parcel map overlays.

Kadaster has published this dataset as linked data.

- Website: https://brk.basisregistraties.overheid.nl
- Data: GML data dump from https://downloads.pdok.nl/kadastralekaart/api/v4_0/ui/
- Mappings: RML
- Ontology: http://brk.basisregistraties.overheid.nl/def/brk
- Tool(s) (transformation/access tool but also mapping generator tools): [CARML](https://github.com/carml/carml)
- Output (you could have several outputs with different features, figures with the workflow are also welcome): RDF

### BRT-top10nl - Topography Key Registry
The BRT is the Dutch key registry for topography containing information to create detailed maps of the Netherlands.

Kadaster has published this dataset as linked data.

- Website: https://brt.basisregistraties.overheid.nl
- Data: GML data dump from https://downloads.pdok.nl/kadastralekaart/api/v4_0/ui/
- Mappings: RML
- Ontology: http://brt.basisregistraties.overheid.nl/def/top10nl
- Tool(s) (transformation/access tool but also mapping generator tools): [CARML](https://github.com/carml/carml)
- Output (you could have several outputs with different features, figures with the workflow are also welcome): RDF

### Ruimtelijke Plannen - Spatial Planning API
The spatial planning API is used to provide information for the execution of Spatial Planning in the Netherlands. This API uses RDF data as it's source under the hood and drives the [DSO Viewer](https://viewer.dso.kadaster.nl/) application. 

- Website: https://aandeslagmetdeomgevingswet.nl/ontwikkelaarsportaal/api-register/api/rp-opvragen/
- Data: XML and GML sources from various governmental organizations collected via https://www.ruimtelijkeplannen.nl/
- Mappings: RML
- Ontology: unpublished
- Tool(s) (transformation/access tool but also mapping generator tools): [CARML](https://github.com/carml/carml)
- Output (you could have several outputs with different features, figures with the workflow are also welcome): RDF


### Bestuurlijke Grenzen - Administrative Units API
The [administrative Units API](https://brk.basisregistraties.overheid.nl/api/bestuurlijke-grenzen/v1) is an API used to provide administrative boundaries for the execution of Spatial Planning in the Netherlands. This API uses RDF data as it's source under the hood.

- Website: https://brt.basisregistraties.overheid.nl
- Data: GML data from various government sources, including https://www.pdok.nl/geo-services/-/article/bestuurlijke-grenzen
- Mappings: RML
- Ontology: unpublished
- Tool(s) (transformation/access tool but also mapping generator tools): [CARML](https://github.com/carml/carml)
- Output (you could have several outputs with different features, figures with the workflow are also welcome): RDF
