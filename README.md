Welcome to my Git-It-Done repo! This repo exists to help me learn how to use GitHub, to better document my work, and share what I know and have learned with other interested folks.  Right now, my primary project is making 60+ maps for a new book. Thanks for visiting.

***

### Working with [Natural Earth Data](http://www.naturalearthdata.com/) in ArcMap

* **Creating custom shaded relief color ramps**  
   For most cartographic production projects, the default color ramps in ArcMap really don't work well.  I encountered this problem when I was working on a map to be printed in color, so I wanted a color ramp which went from light to dark like a greyscale ramp, but in a different hue. [Here's how...](/Tutorials/Custom-Color-Ramp-ArcMap/Custom-Color-Ramp-ArcMap.md)

* **Styling scale-dependent labels using ScaleRank Attributes**  
   Natural Earth vector and point files contain a lot of great data, and for most maps you are going to want to label _some_ of this data, but likely not _all_ of it- or at least not all of it the same way.  Each vector shapefile contains a few different attribute fields that helps you to select and style features and their labels to create a more coherent and appealing visual hierarchy. [Here's how...](/Tutorials/Styling-Natural-Earth-Labels/Styling-Natural-Earth-Labels.md)

### Using [Blender](http://www.blender.org/) to produce beautiful shaded relief layers
Daniel Huffman [(@pinkogeograp)](https://twitter.com/pinakographos) has done a lot of work in developing an easy to follow workflow for creating beautiful shaded relief layers using the open source 3D animation software called Blender. In his blog post [Blending my way to Relief](http://somethingaboutmaps.wordpress.com/2013/07/02/blending-my-way-to-relief/) he explains why he finds Blender produced shaded relief's to be more appealing than those produced in ArcMap.  Subsequently, he has produced a 6-part [YouTube video series](https://www.youtube.com/watch?v=6l9e5KM9CUU) where he demonstrates the step-by-step process from importing a DEM to exporting the final product.

I followed along with his tutorial the first time, but found that when I was trying to reproduce the process on my own, I frequently had to go back to the videos. To make it easier to understand the workflow and quickly reference the different steps, I've created a [GoogleDoc spreadsheet](https://docs.google.com/spreadsheets/d/11HHMdKawdbXNkkxWdW82-HgHE2k3Tojg7P_X75ojb50/edit?usp=sharing) where I tried to transcribe each video, and sequentially number the steps within the workflow.

### Using ArcGIS Data Driven Pages   
The print cartography project I'm working on requires making about 60 unique maps.  My workflow is to organize and layout the map data in ArcGIS, then export the data from ArcGIS as an Adobe Illustrator file (.ai), and adjusting type and applying other styling in Adobe Illustrator.  Many of the maps will have a raster base data, so the raster files have to exported from ArcGIS separately as a TIFF file.  I'm exploring [ArcGIS's Data Driven Pages] (http://resources.arcgis.com/en/help/main/10.1/index.html#//00s90000003n000000) tools to see if they I can automate the export process in python with the [arcpy.mapping](http://resources.arcgis.com/en/help/main/10.1/index.html#//00s30000000n000000) module.  [Here's what I'm trying...](/Tutorials/Data-Driven-Pages/DataDrivenPagesExperiment.md)

### List of OpenStreetMap (OSM) tools     
A summary of the different tools I use for querying and downloading OSM data.  

##### Data Export  
   [GEOFABRIK downloads](http://download.geofabrik.de/): No account needed.  Download zipped .shp and .osm files based on a given country or administrative units.  
   [WeoGeo.com](http://www.weogeo.com/data/OpenStreetMap_Data.html): Free accountrequired. Define a custom AOI and download in a vareity of different common geospatial data formats.   
   [Overpass Turbo](http://overpass-turbo.eu/): No account needed.  Use Query Wizard to select specific features from current OSM data server for a user defined AOI.  Export data into any number of common geospatial data formats (No direct export to shapefil option). [Example Tutorial](/Tutorials/OSM-Export_Tools.md)
   
##### Visualize data statistics  

   [Taginfo](http://taginfo.openstreetmap.org/): See word cloud of most popular OSM tag Keys, and invidual statistics for each tag used.  
   [Neis One!](http://neis-one.org/): The personal website of Pascal Neis, there are lots of great webtools for tracking and analyzing edits to OSM by location, individual user name, and change sets. [How did you contributed to OpenStreetMap)[http://hdyc.neis-one.org/] generates a custom activity report for a specific username. [Your OSM HeatMap](http://yosmhm.neis-one.org/) generates a cusome heat map based on aggregating the location of a single users edits globally.   [Who's around me](http://resultmaps.neis-one.org/oooc) shows the locatio of other users based on a mean location of their edits for a specific point in time, or averages over 6 months.  
   [ito! OSM Mapper](http://www.itoworld.com/static/openstreetmap_tools/osm_mapper.html) Account required.  Generate maps and reports of editing activity by user, by tag, or by time for a user defined area.  Maps and tables are exportable in several easily accessible formats.
