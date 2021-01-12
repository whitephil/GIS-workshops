---
layout: default
title: 3. Visualization
parent: QGIS
has_children: false
nav_order: 3
---

# Visualizing Data in QGIS:

### Basics of Styling & Symbolology

- __Layer Properties__
  1. Double-click the counties layers
  2. View layer information under different tabs at left
  3. On the __Style tab__, click Simple fill, then, under Symbol Lyer Type, choose a pretty Fill color
  4. __Click "Apply"... You must click "Apply before clicking "OK" or changes won't take__

![Style Properties][QGIS5]

*Explore the possiblities!* QGIS has a very handy [Color Picker tool](https://docs.qgis.org/3.4/en/docs/user_manual/introduction/general_tools.html#color-selector), too.


### Create a Table Join

1. Add the Boulder_Co_Tracts.shop layer from the workshop data folder
2. Next, add the Coulbder)Co)MHHI.csv file from the workshop data folder (this is US Census income data)
3. Now we must merge the attribute table of the Bopulder census tracts layer with the CSV table of median household income.
  - Double click the Boulder_Co_Tracts layer to open layer properties
  - On the Joins tab, click the green plus button to create a new join: ![Join Button][QGIS6]
  - In the Add Vector Join dialog box, under Join layer, choose Boulder)Co)MHHI, then choose GEOID10 under both the Join and Target fields*
  - Click OK, then Apply, then OK. Open the Boulder_Co)Tracts attribute table to ensure the join occurred (right click the layer > Open Attribute Table)

&ast;To join (aka merge) a data table to a vector layer's attribute table, there must be corresponding identical fields in both tables—lucky for you, we prepared this data ahead of time!

![Joining Data][QGIS7]

### Make a Choropleth map

__Now that the income data has been added to the census tract layer, we can symbolize each tract based on median household income!__

1. Open the Boulder_Co_Tracts layer properties
2. On the Style tab, choose Graduated

![Graduated Symbology][QGIS8]

3. For Column, choose Boulder_Co_MHHI_MHHI2014
4. For Color Ramp choose a scheme that suits your fancy...
5. Click Classify
6. Click Apply!

![Choropleth Styling][QGIS9]

*You made a choropleth! Nice work!*



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
