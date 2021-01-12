---
layout: default
title: 3. Styling
parent: ArcGIS Pro
has_children: false
nav_order: 3
---

# Styling and Symbolizing Data:

### Quick, single-symbol styling:  

1. Start by double-clicking a layer's symbol.  
2. Use the Symbol Selector to change a layer's appearance:  

![Symbol Selector][ARCPRO10]

### Advanced:  

1. Add the Counties layer from the workshop geodatabase.  
2. Select the Counties Layer  
3. On the Appearance tab, select an option for styling, such as by unique values or graduated colors  

    ![Appearance Tab][ARCPRO11]  

4. Under Fields, select Pop_Dens from the Value menu (this corresponds with the Pop_Dens field in the attribute table)  
5. Ta da! You've made a choropleth map that shows population density. Hurrah!  

    ![Symbology Tab][ARCPRO12]  

### Changing the displayed projection  

You may want to change the projection of your map for stylistic purposes  

1. Right click on Map in the Contents pane & scroll to properties  
2. Click the Coordinate Systems tab
3. Search or scroll to find an appropriate projection for Colorado  

*Note: this only changes the display of your map, not the underlying coordinate system of your data layers*

![Snappy Map][ARCPRO13]


[ARCPRO0]: img/esrilogo.png "Esri logo"
[ARCPRO1]: img/ArcGIS1.jpg "start screen"
[ARCPRO2]: img/ArcGIS2.jpg "Name & save  your project"
[ARCPRO3]: img/ArcGIS3.jpg "Connect to folders or geodatabases"
[ARCPRO4]: img/ArcGIS4.jpg "Insert a map"
[ARCPRO5]: img/ArcGIS5.jpg "map interface"
[ARCPRO6]: img/ArcGIS6.jpg "add data button"
[ARCPRO7]: img/ArcGIS7.jpg "add from catalog"
[ARCPRO8]: img/ArcGIS8.jpg "right click on a layer"
[ARCPRO9]: img/ArcGIS9.jpg "the attribute table"
[ARCPRO10]: img/ArcGIS10.jpg "symbol selector"
[ARCPRO11]: img/ArcGIS11.jpg "appearance tab"
[ARCPRO12]: img/ArcGIS12.jpg "symbology tab"
[ARCPRO13]: img/ArcGIS13.jpg "snappy looking map"
