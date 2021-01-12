---
layout: default
title: Glossary
nav_order: 9
---
# Glossary  

### A non-exhaustive  list.  

**ArcGIS** –  ArcGIS is a suite of GIS applications designed and licensed by Esri. ArcGIS for desktop includes the applications ArcMap, ArcCatalog, ArcScene, and ArcGlobe. ArcGIS Pro is the latest ArcGIS software from Esri.

**ArcGIS Online** – Esri's online GIS tool. Great for creating web-maps and sharing them with others. Has ready-made apps that you can use to feature your web-maps. Does not have the same capabilities of ArcMap or Pro, but seems to gain functionality all the time.

**ArcGIS Pro** – A new addition to Esri's desktop GIS offerings. Pro is kind of a step between ArcMap and ArcGIS Online. Much of the functionality of ArcMap has been carried into ArcGIS Pro.

**ArcMap** – The primary GIS application available in the ArcGIS software suite by Esri. ArcMap is the go to software for GIS professionals, though the line between ArcMap and ArcGIS Pro is getting fuzzier.

**Coordinate System (CRS)** – A reference framework consisting of a set of points, lines, and/or surfaces, and a set of rules, used to define the positions of points in space in either two or three dimensions. Cartesian coordinate system and the geographic coordinate system used on the earth's surface are common examples of coordinate systems.*

**Datum** – The reference specifications of a measurement system, usually a system of coordinate positions on a surface (a horizontal datum) or heights above or below a surface (a vertical datum).*

**DEM** – Digital Elevation Model. The representation of continuous elevation values over a topographic surface by a regular array of z-values, referenced to a common datum. DEMs are typical used to represent terrain relief.*

**ESRI** – Esri is the industry leader in GIS. Esri standa for Environmental Systems Research Institute, but most just refer to it as "Esri." Esri is headquartered in Redlands, CA.

**Geocode** – Or Geocoding. A GIS operation for placing points on a map based on street addresses. You can also plot x,y (lat, long) data.

**GeoDatabase** – A database or file structure used primarily to store, query, and manipulate spatial data. Geodatabases store geometry, a spatial reference system, attributes, and behavioral use data.* Geodatabases have become the standard file storage format in ArcGIS. Allows you to store many different data in one packaged file, rather than many shapefiles & associated files in a simple folder. Certain operations seem to run more smoothly when your data is packaged in a geodatabase.

**GeoJSON** – GeoJSON is an open vector data format that is essentially a "spatialized" version of JavaScript Object Notation (JSON). GeoJSON is a popular format for displaying vector data on web maps. A benefit of GeoJSON is that all of the data is stored in one file (as opposed to a shapefile). A drawback is that large GeoJSON layers can perform slowly.

**GeoPackage** – GeoPackage is an open source alternative to the GeoDatabase. It is based on SQLite. It is increasingly popular among QGIS users.

**GeoPandas** – GeoPandas is a Python package and extension of the popular data science package Pandas.

**Georeference** – An operation in which an image (such as an aerial photo) is aligned to a known coordinate system so it can be viewed and analyzed with other spatial data.* Typically, georeferencing involves overlaying an image above a basemap and aligning known points on the image with the basemap (such as an easily identified street intersection).

**GIS** - (Geographic Information System) An integrated collection of computer software and data used to view and manage information about geographic places, analyze spatial relationships, and model spatial processes.*

**GIS "Lite"** – A commonly used and broad term describing GIS tools that are less full-featured and have a lower barrier to entry. Typically, GIS Lite tools are web-based, and require little advanced training. Examples: Google Earth, Google Maps, ArcGIS Online (although ArcOnline is becoming more fully featured), other online mapping tools.

**KML** – Or KMZ. The KML is Google's standard file format for spatial data. KML stands for Keyhole Markup Language. KMZ is the zipped version. KML/Zs are handy for web-GIS and can be used in Google Earth, Google Maps, Google Fusion Tables. You can convert KML/Z to Shapefile as well.

**Layer** – The visual representation of a geographic dataset in any digital map environment. Conceptually, a layer is a slice or stradum of the geographic reality in a particular area, and is more or less equivalent to a legend item on a paper map.¹ When you add data (such as a shapefile) to a GIS application it is represented as a layer on a map. [See these images](https://www.google.com/search?q=gis+layers&espv=2&biw=1431&bih=831&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjJw5vavafJAhUQ2GMKHUm4AeQQ_AUIBigB){:target="_blank"}.

**Leaflet** – An open source JavaScript package for creating web maps. Leaflet is a very popular tool for displaying GIS data on the web.

**MapBox** - Another free (though not quite open source) JavaScript library for generating webmaps. Very easy to use and flexible.

**Map Document** – Or .mxd file. The filetype for saving your workspace in ArcMap. My friend [Mark Thomas](https://guides.library.duke.edu/arcgis/arcgis_formats){:target="_blank"} says it best: "Sort of a bookmark file, which tells the program which layers and tables are being used for the particular map and how they are being symbolized.  All the files referred to that are being used to build the layers and store the data must be accessible."

**Project File** – Or .aprx file. The standard filetype for saving projects in ArcGIS Pro.

**Projection** – A method by which the curved surface of the earth is portrayed on a flat surface. Every map projection distorts distance, area, shape, direction, or some combination thereof.*

**Python** – An open source, general purpose programming language. Python is very popular among GIS users due to a variety of both free (PyQGIS, GDAL, GeoPandas, GeoPy, many more) and proprietary (ArcPy, ArcGIS API for Python) GIS packages.

**QGIS** – A free and open-source (and fully featured) GIS platform. An alternative to ArcGIS. Also works on Macs.

**R** – The R project for statistical computing is a very popular open source statistical package. There are several excellent, highly developed R packages for working with geospatial data (rspatial, rgdal, sf, tmap, raster).

**Raster Data** – A spatial data model that defines space as an array of equally sized cells arranged in rows and columns.* Think of these cells as pixels.

**Shapefile** – Or .shp. This is the most common filetype for geographic or spatial data, and is the most frequently used filetype in ArcGIS. Shapefiles come to you as points (placemarks, cities), lines (roads, rivers), or polygons (state boundaries, counties, zones). Free available shapefiles of all sorts of stuff are freely available on the web.

**Topology** – The spatial relationships between connecting or adjacent features in a geographic data layer (for example, arcs, nodes, polygons, and points). Topological relationships are used for spatial modeling operations that do not require coordinate information.* Think of it as the relationships between things that are adjacent or connected to one another.

**Topography** – The study and mapping of land surfaces, including relief (relative positions and elevations) and the position of natural and constructed features.* USGS Topo Maps are a prime example.

**Vector Data** – A coordinate-based data model that represents geographic features as points, lines, and polygons.*  

*Wade, T., & Sommer, S. (2006). A to Z GIS: An illustrated dictionary of geographic information systems. Redlands, Calif: ESRI Press.

[Octocat]: https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Font_Awesome_5_brands_github.svg/232px-Font_Awesome_5_brands_github.svg.png "GitHub logo."
