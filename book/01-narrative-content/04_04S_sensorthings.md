
## OGC SensorThings API datasets

### Investigating Sensor Things integration

While Terriamap Supports the older OGC SOS (Sensor Observation Service)
Terriamap doesn’t currently support the Newer OGC Sensor Things API

The Terriamap “Api Table”
(<https://docs.terria.io/guide/connecting-to-data/catalog-type-details/api-table/>
) “catalog item” was investigated as an approach to working with the
[OGC Sensor Things API](https://www.ogc.org/standards/sensorthings/),

The Royal Belgian Institute of Natural Sciences publishes Research
Vessel “RV Belgica” underway data using the open Source “Frost Server” (
<https://www.iosb.fraunhofer.de/en/projects-and-products/frost-server.html>
) OGC Sensor Things API.

An initial example was created using the British Geological Survey
Sensor Things Service 

The API is called twice for the display of sensors data.

- One call to get all the sensor locations

- One call to get the data per selected sensor

The json confiurtation snippet is:

```json
{
"type": "geojson",
"name": "STA geojson output",
"id": "123456",
"url":
"https://sensors.bgs.ac.uk/FROST-Server/v1.1/FeaturesOfInterest?$resultFormat=GeoJSON",
"featureInfoTemplate": {
"template":
"<table><tbody><tr><td>Type</td><td>Station</td></tr><tr><td>Value</td><td>{{id}}</td></tr><tr><td>Data
for station {{id}}</td><td><chart
sources='https://sensors.bgs.ac.uk/FROST-Server/v1.1/FeaturesOfInterest({{id}})/Observations?$select=phenomenonTime,result&$top=100&$resultFormat=CSV'
column-names='Time,Signal' column-units='Date,value'
y-column='result'></chart></td></tr></tbody></table><p>Sample data only</p>",
"showFeatureInfoDownloadWithTemplate": false
}
}

```

```{figure} content/image17.png
:height: 350px
:name: figure-image17

BGS Frost Server features
```

Another approach tested to try to resolve the Time issue with only one
feature:

```json
{
"type": "geojson",
"name": "STA one feature test as GEOJSON",
"id": "1234567",
"url":
"https://sensors.bgs.ac.uk/FROST-Server/v1.1/FeaturesOfInterest(49)/Observations?$filter=Datastream/@iot.ideq25&$select=phenomenonTime,result&$expand=FeatureOfInterest&$top=100&$resultFormat=GeoJSON",
"defaultStyle": {
"time": {
"timeColumn": "phenomenonTime",
"idColumns": ["FeatureOfInterest/id"]
},
"chart": {
"xAxisColumn": "phenomenonTime",
"lines": [
{
"yAxisColumn": "result"
}
]
}
}
}
```
The “Api Table” Catalog item did not appear to be a good fit for OGC
Sensor Things Services it was recommended that a new “Sensor Things
Catalog item” would need to be developed as a better fit than the “Api
Table” Catalog item.

There is a discussion on Github
[<u>here</u>](https://github.com/TerriaJS/terriajs/discussions/7561)
with the TerriaMap/TerriasJS developers


### RV Belgica Update

It was found that the TerriaMap geojson catalog item could be used to
access geojson outputs from queries to the Royal Belgian Institute of Natural Sciences Frost Server to display 2023 Survey Data from the sensor things
service.
```json
{
"type": "geojson",
"name": "RV belgica SensorThings locations",
"id": "123456",
"url":"https://sensors.naturalsciences.be/sta/v1.1/Locations?$filter=properties/cruise_identifier%20eq%20%272023/11%27&$top=4200&$resultFormat=GeoJSON",
"styles":[{"id":"@iot.id","color":{"colorPalette":"Reds","legendTicks":4},"pointSize":{"nullSize":1,"sizeFactor":5,"sizeOffset":1},"time":{"idColumns":["@iot.id"]},"hidden":false}]
}
```

```{figure} content/Belgica_2023_geojson_uca.png
:height: 350px
:name: figure-imageBelgica

RV Belgica Frost Server geojson features
```

