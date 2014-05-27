Exporting map data into separate Adobe Illustrator (.AI) files for each individual map can be a lot of repetitive clicking.  I've already prepared and styled the vector data and shaded relief rasters, and I've also created a polyon layer which shows the extent for each map.  My hope is that I can use the arcpy.mapping module to write a python script which will loop through each polygon feature in my map extent layer, and export the area inside each feature as a new .AI file.

It looks like there are already some useful pyton scripts to work from in the ESRI support documentation.

One of the first things I need to do is to make sure that I don't have any vector layers styled using transparency.  In the ESRI Support pages, there is a [python script](http://resources.arcgis.com/en/help/main/10.1/index.html#//00sm00000004000000) designed to create a report which tells you which layers in your MXD curently have a transparency applied
import arcpy

```
def DetectRasterization():
  mxd = arcpy.mapping.MapDocument("CURRENT")
  df_list = arcpy.mapping.ListDataFrames(mxd)
  foundRasterization = False
  noneFoundMsg = "No rasterizing layers were detected."
  for df in df_list:
    lyr_list = arcpy.mapping.ListLayers(mxd, data_frame=df)
    for lyr in lyr_list:
      if lyr.isRasterizingLayer or lyr.supports("BRIGHTNESS"):
        foundRasterization = True
        if lyr.isGroupLayer and lyr.transparency > 0:
          print "In data frame '" + df.name + "', the group layer '" + \
                   lyr.longName + "' is a rasterizing layer:\r",
          print "\tVisibility is " + str(lyr.visible) + ".\n" + \
                "\tTransparency is " + str(lyr.transparency) + " percent.\n"
        elif not lyr.isGroupLayer:
          print "In data frame '" + df.name + "', the layer '" + \
                   lyr.longName + "' is a rasterizing layer:\r",
          if lyr.transparency > 0:
            print "\tVisibility is " + str(lyr.visible) + ".\n" + \
                  "\tTransparency is " + str(lyr.transparency) + " percent.\n"
          else:
            print "\tVisibility is " + str(lyr.visible) + ".\n" + \
                  "\tTransparency is 0 percent, but the layer may be a\n" + \
                  "\traster layer or contain rasterizing symbology such\n" + \
                  "\tas bitmap picture symbols.\n"
      del lyr
    del lyr_list
    del df
  if not foundRasterization:
    print noneFoundMsg
  del df_list
  del mxd

DetectRasterization()
```

In addition to having a hard time remembering whether transparency has been applied or not, I also have a hard time keeping track of label classes, since they may or may not match your feature symbology classes.  The python script below (based on "LabelClass Example 1" [found here](http://resources.arcgis.com/en/help/main/10.2/index.html#/LabelClass/00s30000002t000000/)) will quickly run a report of the currently applied label classes.

```
import arcpy
mxd = arcpy.mapping.MapDocument("CURRENT")
for lyr in arcpy.mapping.ListLayers(mxd):
    if lyr.supports("LABELCLASSES"):
        if lyr.showLabels:
            print "Layer name: " + lyr.name
            for lblClass in lyr.labelClasses:
                if lblClass.showClassLabels:
                    print "    Class Name:  " + lblClass.className
                    print "    Expression:  " + lblClass.expression
                    print "    SQL Query:   " + lblClass.SQLQuery
del mxd
```

The script below (copied from "Example 2" [here](http://resources.arcgis.com/en/help/main/10.1/index.html#/ExportToAI/00s30000002v000000/)) will export an AI file based on the current data frame extent, and desired output resolution.   

```
import arcpy   
mxd = arcpy.mapping.MapDocument(r"C:\Project\Project.mxd")
df = arcpy.mapping.ListDataFrames(mxd, "Transportation")[0]
arcpy.mapping.ExportToAI(mxd, r"C:\Project\Output\ProjectDataFrame.ai", df,
                         df_export_width=1600,
                         df_export_height=1200)
del mxd
```

!!Here's a script I just made which actually worked.  I had to greatly simplify the MXD file I started with, but the output are 5 different maps covering different parts of the world as defined by a single input shapefile. 

```
print "starting script"

import arcpy

#Set the name of MXD File to open.  Note MXD must already have Data Driven Pages initiated
mxd = arcpy.mapping.MapDocument("Z://Yellow_Book_2016//AdministrativeFiles//Maps//MapTemplates//DataDrivenPages_ReferenceMap_MultiScale_v1.mxd")

print "starting for loop"

#For each pageNum in range of all page numbers, export an AI file
for pageNum in range(1, mxd.dataDrivenPages.pageCount + 1):
    
    #Set currentPageID equal to the current pageNum
    mxd.dataDrivenPages.currentPageID = pageNum
    
    #Run ExportToAI process
    arcpy.mapping.ExportToAI(mxd, "C://Temp//DataDrivenPagesTest//" + str(pageNum) + ".ai")
    
    #print command when each map is done
    print "... done with map " + str(pageNum)
del mxd
