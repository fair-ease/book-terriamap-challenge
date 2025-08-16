
# Examind

The Open Source Examind Community Edition (
<https://www.examind.com/en/examind-community/> ) was used in the
FAIR-EASE project for demonstrating the publication of datasets using
OGC compatible web services and sharing and visualising geospatial data.

Examind Community Edition is built on top of Apache SIS ([Apache SIS -
The Apache SIS library](https://sis.apache.org/)) and has strong
support for the OGC services used by Terriamap.

#### Examind documentation

Quentin from Geomatys has produced a number of tutorials on working with
Examind and using Examind with Terriamap.

<https://github.com/fair-ease/Examind_Tutorials/tree/main>

Setup WMS, and visualisation in Terriamap:

- Import data: [How to import my data in
  examind](https://github.com/fair-ease/Examind_Tutorials/blob/main/wms-terriamap/import_data.md)
  ?

- Style data: [How to set a style to my data in
  examind](https://github.com/fair-ease/Examind_Tutorials/blob/main/wms-terriamap/style_data.md)
  ?

- WMS setup: [WMS setup
  example](https://github.com/fair-ease/Examind_Tutorials/blob/main/wms-terriamap/wms_setup.md)

- Terriamap configuration for Examind WMS: [Terriamap configuration
  example](https://github.com/fair-ease/Examind_Tutorials/blob/main/wms-terriamap/terriamap_config.md)

- Terriamap setup example: [FairEase
  Terriamap](https://github.com/fair-ease/terria-config)

### Beacon

The “Beacon” server ( <https://beacon.maris.nl/> ) was developed by
Maris as part of the Blue cloud project. Beacon was used in the
FAIR-EASE project for data exploration demonstrations, it can be used to
query large data archives and export Marine Datasets in a variety of
data formats including CSV, netcdf and parquet, it can also be
configured to expose some datasets in OGC WMS format.

As part of the Terriamap Challenge an example beacon CSV file export was
configured in Terriamap, this was a subset of the nearest Argo BGC data
from CMEMS data from the Pacific time of the Hunga Tonga eruption.
```json
{
"type": "csv",
"name": "CMEMS BGC Beacon",
"url": "test/CMEMS_BGC.csv",
"activeStyle": "Magnitude",
"id": "cmemsbgcbeacon"
}
```