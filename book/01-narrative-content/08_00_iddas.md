
# IDDAS Catalogue Integration – SPARQL endpoint querying 

VLIZ looked at approaches to interacting with the IDDAS catalogue, while
Terriamap supports interacting with OGC CSW and CKAN data catalogues, at
the time of the hackathon there was no OGC CSW interface to the IDDAS.
Vliz started an initial investigation at querying the IDDAS SPARQL
endpoint to get a list of datasets with either OGC Web service
interfaces or data formats that could be output in a format that could
be used in TerriaMap. The initial code is available in Github (see
<https://github.com/fair-ease/py-iddas-query>). The “py-iddas-query”
code can query the IDDAS and produce a tabular result set (data frame)
with matching results, available parameters as well as available fields
in the result set

(which is a programmable variant of the UI at
<https://fair-ease-iddas.maris.nl/>). There was insufficient time at the
Hackathon to work on this further.
