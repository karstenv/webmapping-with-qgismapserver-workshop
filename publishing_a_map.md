# STEPS TO PUBLISHING A WEB MAP

1. QGIS DESKTOP (Client Side)

- Prepare a qgis project and do the required styling.
- Do the minimum settings in project properties and save your project in your desired file directory as a *.qgs file. Example rivers.qgs
- Major point to note is that your Qgis project should be saved in a directory relative to where your data layers are saved. The data layer should be in the same directory or a sub-directory as the *.qgs file. 
- Do minimum settings in Liz map.
 Liz Map is a qgis plugin. If it is not installed in your Qgis software, you can install it from the plugins menu. If it does not appear, go to settings and enable the "Show Also Experimental Plugins".
 This settings in Liz Map yield the *.qgis.cfg file which is saved in the same directory as the *.qgs file.
 The *qgis.cfg is a configuration file which defines which and how elements will be displayed on the web map.
 
2. Prepare a *.qgis.png file. This can be created using any graphics creation software. An examples is Ms Paint, or a simple screen shot using the snipping tool in windows.
   The name of this image needs to correspond to the qgis project file. For example, if the project file is named rivers.qgs, the image file should be named as rivers.qgs.png.
   You can other image file formats like .jpg. .jpeg, .gif e.t.c.

3. Server Side.

 Transfer the files (*.qgs, *.qgs.cfg, *.qgs.png) to the Liz map web server for publishing.

N/B - The file structure in QGIS client side should be the same as the structure in the Liz Map web server. 
    - In the event of a mismatch, the structure may be re-organized in the server side.
    - If your data is in a different directory from where the qgis project is, the Liz Map plugin will not launch successfully. In this event, you can use the Qconsolidate plugin to bring together all the layers in the same directory as the qgis project (*.qgs)
	  However, you will have to restart your qgis project with the updated data directories for Liz Map to launch successfully.

![pub_map_79](pub_map_79.png)

![pub_map_85](pub_map_85.png)

![pub_map_80](pub_map_80.png)

![pub_map_82](pub_map_82.png)

![pub_map_84](pub_map_84.png)

![pub_map_86](pub_map_86.png)

![pub_map_88](pub_map_88.png)

![pub_map_89](pub_map_89.png)
