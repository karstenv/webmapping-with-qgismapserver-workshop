# Troubleshooting, debugging no show maps

[go back to main page](README.md)

## How to fix no show maps

1. Ensure that the right .qgs and .qgs.cfg files are on the right directory in the server and in the clients side. 
   a) q consolidate plugin help in saving the .qgs.cfg and .qgs files in one correct folder where they are needed. 
   b) Go to Plugin_QConsolidate_QConsolidate in QGIS desktop to launch the plugin. 
   c) Browse to the output directory to consolidate your files 

2. Client be keen not to load duplicate .qgs and .qgs.cfg files that aren't in the server

3. When you upload your configuration file *cfg, *.png file and *.qgs file and your map does not appear on the webpage, although the legend appears, it means there is a problem with the CRS
	- to fix this go to Project - Project Properties - CRS and select the correct Coordinate Reference System e.g. WGS84/Pseudo Mercator (EPSG  3857)if using OSM or Google as Baselayers.  - Then click  Apply followed by OK.(CRS 01)
	- Similarly got to Project - Project Properties - OWS Server. Under the WMS capabilities activate the CRS Restrictions and Advertised Extents. Select the Used CRS and Use Current Canvas extent- Then click  Apply followed by OK.(OWS 01)
	- Finally carry out the Lizmap Settings - Web - Lizmap - Lizmap - Map Options - Initial Map Extent - select Set From Project Properties. Click Apply then Close (Lizmap 01)
	- Copy the *.qgs and *.cfg files to the server then refresh the webpage and your map will be displayed correctly.

4. All the shapefile and other source data in the QGIS project should be present in the server. Missing files won't e displayed and so if you all the files are missing nothing will displayed in the browser.

5. The path of the projects are case sensitive. You should also not use spaces. You can opt to combining the words. The names of the project from the client should be similar to that on the server considering the cases.

6. There is a restriction on the length of the QGIS project file. Avoid using names longer than 20 characters in order to make the web GIS project display.
