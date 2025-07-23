## Introduction

## Hackathon Objective 

The main aim of the TerriaMap Hackathon challenge was to explore how
diverse environmental datasets (e.g. Argo, ERDDAP, omics data) could be
visualized and interacted with in the TerriaMap web application,
allowing for cross disciplinary integration of data services from the
FAIR-EASE use cases and infrastructure.

### What is TerriaMap?

TerriaMap is an Open Source, web application for web-based Atlases and
Digital Twin Interfaces.

The Terriamap web application was developed using nodejs and the
Terriajs javascript library. An Overview of the various functionalities
of TerriaMap are described at the website <https://terria.io>

The Terriamap web application can be customised and configured by users
with very little programming experience. An instance of Terriamap can be
configured by editing just 3 json files “serverconfig.json”,
“config.json” and an init json file like the example file “simple.json”
provided in the default configuration of TerriaMap. The user can
configure Terriamap to point at local or remote datasets, files or web
services. Terriamap has support for Open Geospatial Consortium (OGC) web
services, various file formats and Web APIs and also some catalogue data
sources like OGC CSW and CKAN. A Terriamap Instance is configured
through creating “Catalogue Groups” and “Catalogue items” in the init
json file (e.g. the “simple.json” example). A catalogue item can be any
number of different spatial data sources, for example a data layer
created from a CSV file with latitude, longitude and parameter fields,
it can also be a geospatial OGC WMS map layer, these items can then be
arranged logically into catalogue groups. A catalogue group can also be
used to add a collection of available data layers from a remote service
e.g. OGC getCapabilities URLs or a Catalogue Service.

The Terriamap documentation ( <https://docs.terria.io/guide/> ) provides
example json configuration snippets for various data source types as
example “Catalogue Group” and “Catalogue Items”. These can be copied and
customised depending on what data and services the user wishes to
display in their terriamap application instance.

Terriamap can use the temporal information in the geospatial data to
create timeseries graphs and data visualisations. It also provides a
simple slider comparison tool that allows different datasets to be
visually compared on a map.

The TerriaMap github repository is available at this link
<https://github.com/TerriaJS/TerriaMap>
