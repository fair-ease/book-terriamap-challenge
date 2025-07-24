## Location-tagged RO-Crates

During the Hackathon a brief investigation was conducted into how
RO-Crate geospatial metadata could be imported into TerriaMap. Some of
the web sources of RO-Crates were investigated. It was found that there
is some divergence as to how geospatial metadata is implemented in
RO-Crates. Further investigation would be required, possibly looking at approaches to extracting and indexing geospatial data in RO-Crate archives and generating a csv or geojson file to visualise points or areas relevant to specific RO-Crates in TerriaMap. 

### RO-Crate geospatial metadata Specification

This is the guidance on how to represent geospatial metadata in an
RO-Crate
[<u>https://www.researchobject.org/ro-crate/specification/1.2-DRAFT/contextual-entities.html#places</u>](https://www.researchobject.org/ro-crate/specification/1.2-DRAFT/contextual-entities.html#places)


Not every implementation follows this guidance as it is not mandatory,
it is a recommendation.

### ROHub

[<u>https://www.rohub.org/explore?page=1&page_size=9&ordering=-created&activetab=ro</u>](https://www.rohub.org/explore?page=1&page_size=9&ordering=-created&activetab=ro)

filter by tags \> location, there are just a few location-tagged
datasets there. They can be downloaded as RO-Crates from the individual
dataset page. They use location to link to the geospatial metadata

### LDaCA (Language Data Commons of Australia)

Farms to Freeways Example Dataset

[<u>https://data.ldaca.edu.au/collection?id=arcp%3A%2F%2Fname%2Chdl10.4225~35~555d661071c76&\_crateId=arcp%3A%2F%2Fname%2Chdl10.4225~35~555d661071c76</u>](https://data.ldaca.edu.au/collection?id=arcp%3A%2F%2Fname%2Chdl10.4225~35~555d661071c76&_crateId=arcp%3A%2F%2Fname%2Chdl10.4225~35~555d661071c76)

(the full dataset is >1GB but the metadata can be downloaded
separately)

It’s a single RO-Crate containing a collection of many interviews, each
interview has location data linked through contentLocation - the
metadata follows this guidance in the RO-Crate specification:
[<u>https://www.researchobject.org/ro-crate/specification/1.2-DRAFT/contextual-entities.html#places</u>](https://www.researchobject.org/ro-crate/specification/1.2-DRAFT/contextual-entities.html#places)

### ARP Research Data Repository

This is a Dataverse instance based in Hungary.

[<u>https://repo.researchdata.hu/dataverse/hun-ren?q=&fq2=subject_ss%3A%22Earth+and+Environmental+Sciences%22&fq0=subtreePaths%3A%22%2F210%22&fq1=dvObjectType%3A%28dataverses+OR+datasets%29&types=dataverses%3Adatasets&sort=dateSort&order=</u>](https://repo.researchdata.hu/dataverse/hun-ren?q=&fq2=subject_ss%3A%22Earth+and+Environmental+Sciences%22&fq0=subtreePaths%3A%22%2F210%22&fq1=dvObjectType%3A%28dataverses+OR+datasets%29&types=dataverses%3Adatasets&sort=dateSort&order=)

filtered for Earth and Environmental Sciences - a number of datasets
have location data.

They use geographicalCoverage to link it (a term from the Dataverse
schema)