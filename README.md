# Web GIS Workshop Materials

[Live Web Maps published during the workshop](http://ws2018.terragis.net/lm33)

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

[Restrictions and prerequisites publishing a map](restrictions_prerequisites.md)


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
 
## Installation Documentation

[back to page top](#web-gis-workshop-materials)

[QGIS Server Installation](https://docs.3liz.com/en/install/windows.html#qgis-server-installation)

[Lizmap Installation](https://docs.3liz.com/en/install/windows.html)

### Troubleshooting Installation

* QGISMapserver print did not work
copied from http://www.itopen.it/qgis-server-setup-notes/

__X dependency__

The most important is probably the xorg requirement that Qt libs have when rendering to PDF, this is an undocumented requirement and the fix is not trivial.
Basically, your server needs an X server running, a fake X server like Xfvb will do (xvfb – Virtual Framebuffer ‘fake’ X server), you can easily install this package in debian/ubuntu with:

vfb needs a startup script, I’ve found a good one here: https://gist.github.com/dloman/8303932
Since a configurable display number is needed (here set to 99), I’ve adapted the script setting display to 99:

----------
    #!/bin/sh
    ### BEGIN INIT INFO
    # Provides: Xvfb
    # Required-Start: $local_fs $remote_fs
    # Required-Stop:
    # X-Start-Before:
    # Default-Start: 2 3 4 5
    # Default-Stop: 0 1 6
    # Short-Description: Loads X Virtual Frame Buffer
    ### END INIT INFO
     
    XVFB=/usr/bin/Xvfb
    XVFBARGS=":99 -screen 0 1024x768x24 -ac +extension GLX +render -noreset"
    PIDFILE=/var/run/xvfb.pid
    case "$1" in
      start)
        echo -n "Starting virtual X frame buffer: Xvfb"
        start-stop-daemon --start --quiet --pidfile $PIDFILE --make-pidfile --background --exec $XVFB -- $XVFBARGS
        echo "."
        ;;
      stop)
        echo -n "Stopping virtual X frame buffer: Xvfb"
        start-stop-daemon --stop --quiet --pidfile $PIDFILE
        echo "."
        ;;
      restart)
        $0 stop
        $0 start
        ;;
      *)
            echo "Usage: /etc/init.d/xvfb {start|stop|restart}"
            exit 1
    esac
     
    exit 0
--------------

Install it with:
    chmod +x /etc/init.d/xvfb
    update-rc.d xvfb defaults
    
then
/etc/init.d/xvfb start


in trusty as a service :

as /etc/init/xvfb.conf:

-----------------
description     "Xvfb X Server"
start on (net-device-up
    and local-filesystems
    and runlevel [2345])
stop on runlevel [016]
exec /usr/bin/Xvfb :99 -screen 0 1024x768x24

---------------
service xvfb start

used the info from https://gist.github.com/jterrace/2911875
with these settings below
      
      /etc/init.d/xvfb start
      export DISPLAY=:0

Fast CGI needs an environment variable DISPLAY having the same display number (99), I’ve adapted the fcgid configuration accordingly:
    $ cat /etc/apache2/mods-enabled/fcgid.conf 
     
      AddHandler    fcgid-script .fcgi
      FcgidConnectTimeout 20
      # Pass display number to QGIS MapServer instances
      FcgidInitialEnv DISPLAY ":99"


## Working with Lizmap Client

[back to page top](#web-gis-workshop-materials)

The welcome page of the Lizmap Client based webpage is a gallery of all interactive maps residing/ published in one Lizmap repository displaying meta information and screen shots of the maps along with live links to the maps.

![Lizmap Web map gallery](/images/lizmap_client_gallery.png)
