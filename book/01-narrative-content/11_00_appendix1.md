
## Appendix 1 - Hackathon Daily Activity reports 

<u>TERRIA MAP CHALLENGE STATUS DAY 1</u>

​​Terriamap is an Australian Open Source Web Application

- Marc worked on setting up a github development process and build
  environment to facilitate configuration contributions

- Marc also offered W3id as an open persistent identifier and url
  shortener with many other useful functionalities

- Nicolas looked at the “table-api” Terrimap “catalog item” as a way of
  interacting with OGC SensorThings API

- Leo and Maxence Worked on bringing ifremer OGC WMS data into Terriamap
  and ways of interacting with and querying ERDDAP Tabular data

- Said contributed a csv spreadsheet of Honga Tonga omics sample
  locations which was visualised in Terriamap, “Featureinfo” templates
  could be used to link to external sample metadata

- Quentin was setting up his environment and looking at the Examind WMS
  data

- David was looking at how Argo Float data for the Mediterranean and
  Geotiffs could be brought into terriamap

- Damian assisting/discussing approaches for adding data

- Eli explained how RO- Crates can store geospatial metadata, e.g.
  geographic points. These could be extracted and used in Terriamap, and
  Terriamap “featureinfo” templates could be used to link to external
  web urls for the RO-Crates

<u>TERRIA MAP CHALLENGE STATUS DAY 2</u>

- Example configuration for working with Omics CSV files to visualise
  sample locations and return relevant Omics data records from The
  European Nucleotide Archive
  ([<u>https://www.ebi.ac.uk/ena/browser/home</u>](https://www.ebi.ac.uk/ena/browser/home)
  ) using the “featureInfoTemplate”

- Said worked on adding additional summary statistics to Omics CSV files
  and styling approaches.

- Nicolas evaluated opportunities for working with OGC Sensor Things
  like APIs

- Marc finished working on initial github collaboration/build repo
  ([<u>https://github.com/fair-ease/terria-config</u>](https://github.com/fair-ease/terria-config)
  )

- Marc and Maxence investigated what would be involved in writing
  extensions to Terriamap, some extensions e.g ERDDAP API like access or
  working with FAIR EASE IDDAS catalog would be \> 2 days work and out
  of scope for the Hackathon

- Marc investigating Exporting useable data records and service types
  info from the FAIR-EASE IDDAS for inclusion in Terriamap.

- Quentin continues to work on Examind configuration (tests with Examind
  WPS, WMS style configuration, WMTS endpoint) and some debug on Examind
  side. Documentation for using Examind with Terriamap has been written
  (import data, styling the data, export it as a wms and use terriamap
  as a client)

- Eli shared info on RO Crate web sites and possible sources of spatial
  information that could be used for Terriamap.

- Example Cloud Optimised Geotiffs brought into Terriamap (Sentinel 2
  True Colour TCI.tiff) for one of the Honga Tonga Islands.

<u>TERRIA MAP CHALLENGE STATUS DAY 3</u>

- All continuing to work on examples

- Continuing to improve Omics examples adding styling etc

- Testing URL encoding workarounds for different dynamic ERDDAP query
  URLs (so that CSV and GeoJSON can be called directly from ERDDAP )

- Nicolas continued testing of Marcs github repo and Build and
  configuration process

- Nicolas cleaning up example Terriamap configuration

- Marc working on a python script to query IDDAS catalog and output
  resource urls for Terriamap to use e.g. Dataset WMS getCapability
  URLs, CSV, GeoJson file download URLs etc.

- Marc ran out of time will commit current version to github and will
  also need to discuss with Paul(Maris) about the sparql graph

- Maxence worked on erddap call url encoding it works fine for the
  ifremer server but seems to be problematic with the ERDDAP server on
  the UCA server, Damian will investigate more also

- All contributing json snippets for “fairease-main.json” configuration
  files

- Quentin cleaned up the examind configuration and published the changes
  on the github repository, finished writing documentation, and
  continued investigating the connection between examind and terriamap
  on various OGC services: WMS and WPS.
