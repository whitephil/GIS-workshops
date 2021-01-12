---
layout: default
title: 4. Analysis
parent: QGIS
has_children: false
nav_order: 4
---

# Intro to Analysis Tools:

### Analysis Tools and Toolboxes

Many of the most frequently used tools are available from the main menu under Vector and Raster:

__Vector tools:__

![Vector Menu][QGIS16]

__Raster tools:__

![Raster Menu][QGIS17]

But many more tools are available in the Processing Toolbox. To open the Processing Toolbox, click the button that looks like a cogwheel in the menu:
![Gear icon][QGIS18]

Here you can view all the available tools, your processing history, and recently used tools:

![ToolBox][QGIS19]

An advantage to using QGIS is that other open source geospatial libraries are available as tools as well, such as GRASS or GDAL processing tools.


## Example Vector Analysis

### Count Points In Polygon (aka Summarize Within or Spatial Join)

Let's say you wanted to know how many points fall within a polygon. For example, hospitals within a search radius, or McDonalds per county. We can achieve this using the __Count Points In Polygon__ tool.

In this example, we'll sum the number of cities within counties.

![CitiesInCounties][QGIS20]

- Under Vector, choose Analysis > Count Points In Polygon:

![PointsInPolygon][QGIS21]

- In the Count Points in Polygon dialog box, choose counties under Polygons and cities under points. In this example, leave all other options as default. This will produce a temporary, "scratch" layer that can be made permanent later.

![PointsInPolyDialog][QGIS22]

*Note how fast that process ran!! Better than ArcGIS, for sure!*

- The tool produced a new temporary counties layer named "Count". Right click on the new "Count" layer to open the attribute table. You will find a new data field containing the sum of cities within each county. *Easy!*

To make this layer permanent, right click on the layer and select Make Permanent.

## Example Raster Analysis

### Create a Quick Hillshade Layers

- Add the Flatirons_DEM_1m geotiff file from the workshop data folder.

- In the Raster menu, choose Analysis > Hillshade. Note this is a GDAL tool.

![Hillshade][QGIS23]

-In the Hillshade dialog box, you can leave all parameters as default (but feel free to tinker with azimuth and altitude settings for different effects).

![HillshadeTool][QGIS24]

You're resulting hillshade raster will be added to the map. To make the hillshade a permanent image, right click the layer and choose Export > Save As...

Spend a few minutes tinkering with hillshade parameters as well as styling of the original DEM (color ramps, transparency, etc.) to make something pleasing.

![HillshadeLayer][QGIS25]

*__Pro Tip:__* For folks familiar with ArcGIS and looking for equivalent tools, often the best strategy is to search for the tool name as you know it in ArcGIS along with "QGIS" [Example: "Summary Statistics QGIS"]. This will usually yield good results. If you can't find a tool for a particular task in the QGIS tools, check other tool libraries like GRASS, GDAL, or SAGA, or search the Plugin Repository.









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
[VECTOR]: https://upload.wikimedia.org/wikipedia/commons/3/38/Simple_vector_map.svg "Source: wikimedia"
