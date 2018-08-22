# Working with Tools

# How to add tools in a Lizmap map

## Identify and Popup tool

In QGIS desktop with a loaded map, click on Project Properties/Identify Layers
* Check the layers you want to be used in the web map for identity
* Apply and save your work
* After publishing the map on the website, the identity tool (i) appears and when you click it and use it on the map the map features will be identified.

![identify1](images/identify11.png)
![identify2](images/identify2.png)


## Print tool

* Add a map layout in QGIS desktop
* Open Lizmap window and check the Print box under the maps tool
* Apply and save your work
* The print icon appears on the website when the work is published

![print1](images/print1.png)
![print2](images/print2.png)
![print3](images/print3.png)


## Data Visualization Tool

When QGIS Project is set for web mapping or Publishing

![dataviz1](images/dataviz1.png)

a) Click on the lizmap tool to open the lizmap dialogue box
b) Click on the DataViz tab 
c) In the window that opens; choose;
i) Type of visualization (Histogram, Scatter, Piechart, Box, etc
ii) Give the vizualisation a title (with no underscores)
iii) Choose the appropriate X &Y fields  (NB: These fields are inactive unless the WFS capability tool is checked in the Project Properties under the OWS Server tab
iv) Choose the appropriate colours for the vizualisation of the appropriate values in the X &y axes
v) Select any of the descriptive statistic parameter; stddev, avg, mean, etc, if applicable
