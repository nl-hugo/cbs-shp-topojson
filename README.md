# cbs-shp-topojson
A npm command-line tool to download and convert CBS shapefiles into TopoJSON format.

## Project dependencies
This project relies on the Node package manager ([npm](https://www.npmjs.com/)). Install project dependencies by running:

    npm install

GDAL is required for geospatial reprojections: 
* Download and install [gdal](https://gdal.org/). 
* Add the installation directory to the `PATH` variable
* Create a new `PROJ_LIB` variable referencing the 'projlib' directory (C:\Program Files (x86)\GDAL\projlib)


## Create a map

Use the `npm run` command the run one of the following steps to create a GeoJSON file. View the results on [mapshaper](https://mapshaper.org/).


####  Gemeenten (municipalities)

    npm run map:gem


#### Wijken (districts)

* Specify the `GM_CODE` of the municipality first:
> "shape:wijk": "ogr2ogr -f GeoJSON -t_srs EPSG:4326 -where GM_CODE='GM0344' temp/wijk_2019_v1.json temp/wijk_2019_v1.shp",

* Then run


    npm run map:wijk


#### Buurten (neighbourhoods)

* Specify the `GM_CODE` of the municipality first:
> "shape:buurt": "ogr2ogr -f GeoJSON -t_srs EPSG:4326 -where GM_CODE='GM0344' temp/buurt_2019_v1.json temp/buurt_2019_v1.shp",

* Then run


    npm run map:buurt


#### Data

&copy; CBS en het Kadaster


#### Future enhancements

* Specifiy variables from command line
* Add option to not remove the downloaded shape files 
* Remove unwanted properties with ndjson (thus reducing the file size)