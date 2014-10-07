Welcome! This repo exists to help me learn how to use GitHub, to better document my work, and share what I know and have learned with other interested folks.  Right now, my primary project is making 60+ maps for a new book. Thanks for visiting.

***

### List of OpenStreetMap (OSM) tools     
A summary of the different tools I use for querying and downloading OSM data.  

##### OpenStreetMap (OSM) and Humanitarian OpenStreetMap Team (HOT)
I think OSM is an incredibly valuable tool, and I think everyone should know about it. Here's how you can get started.  
1. Start with [MapGive](http://wwww.mapgive.state.gov), and wathc the [Why you should map](http://mapgive.state.gov/why-map/) video.  Follow the instructions on the [Learn to map](http://mapgive.state.gov/learn-to-map/) webpage to create an OpenStreetMap account.  
2.

##### Data Export  
   * [GEOFABRIK downloads](http://download.geofabrik.de/): No account needed. Data for download is Updated roughly once every 24hrs. Download zipped .shp and .osm files based on a given country or administrative units. 
   * [Mapzen](https://mapzen.com/metro-extracts/): No account needed.  Data refreshed weekly.  Coverage is for approximately 240 major cities in the world.  Download zipped .osm, .shp, and .geoJSON files.
   * [WeoGeo.com](http://www.weogeo.com/data/OpenStreetMap_Data.html): Free account required. Data for download is refreshed  roughly once every month. Define a custom AOI and download in a vareity of different common geospatial data formats.   
   * [Overpass Turbo](http://overpass-turbo.eu/): No account needed.  Use Query Wizard to select specific features from current OSM data server for a user defined AOI.  Export data into any number of common geospatial data formats (No direct export to shapefil option). Data downloaded is from current OSM database. [Example Tutorial](/Tutorials/OSM-Export_Tools.md).  
   * [bbox finder](http://bboxfinder.com/): No account needed.  This handy tool allows you to quickly get the Lat/Long values for any user defined AOI in the web-mercator projection.  
   * [HOT Exports](http://export.hotosm.org/): Free account required. Users can select their own AOI. Download only the features/tags you want by creating your own download preset, or choose from a tag presets.  Data downloaded is from current OSM database. Queries can be saved to the users account, and can be rerun whenever refreshed data is desired. A significant limitation to this tool is that it does not support exports for all parts of the globe.  See the [OSM Wiki- HOT Export](http://wiki.openstreetmap.org/wiki/HOT_Exports) page for a map of areas covered by this tool, and for more information on how to use it.

##### OSM database Visualization and summary statistic tools  
   * [Taginfo](http://taginfo.openstreetmap.org/): See word cloud of most popular OSM tag Keys, and invidual statistics for each tag used.  
   * [Neis One!](http://neis-one.org/): The personal website of Pascal Neis, there are lots of great webtools for tracking and analyzing edits to OSM by location, individual user name, and change sets. [How did you contributed to OpenStreetMap](http://hdyc.neis-one.org/) generates a custom activity report for a specific username. [Your OSM HeatMap](http://yosmhm.neis-one.org/) generates a custom heat map based on aggregating the location of a single users edits globally.   [Who's around me](http://resultmaps.neis-one.org/oooc) shows the location of other users based on a mean location of their edits for a specific point in time, or averages over 6 months.  
   * [ito! OSM Mapper](http://www.itoworld.com/static/openstreetmap_tools/osm_mapper.html) Account required.  Generate maps and reports of editing activity by user, by tag, or by time for a user defined area.  Maps and tables are exportable in several easily accessible formats.
  
### Adobe Illustrator Tricks
Most all of my maps start in ArcGIS but get exported to Adobe Illustrator for further refinement, particularly for laying out type, styling fill patterns that incorporate shading, and for detailed linework. Recently I've been wanting to replicate some of the great variation in linework which Dave Imus has used in his [Essential Geography of the United States](http://www.imusgeographics.com/listitems_63/usa-maps) wall map.

Tips and Tools that I have found useful include:
   * [Exporting an ArcGIS Map Document to Adobe Illustrator](/Tutorials/ArcGIS-Map-Export-to-AdobeIllustrator/ArcGIS-Map-Export-to-AdobeIllustrator.md): My own list of tips for preparing data in ArcGIS for export to Adobe Illustrator  
   * [Swiss Cartographic and Information Institute AI plugins](http://www.ika.ethz.ch/plugins/index.html): Note that these plugins only work on a Windows OS, not Mac. Although the download pages are in German, using Google Translate I was able to follow along and install the plugins in the right location. There appears to be great documentation for each of the plugins, however it is all written in German.  Fortunately, over on the [CartoTalk](http://www.cartotalk.com/) discussion forum, some kind folks have written a [very useful document in English](http://www.cartotalk.com/index.php?showtopic=4070) of the basic tool functions, and posted it as a MS Word document (see reply #15 by "sitesatlas" posted on 14 July 2009, at 04:34 PM).  
   * [Cave Cartography Introduction to Cartography with Illustrator](http://cavecartography.com/Survey%20Training.htm): This website has a series of powerpoint presentations which explain how to create a basic pattern in Illustrator, and convert it to a pattern brush style.  Specifcially, check out the "[Introduction to Illustrator - Lines, Scan and Walls](http://cavecartography.com/Intro%20to%20Illus%20-%20Lines,%20Scan%20and%20Walls.ppt)" powerpoint.  Note that the screencaptures are based on pre-CS5 version of Adobe Illustrator, but everything else seems to still apply.  
   * [John's scripts for Adobe Illustrator](http://www.wundes.com/JS4AI/) (h/t @NVKelso):  I have not had a chance to explore these yet, but look forward to.   

### Working with [Natural Earth Data](http://www.naturalearthdata.com/) in ArcMap

* **Creating custom shaded relief color ramps**  
   For most cartographic production projects, the default color ramps in ArcMap really don't work well.  I encountered this problem when I was working on a map to be printed in color, so I wanted a color ramp which went from light to dark like a greyscale ramp, but in a different hue. [Here's how...](/Tutorials/Custom-Color-Ramp-ArcMap/Custom-Color-Ramp-ArcMap.md)

* **Styling scale-dependent labels using ScaleRank Attributes**  
   Natural Earth vector and point files contain a lot of great data, and for most maps you are going to want to label _some_ of this data, but likely not _all_ of it- or at least not all of it the same way.  Each vector shapefile contains a few different attribute fields that helps you to select and style features and their labels to create a more coherent and appealing visual hierarchy. [Here's how...](/Tutorials/Styling-Natural-Earth-Labels/Styling-Natural-Earth-Labels.md)

### Using [Blender](http://www.blender.org/) to produce beautiful shaded relief layers
Daniel Huffman [(@pinkogeograp)](https://twitter.com/pinakographos) has done a lot of work in developing an easy to follow workflow for creating beautiful shaded relief layers using the open source 3D animation software called Blender. In his blog post [Blending my way to Relief](http://somethingaboutmaps.wordpress.com/2013/07/02/blending-my-way-to-relief/) he explains why he finds Blender produced shaded relief's to be more appealing than those produced in ArcMap.  Subsequently, he has produced a 6-part [YouTube video series](https://www.youtube.com/watch?v=6l9e5KM9CUU) where he demonstrates the step-by-step process from importing a DEM to exporting the final product.

I followed along with his tutorial the first time, but found that when I was trying to reproduce the process on my own, I frequently had to go back to the videos. To make it easier to understand the workflow and quickly reference the different steps, I've created a [GoogleDoc spreadsheet](https://docs.google.com/spreadsheets/d/11HHMdKawdbXNkkxWdW82-HgHE2k3Tojg7P_X75ojb50/edit?usp=sharing) where I tried to transcribe each video, and sequentially number the steps within the workflow.

### Blending Shaded Relief data with Adobe Photoshop  
Draping imagery or vector artwork over shaded relief terrain data is a common way of trying to convey physiography to map users.  The simplest method many of us are taught is simply to adjust the transparency of your imagery layer.  However, when doing so, you also end up muting the texture of your terrain data.  To retain the natural variation in texture which the shaded relief data provides, it is necessary to use a more sophisticated blending method, and Adobe Photoshop provides the tools to do this.  [Here's how...](/Tutorials/Blending-Shaded-Relief-Photoshop/Blending-Shaded-Relief-Photoshop.md)

### Using ArcGIS Data Driven Pages   
The print cartography project I'm working on requires making about 60 unique maps.  My workflow is to organize and layout the map data in ArcGIS, then export the data from ArcGIS as an Adobe Illustrator file (.ai), and adjusting type and applying other styling in Adobe Illustrator.  Many of the maps will have a raster base data, so the raster files have to exported from ArcGIS separately as a TIFF file.  I'm exploring [ArcGIS's Data Driven Pages] (http://resources.arcgis.com/en/help/main/10.1/index.html#//00s90000003n000000) tools to see if they I can automate the export process in python with the [arcpy.mapping](http://resources.arcgis.com/en/help/main/10.1/index.html#//00s30000000n000000) module.  [Here's what I'm trying...](/Tutorials/Data-Driven-Pages/DataDrivenPagesExperiment.md)

### ArcGIS Python Scripts
Python is supposed to make repetative tasks quick and painless in ArcGIS.  I've started collecting code snippets and scripts I have used, and [putting them here...](/ArcGIS-Python-Code/ArcGIS-Python-Code.md)
