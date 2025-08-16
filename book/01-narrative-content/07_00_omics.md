# Omics Data 

### Sample CSV File with Omic’s reference id and Coordinates

Using the example Omics CSV files created by the Università degli Studi
di Napoli Federico II (UNINA), TerriaMap was configured to use the Omics
dataset IDs e.g. "library_id" and "Run" fields in the data to
dynamically construct a clickable hyperlink in a Terriamap featureInfo
popup. The hyperlinks link to further information on data collected at a
specific location

(e.g.
  href='https://www.ebi.ac.uk/ena/browser/view/{{Run}} )

to browse to the metadata for the dataset/sample in the European
Nucleotide Database.

```{figure} content/image22.png
:height: 350px
:name: figure-image22

UNINA CSV file
```

The “library_id” field can be used in a “featureInfoTemplate” using
mustache templating in to replace the id in the popup url with the
“library_id” for the feature

```json
"featureInfoTemplate": {
"template": "<div class='ena'><small>Record:
{{library_id}}</small><p><a target='_enaurl'
href='https://www.ebi.ac.uk/ena/browser/view/{{library_id}}'\>Open
European Nucleotide Archive Record </a></div>"
}

```
### Terriamap Omic’s sample CSV files json Snippets

```json
{
"type": "csv",
"name": "Honga Tonga Marmdb",
"id": "TongaMarmadbomics",
"url": "test/omics/HungaTonga_latlon_marmdb.csv",
"styles":[{"id":"User
Style","color":{"nullColor":"rgba(229,220,220,1)"},"hidden":false}],
"activeStyle":"User Style",
"columns": [
  {
    "name": "library_id",
    "type": "hidden"
  }
 ],
  "featureInfoTemplate": {
  "template": "<div class='ena'><small>Record:
  {{library_id}}</small><p><a target='_enaurl'
  href='https://www.ebi.ac.uk/ena/browser/view/{{library_id}}'>Open
  European Nucleotide Archive Record </a></div>"
  }
}
```

Clicking the URL in the popup dialog box will open a browser tab to the
relevant record(s) in the ENA Archive.

```{figure} content/image23.png
:height: 350px
:name: figure-image23

Feature Information with dynamic ENA link
```

### OMICs KML Example performance issues

UNINA also provided some relevant Honga Tonga omics metadata output as
KML (HungaTonga_metadata.kml), Terriamap supports the KML data format
originally developed and used by the google earth 3D viewer technology.

However the sample Honga Tonga metadata KML data when loaded in
Terriamap appeared to slow down performance in some browsers increasing
CPU and memory usage (e.g. Microsoft Edge), this may have been related
to the styling information or the particular format of the data in the
KML file.

We did not have time to fully debug the performance issues. To work
around these KML rendering performance problems, the Honga Tonga Omics
metadata KML was converted into geojson format using the open source
geospatial [gdal](https://gdal.org/en/stable/) translator utility
“ogr2ogr”. The KML file was converted into geojson
(“HungaTonga_metadata_year.geojson”) using the following gdal ogr2ogr
command:

```console
ogr2ogr -f "GeoJSON" HungaTonga_metadata_year.geojson HungaTonga_metadata.kml -sql "SELECT Name AS survey_year, Name as Year, description as description, tessellate as tessellate, extrude as extrude, visibility as visibility FROM HungaTonga_metadata"
```
We also used the opportunity of the conversion process to rename the
“Name” field to “survey_year” This “HungaTonga_metadata_year.geojson”
file loads without causing any rendering performance issues.

```{figure} content/image24.png
:height: 350px
:name: figure-image24

UNINA geojson file
```


### Aggregating Taxonomy and Diversity data with SAMBA Omics data as CSV

The Ifremer Omics team looked at manually merging some example Honga
Tonga data from SAMBA TSV file outputs (see [SAMBA
report](https://ifremer-bioinformatics.github.io/SAMBAExampleReport/SAMBA_report.html)
) to create an omics csv file (see
[geolocalisation_with_asvs.csv](https://github.com/fair-ease/terria-config/blob/main/wwwroot/fairease.eu/data/omics/geolocalisation_with_asvs.csv)
) with spatial information and more Omics metrics information like chao1
diversity index (Selecting and filtering on this different Metric
information is also possible in Terriamap ).

The terriamap dynamic hyperlink generation was also used to redirect
dynamically from the various map point pop ups to the relevant records
in the European Nucleotide Database (ENA) Portal. While this data was
hand crafted from the SAMBA output files, it hints at a possible output
format that could make the mapping and exploration of such information
in map viewers like TerriaMap more easily achieved.

SAMBA metadata rendered in Terriamap:

```{figure} content/image25.png
:height: 350px
:name: figure-image25

Ifremer SAMBA metadata and styling
```


changed json template

```json
{
"name": "ASV diversity data",
"description": "Honga tonga data from 2018-2019 ",
"type": "csv",
"id": "xx98JHt",
"url": "test/geolocalisation_with_asvs.csv",
"featureInfoTemplate": {
"template": "<div class='microbiome-data'><h3>Sample:
{{RUN_ID}}</h3><div class='data-section'><h4>Location
Information</h4><p><strong>Location:</strong>
{{geo_loc_name}}</p><p><strong>Country:</strong>
{{geo_loc_name_country}}
({{geo_loc_name_country_continent}})</p></div><div
class='data-section'><h4>Diversity Metrics</h4><p><strong>Chao1
Index:</strong> {{chao1_Index}}</p><p><strong>ASV
Count:</strong> {{asv_count}}\</p><p><strong>Phylum
Diversity:</strong> {{phylum_diversity}}
phyla</p><p><strong>Family Diversity:</strong>
{{family_diversity}} families</p></div><div
class='data-section'><h4>Taxonomic
Profile</h4><p><strong>Dominant Phylum:</strong>
{{dominant_phylum}}</p><p><strong>All Phyla:</strong>
{{all_phyla}}</p><p><strong>Phylum Profile:</strong>
{{phylum_profile}}</p></div>{{#RUN_ID}}<div
class='data-section'><h4>External Links</h4><p><strong>ENA
Browser:</strong> <a target='_blank'
href='https://www.ebi.ac.uk/ena/browser/view/{{RUN_ID}}'>View Run
{{RUN_ID}} in ENA</a></p></div>{{RUN_ID}}</div>",

"formats": {
"csv": {
"formats": {
"chao1_Index": {
"type": "number",
"maximumFractionDigits": 0
},
"asv_count": {
"type": "number",
"maximumFractionDigits": 0
},
"phylum_diversity": {
"type": "number",
"maximumFractionDigits": 0
},
"family_diversity": {
"type": "number",
"maximumFractionDigits": 0
  }

                }

               }

               }

              }

         }
```