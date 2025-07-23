## Creating a Terriamap Instance

### TerriaMap Documented approach

The Terriamap [getting
started](https://docs.terria.io/guide/getting-started/) documentation
describes how to create a test or development instance using a docker
container (e.g. on a laptop) and passing the 3 configuration files to
the container.

```console
docker run -d -p 3001:3001 \
--mount type=bind,source=$(pwd)/config.json,destination=/app/wwwroot/config.json \
--mount type=bind,source=$(pwd)/my-catalog.json,destination=/app/wwwroot/init/simple.json \
--mount type=bind,source=$(pwd)/serverconfig.json,destination=/app/serverconfig.json \
ghcr.io/terriajs/terriamap
```

### FAIR-EASE terria-config github makefile approach

During the Hackathon we looked at an opinionated Vliz aproach to
storing a Terriamap configuration in Github and cloning, configuring and
building a Terriamap Instance using a makefile

The approach is described in the github repo
[https://github.com/fair-ease/terria-config](https://github.com/fair-ease/terria-config)

It uses a FAIR-EASE “fairease-main.json” init file and a separate fair
www/fairease.eu folder for storing resources.

### Galaxy Europe TerriaMap Interactive tool

At the FAIREASE Hackathon Bjorn from the Galaxy Europe team created a
tool in Galaxy for launching a Terriamap instance, the user can supply
their own configuration file to the tool and launch a customised
instance of Terriamap on the Galaxy platform. This is mentioned in a
Galaxy project Blog post.

<https://galaxyproject.org/news/2025-04-02-fair-ease-brest-hackathon-2025-news-post/#galaxy-hackathon-in-brest-france-innovation-on-the-edge-of-the-ocean>

**TerriaMap Interactive Tool** added to Galaxy

- [Tool
  link](https://usegalaxy.eu/root?tool_id=interactive_tool_terriamap)

- [Repo](https://github.com/usegalaxy-eu/galaxy/tree/release_24.2_europe/tools/interactive/terriamap)

<https://usegalaxy.eu/root?tool_id=interactive_tool_terriamap>

<https://github.com/usegalaxy-eu/galaxy/tree/release_24.2_europe/tools/interactive/terriamap>

## Configuring Terriamap

To configure Terriamap the json config file (e.g. “simple.json” file) in
the wwwroot/init directory needs to be edited to add “Catalog Groups”
and “Catalog items” when configuring a custom Terriamap Instanc

The serverconfig.json file may also need to be edited if Terriamap is to
be configured to access remote services on servers with restrictive CORS
settings, these sites will be proxied by the TerriaMap application so
that the data from these sites can be used.

The config.json file stores general “look and feel” settings for the
Terriamap instance as well as API keys for map and data services that
require these (bing maps, cesium ion etc) and also the config.json can
be used to tell Terriamap to use a different json file than
“simple.json” for defining the Terriamap Catalogue Groups and Items.

The “simple.json” file in the wwwroot/init directory has a few example
group and item configurations demonstrating how map data from various
Australian and international open data services can be brought into
Terriamap.

[https://raw.githubusercontent.com/fair-ease/TerriaMap/refs/heads/fairease/wwwroot/init/simple.json](https://eur01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fraw.githubusercontent.com%2Ffair-ease%2FTerriaMap%2Frefs%2Fheads%2Ffairease%2Fwwwroot%2Finit%2Fsimple.json&data=05%7C02%7Cdamian.smyth%40marine.ie%7C10759845bece4598689f08dd5fb7f34c%7C12cb7a361f0944a4b614b3eacaffb718%7C0%7C0%7C638771967144945807%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=JLypio%2BmG7KMvuTJhRkFeYJyEuPMr0GgajfsqJ9mW%2F0%3D&reserved=0)

The “simple.json” is used to populate the “Explore Data” menu with
predefined “catalogue groups” and individual services “catalogue items”.

**“Upload Data”**

The “Upload Data” button can be used to initially test some local data
on the users systmen or remote data sources and supported file formats.

```{image} ../content/image1.png
:alt: screenshot add local file
:align: center
```

It is also possible to add and explore some remote standard Web APIs and
OGC Services via the Upload button.

```{image} ../content/image2.png
:alt: screenshot add web data 
:align: center
```
