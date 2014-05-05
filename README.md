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
The print cartography project I'm working on requires making about 60 unique maps.  My workflow is to organize and layout the map data in ArcGIS, then export the data from ArcGIS as an Adobe Illustrator file (.ai), and adjusting type and applying other styling in Adobe Illustrator.  Many of the maps will have a raster base data, so the raster files have to exported from ArcGIS separately as a TIFF file.  I'm exploring [ArcGIS's Data Driven Pages] (http://resources.arcgis.com/en/help/main/10.1/index.html#//00s90000003n000000) tools to see if they I can automate the export process in python with the [arcpy.mapping](http://resources.arcgis.com/en/help/main/10.1/index.html#//00s30000000n000000) module.  [Here's what I'm trying...](/Tutorials/Data-Driven-Pages/DataDrivenPagesTutorial.md)
