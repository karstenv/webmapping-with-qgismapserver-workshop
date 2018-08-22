# Web GIS Workshop Materials

## Table of Content

[Using QGIS - QGIS Server - Lizmap Client](#using-qgis---qgis-server---lizmap-client)

[Server Prerequisites](#server-prerequisites)

[Installation Documentation](#installation-documentation)

[Troubleshooting Installation](#troubleshooting-installation)

[Working with Lizmap Client](#working-with-lizmap-client)

[Adding tools to Lizmap based web maps](tools.md)

[Adding and working with Data View](dataview.md)

[Minimum Configuration Settings for a Lizmap based Web Map](min_settings.md)

[Steps for publishing a web map via Lizmap](publishing_map.md)

[Tips and tricks](notes.md)

[Troubleshooting, debugging no show maps](troubleshooting.md)



## Using QGIS - QGIS Server - Lizmap Client

* QGIS Desktop

The Lizmap (python) Plug-in needs to be installed in order to create Lizmap configuration files (*.cfg) for a web map. This file is a text file that the Lizmap-Client on the Server will read in order to dynamically create the Web Map (in addition to the QGIS project file (*.qgs). 

* Lizmap Client

This is a software that is installed on the Server and is based on a collection of PHP scripts. Having configured relevant settings in the QGIS project (saved to the map document *.qgs) in connection with the lizmap configuration file (*.cfg) these scripts can dynamically create the Web Map. The viasualisation in a web browser (aka the web viewer) of the Lizmap Client is based on the JavaScript library Openlayers 2.13.


* QGIS Server

Is the rendering engine that delivers for example the map images, map legends, and attribute feature information defined in thr QGIS desktop map document (*.qgs). It  acts as WMS / WFS server. Each map layer is served as a Web Map Service WMS (and/or Web feature Service - WFS) according to the map document settings and can deliver teh respective information via HHTP request to teh map viewer (WMS = images , such as png or jpeg, WFS = the attributes and geometries as vectors ).


## Server Prerequisites

[back to page top](#web-gis-workshop-materials)

* Software that need to be installed
   * HTTP Server e.g. Apache2
   * PHP (version 5 or 7)
   * QGIS Server (and related libraries)
   
The version of the Desktop QGIS and the QGIS Server needs to be the same to avoid unexpected (or even not working) results. On Ubuntu for QGIS Server 2.18 LTS the minimum requirement operating system version is [Ubuntu 16 (Xenial Xerus)](http://releases.ubuntu.com/16.04)
 
### Installation Documentation

[back to page top](#web-gis-workshop-materials)

[QGIS Server Installation](https://docs.3liz.com/en/install/windows.html#qgis-server-installation)

[Lizmap Installation](https://docs.3liz.com/en/install/windows.html)

### Troubleshooting Installation

To be added.

## Working with Lizmap Client

[back to page top](#web-gis-workshop-materials)

The welcome page of the Lizmap Client based webpage is a gallery of all interactive maps residing/ published in one Lizmap repository displaying meta information and screen shots of the maps along with live links to the maps.

![Lizmap Web map gallery](/images/lizmap_client_gallery.png)
