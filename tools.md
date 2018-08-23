# Working with Tools

[go back to main page](README.md)

## Adding Tools to Lizmap interactive maps

[How to add an overview Map](#how-to-add-an-overview-map)

[Print Tool](#print-tool) 

[Data Vizualization Tool](#data-visualization-tool)

[Locate by Layer Tool](#locate-by-layer) 

[Adding Base Layers](#adding-base-layers) 

[Adding Measure Tool](#adding-measure-tool) 

[Adding and working with Data View](dataview.md)

# How to add tools in a Lizmap map

## Identify and Popup tool

[back to page top](#working-with-tools)

In QGIS desktop with a loaded map, click on Project Properties/Identify Layers
* Check the layers you want to be used in the web map for identity
* Apply and save your work
* After publishing the map on the website, the identity tool (i) appears and when you click it and use it on the map the map features will be identified.

![identify1](images/identify11.png)
![identify2](images/identify2.png)


## How to add an overview Map

[back to page top](#working-with-tools)

To add an overview map in a Lizmap map, one should:

· Create an independent group of layer  in the QGIS project layer panel called Overview (with the 1st letter capitalized)

· Add layers, for example a layer of Kenya or Counties, a lighter terrain base layer, etc.
All layers and groups in the Overview group will not be shown in the lizmaps map legend.

They are drawn only in the Overview map.

![overviewscreenshot1](images/overviewscreenshot1.png)

![overviewscreenshot2](images/overviewscreenshot2.png)

![overviewscreenshot3](images/overviewscreenshot3.png)

## Print tool

[back to page top](#working-with-tools)

* Add a map layout in QGIS desktop
* Open Lizmap window and check the Print box under the maps tool
* Apply and save your work
* The print icon appears on the website when the work is published

![print1](images/print1.png)
![print2](images/print2.png)
![print3](images/print3.png)


## Data Visualization Tool

[back to page top](#working-with-tools)

When QGIS Project is set for web mapping or Publishing

![dataviz1](images/dataviz1.png)

a) Click on the lizmap tool to open the lizmap dialogue box
b) Click on the DataViz tab 
c) In the window that opens choose:

   i) Type of visualization (Histogram, Scatter, Piechart, Box, etc

   ii) Give the vizualisation a title (with no underscores)

   iii) Choose the appropriate X &Y fields  (NB: These fields are inactive unless the WFS capability tool is checked in the Project Properties under the OWS Server tab

   iv) Choose the appropriate colours for the vizualisation of the appropriate values in the X &y axes

   v) Select any of the descriptive statistic parameter; stddev, avg, mean, etc, if applicable

__Examples of Bar Plots__

![dataviz2](images/dataviz2.png)

[Kenya Protected Areas - Live Map](http://ws2018.terragis.net/lm33/index.php/view/map/?repository=ccrpws&project=kenya&layers=000000000BTTTTFT&bbox=1918852.942147%2C-850291.240807%2C6216448.419855%2C905925.920828&crs=EPSG%3A3857&layerStyles=Major_Towns%3Atown%20blue%3BProtected_Areas%3A%3BDistrict_Boundaries%3A)

__Bar Plot__

![dataviz3](images/dataviz3.png)

__Settings in Lizmap Window__

![dataviz4](images/dataviz4.png)



## Locate by Layer

[back to page top](#working-with-tools)

### Documentation on enabling/activating the Locate by layer and Tooltip 

1.	To Enable locate by layer 
As a prerequisite to be done on QGIS:, the corresponding check box of the WFS capabilities in the OWS Server tab of the Project Properties window must be checked. Otherwise the layers will not be able to be added to the list
=To enable the WFS capabilities, 
1)	open QGIS project Properties
2)	Click on OWS server tab (from the dialog box that pops up),
3)	Under the WFS capabilities click  check  the corresponding  boxes to the  right of  each layer name
See picture: Prerequisite_QGIS_steps 

### Steps on Lizmap plugin

When some selected layers are added to the tool Locate by layer, a drop down list of the layers appears on the Lizmap. This enables to select one name in this list zoom to the selected layer and  the geometry is displayed (if display geometry is checked) 
Make sure that Lizamap plugin is installed and activated 
1.	From QGIS Web menu, open Lizamap plugin
See picture: Enabling Lizamp plugin
2.	Click on locate by layer tab
3.	Click on the layers dropdown list, 
4.	Select the layer and the corresponding field name under Display field drop down list.
5.	For each selected  layer, click add layer button to populate the table above it
6.	Click on display geometry check box (optional)
7.	To remove layer, select and  click remove layer button
8.	Click Apply
See Picture: locate by layer steps on lizmap
2.	Tooltips

For the prerequisites, see Prerequisite_QGIS_steps

1.	To enable Tooltips on Lizmap plugin, see picture: Enabling Lizamp plugin
2.	Click on Tooltips tab 
3.	From the layers dropdown list, select the layer to display
4.	For each selected  layer, click add layer button to populate the table above it
5.	To remove layer, select and  click remove layer button
6.	Click on display geometry check box (optional)
7.	Click Apply


![Enabling Lizamp plugin](images/Enabling_Lizamp_plugin.png)

![locate by layer steps lizmap](images/locate_by_layer_steps_on_lizmap.png)

![Prerequisit_QGIS_steps](images/Prerequisit_QGIS_steps.png)

![Tooltip_ steps_on_Lizmap_plugin](images/Tooltip_steps_on_Lizmap_plugin.png)

See picture: Tooltip_ steps_on_Lizmap_plugin

### Adding Base Layers

[back to page top](#working-with-tools)

To add base map layers to the map, one needs to have the qgs project
On the lizmap plugin, select the baselayers tab.

Under the baselayers tab, Base maps from different sources are available. These are: 
Open Street Map – OSM Mapnik and OSM Stamen Toner
Bing Maps – Streets, Satellite, Hybrid and Terrain.
Google Maps - Streets, Satellite and Hybrid.  
IGN (France) – Plan, Satellite, Streets and Cadastre. 

AVAILABLE BASE LAYERS
In order to access the Google, Bing and IGN maps, you will need an api-key (application programming interface - key). 
This key gives access to a single map that allows the user to load base maps from these sources. 
As for the Open Street Maps layers, an api-key is not required.

The base layers are selected as shown in the figure below.
After selecting the required basemap(s), apply and save edits on the qgs project. 

![Basemap1](images/Basemap1.png)

![Basemap2](images/Basemap2.png)

### Adding Measure Tool

[back to page top](#working-with-tools)

On the Lizmap plugin, select the Map options tab 
Under the map tools select the measure tool which enables measurement in the map (Length, Area and Perimeter)
Apply and close the plugin 
Save edits in qgs project.

![Measure_tool](images/Measure_tool.png)

