# USE CASE Open Data Hub-Virtual Knowledge Graph BY Ontopic 

## Context

Open Data Hub-Virtual Knowledge Graph (ODH-VKG) is a joint project between [NOI Techpark](https://noi.bz.it/en)
and [Ontopic](http://ontopic.biz/) for publishing South Tyrolean tourism data as a Knowledge Graph. Before
the project started, the data was accessible through a [JSON-based Web API](https://opendatahub.bz.it/), backed by a
PostgreSQL database. We created a VKG over the database and a [SPARQL endpoint](https://sparql.opendatahub.bz.it/)
that is much more flexible and powerful than the old Web API. 

## Challenges

1. *Data and Mapping*. For historical reasons, all the database tables are of two columns `id` and `data`, where `id` is a UUID identifying a row and `data` is a JSON object containing rich information. In order to access the internal content of `data`, we have created a customized script to sample the data and extract all possible fileds from the `data` column. Then we create a "relational version" of original table. When there is an array nested in `data`, we need to create a separate table pointing to the parent table using foreign keys.
2. *Ontology*. The ontology is mostly based on based on schema.org, but we often need to extend it. E.g., `:BeerGarden rdf:type owl:Class ; rdfs:subClassOf schema:BarOrPub .`

## Resources

- Websites: 
    - Endpoint: <https://sparql.opendatahub.bz.it/>
    - Source code: <https://github.com/noi-techpark/odh-vkg>
- Data: A snapshot version of the database is available as a [Docker Image](https://hub.docker.com/repository/docker/ontopicvkg/odh-tourism-db)
- Mappings: <https://github.com/noi-techpark/odh-vkg/blob/master/vkg/odh.obda> in Ontop Mapping Syntax
- Ontology: <https://github.com/noi-techpark/odh-vkg/blob/master/vkg/odh.ttl>
- Tools
    - [Ontop](http://ontop-vkg.org) for setting up the SPARQL endpoint
    - Ontop Protege plugin for developing ontology and mapping
    - [Customized Script](https://github.com/noi-techpark/odh-vkg/blob/master/scripts/create_derived_tables_and_triggers_from_db.py) for sampling  thedata and create the "relational version" of the original data.
- Output 
    - [SPARQL Endpoint](https://sparql.opendatahub.bz.it/)
