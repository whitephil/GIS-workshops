---
layout: default
title: 2. Data Types
parent: QGIS
has_children: false
nav_order: 2
---

# Compatible Data Types & Formats:

### Supported Vector Data types:
- [Shapefile (.shp)](https://en.wikipedia.org/wiki/Shapefile)
- [GeoJSON (.geojson)](https://geojson.org/)
- [File GeoDataBase (.gdb)](https://desktop.arcgis.com/en/arcmap/10.3/manage-data/administer-file-gdbs/file-geodatabases.htm)
- [SpatialLite Layers (.sqlite, SQLite)](https://www.gaia-gis.it/fossil/libspatialite/index)
- [PostGIS Layers (PostgreSQL database)](https://postgis.net/)
- [GeoPackage (GPKG)](https://www.geopackage.org/)
- [GPX (.gpx)](https://en.wikipedia.org/wiki/GPS_Exchange_Format)
- [TopoJSON](https://github.com/topojson/topojson-specification)
- [Much more!](https://gdal.org/drivers/vector/index.html) Who knew there were this many vector types?

<img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Simple_vector_map.svg">
Vector data example

[(wikimedia)](https://upload.wikimedia.org/wikipedia/commons/3/38/Simple_vector_map.svg)

### Supported Raster Data types:
- [GeoTIFF](https://en.wikipedia.org/wiki/GeoTIFF)
- [JPEG](https://en.wikipedia.org/wiki/JPEG)
- [ASCII](https://en.wikipedia.org/wiki/ASCII) (nightmare)
- [More!](https://gdal.org/drivers/raster/index.html)

<img src="https://docs.qgis.org/testing/en/_images/raster_data_zoomed.png" alt="Raster image">

[(QGIS.org)](https://docs.qgis.org/testing/en/_images/raster_data_zoomed.png)


### Other Data Formats:
- [Web Map Service (WMS)](https://www.opengeospatial.org/standards/wms)
- [Web Feature Service (WMF)](https://www.opengeospatial.org/standards/wfs)
- [Web Coverage Service (WCS)](https://www.opengeospatial.org/standards/wcs)
- [XYZ tiles](https://openlayers.org/en/latest/examples/xyz.html)
- Loads of great basemaps via QuickMapServices Plugin

### Adding Data... *Many Ways!*
For shapefiles and typical rasters, you can use the add vector or raster buttons, or simply drag and drop from your file system or the QGIS browser panel.

![Add data using the Layer Manager Toolbar][QGIS2]

...shapefiles? That's so 90's! __Let's add a GeoPackage layer:__

1. Click the Add Vector Layer button:![Vector Button][QGIS30]
2. Navigate to your data, select the QGISworkshop.gpkg and click OK:  
![Geopackage dialog][QGIS31]  

3. Next, choose the layer you want to add and click OK:  
![Add gpkg layer][QGIS32]  

__You're done!__  

*Tip:* You can also add data straight from the Browser by just dragging and dropping:  
![Add from browser][QGIS33]




[QGIS0]: img/QGIS0.png "QGIS logo."
[QGIS1]: img/QGIS1.png "The QGIS user interface."
[QGIS2]: img/QGIS2.png "There are many ways to add data using the Manage Layers Toolbar."
[QGIS3]: img/QGIS3.png "Add SpatiaLite data button."
[QGIS4]: img/QGIS4.png "Add SpatiaLite Layers dialog box."
[QGIS5]: img/QGIS5.png "The Style tab on the Layer Properties window."
[QGIS6]: img/QGIS6.png "Add a join button."
[QGIS7]: img/QGIS7.png "Joining a text file to a layer's attribute table."
[QGIS8]: img/QGIS8.png "Styling a layer by graduated symbols"
[QGIS9]: img/QGIS9.png "Styling a choropleth map"
[QGIS10]: img/QGIS10.png "Adding a new Print Layout."
[QGIS11]: img/QGIS11.png "The Print Layout interface."
[QGIS12]: img/QGIS12.png "Useful Print Layout tools."
[QGIS13]: img/QGIS13.png "Print Layout item properties."
[QGIS14]: img/QGIS14.png "Plugin Menu"
[QGIS15]: img/QGIS15.png "Plugin Repository"
[QGIS16]: img/QGIS16.png "Vector tools"
[QGIS17]: img/QGIS17.png "Raster tools"
[QGIS18]: img/QGIS18.png "Toolbox button"
[QGIS19]: img/QGIS19.png "The Toolbox"
[QGIS20]: img/QGIS20.png "Points in Polygon"
[QGIS21]: img/QGIS21.png "Count Points in Polygon"
[QGIS22]: img/QGIS22.png "Points in Poly dialog"
[QGIS23]: img/QGIS23.png "Raster Analysis Menu"
[QGIS24]: img/QGIS24.png "Hillshade options"
[QGIS25]: img/QGIS25.png "Hillshade result"
[QGIS26]: img/QGIS26.png "Pretty map"
[QGIS27]: img/QGIS27.png "New Layout Button"
[QGIS28]: img/QGIS28.png "Use this tool to adjust the map within the frame"
[QGIS29]: img/QGIS29.png "Map layout export tools"
[QGIS30]: img/QGIS30.png "Add vector layer button"
[QGIS31]: img/QGIS31.png "add gpkg"
[QGIS32]: img/QGIS32.png "add gpkg layer"
[QGIS33]: img/QGIS33.png "add by drag & drop"
[VECTOR]: https://upload.wikimedia.org/wikipedia/commons/3/38/Simple_vector_map.svg "Source: wikimedia"
