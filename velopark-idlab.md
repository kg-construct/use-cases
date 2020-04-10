# USE CASE Velopark BY IDLAB

## Context

The [Velopark project](https://velopark.be) aimed on creating a common platform and data model for publishing bicycle parking data in Belgium. Live occupancy information existed already for some parkings through ad-hoc APIs. We used RML to map such data into the [Velopark model](https://velopark.ilabt.imec.be/openvelopark/vocabulary) and republish it as Linked Open Data.  


## Challenges
1. Aligning identifiers: Data coming from non-Linked Data APIs give different identifiers to the parkings compared to the ones that Velopark uses.
2. Live occupancy is a data stream, mapping processes need to happen with a certain periodicity.

## Resources
- Website: https://velopark.be
- Data:
  - Kortrijk parking [linked data](https://velopark.ilabt.imec.be/data/live/kortrijk) - [original API](https://stallingsnet.nl/api/3/parkingcount/kortrijk?apiKey=NzgxOlduaEFfU0t2Z2FicDRKaWh0bXVzNTFUN3pKUT0=)
  - Gent parkings [linked data](https://velopark.ilabt.imec.be/data/live/gent) - [original API](https://datatank.stad.gent/4/mobiliteit/realtimebezettingfietsenstallingen.json)
  - Vilvoorde parking [linked data](https://velopark.ilabt.imec.be/data/live/vilvoorde) - [original API](https://api.fietskluis-app.nl/public-api/locations/8b842ad4-6193-42fc-b1ee-591226fb2ce4)
- Mappings: https://github.com/linkedtimeseries/timeseries-server/tree/develop/mappings 
- Ontology: https://velopark.ilabt.imec.be/openvelopark/vocabulary
- Output: [Time-Series Server](https://github.com/linkedtimeseries/timeseries-server/tree/develop) to republish non-Linked Data streams.
