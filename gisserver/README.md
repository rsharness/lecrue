# LeCrue GIS server project

## Project Setup

`download the following files from google-drive:`

- datastor (folder)
- michigan-latest.osm
- red_suitability.tif
- white_suitability.tif

`TODO: zip all of these up....`

`copy /datastore - into geoserver-shawn`

`copy the following files into:`

** /datastore/tiffs

 - michigan-latest.osm
 - red_suitability.tif
 - white_suitability.tif

## Running the Project

`cd geoserver-shawn`
`docker-compose up -d`

[Mapstore Front End](http://localhost/mapstore)

- login: admin/admin

[geoserver](http://localhost:8080/geoserver)

- login/pass: admin/geoserver

** Database info
postgis db

- host: 172.31.0.101
- port: localhost:5432
- database: gis
- user: cartographer
- pass: Jules20kVerne

Select "Layer Preview" in left menu

click "Open Layers"

optional support apps = qgis
installed locally on administrators machine

### import OSM file into postgis

** need to update paths for operation within datastor project dir
osm2pgsql -c -d gis  -H 127.0.0.1 -U cartographer -W -S ./default.style ./michigan-latest.osm

###mapstore geoserver integration:
[GeoServer Integration](http://172.31.0.100:8080/geoserver/lecrue/wms?request=getCapabilities)
