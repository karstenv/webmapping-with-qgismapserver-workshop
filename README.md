# Web GIS Workshop Materials

## Using QGIS - QGIS Server - Lizmap Client

* QGIS Desktop

Need to have Lizmap (python) Plug-in installed to create a configuration file (*.cfg). This file is a text file that the Lizmap-Client on the Server will read in order to dynamically create the Web Map.

Lizmap Client

This is a software that is installed on the Server and is based on a collection of PHP scripts. Having configured relevant settings in teh QGIS project (savbed to the map document *.qgs) in connection with the lizmap configuration file (*.cfg) dynamically create the Web Map.


QGIS Server



## Server Prerequisites

* Software that need to be installed
   * HTTP Server e.g. Apache2
   * PHP (version 5 or 7)
   * QGIS Server (and related libraries)
   
   The version of the Desktop QGIS and the QGIS Server need to be the same to avoid unexpected or even not working results. On Ubuntu for QGIS Server 2.18 LTS the minimum requirement operating system version is [Ubuntu 16 (Xenial Xerus)](http://releases.ubuntu.com/16.04)
 
### Installation Documentation 

[QGIS Server Installation](https://docs.3liz.com/en/install/windows.html#qgis-server-installation)

[Lizmap Installation](https://docs.3liz.com/en/install/windows.html)

### Trouble shooting Installation


# Working with Lizmap Client

![Lizmap Web map gallery](/images/lizmap_client_gallery.png)
