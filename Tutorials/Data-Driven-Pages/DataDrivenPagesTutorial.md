Exporting map data into separate Adobe Illustrator (.AI) files for each individual map can be a lot of repetitive clicking.  I've already prepared and styled the vector data and shaded relief rasters, and I've also created a polyon layer which shows the extent for each map.  My hope is that I can use the arcpy.mapping module to write a python script which will loop through each polygon feature in my map extent layer, and export the area inside each feature as a new .AI file

It looks like there are already some useful pyton scripts to work from in the ESRI support documentation.

One of the first things I need to do is to make sure that I don't have any vector layers styled using transparency, since 

The script below (copied from "Example 2" [here](http://resources.arcgis.com/en/help/main/10.1/index.html#/ExportToAI/00s30000002v000000/) will export an AI file based on the current data frame extent, and desired outpu resolution
import arcpy
mxd = arcpy.mapping.MapDocument(r"C:\Project\Project.mxd")
df = arcpy.mapping.ListDataFrames(mxd, "Transportation")[0]
arcpy.mapping.ExportToAI(mxd, r"C:\Project\Output\ProjectDataFrame.ai", df,
                         df_export_width=1600,
                         df_export_height=1200)
del mxd
