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
##TITLE: Exporting ArcGIS maps to AI using DataDrivenPages and Definition Queries
##AUTHOR:  Ryan Lash
##DATE:  5/28/2014
##PURPOSE:  This script is meant to help automate the workflow for exporting
##    lots of maps from the same MXD file using ArcGIS Data Driven Pages.
##    The input for this is an MXD file which contains:
##        -A series of vector layers using mostly Natural Earth Data
##        -An "Index file" (See ArcGIS docs on "Data Driven Pages"), which in this
##            example is a polygon feature layer with rectangles showing the desired
##            extent for each map to be output.
##    The desired output is a reference map where the country of interest shows
##    Admin 1 boundaries drawn for only the country of interest, with each
##    of these Admin 1 regions labeled.  Since the Natural Earth Data has a global
##    coverage, a Defenition Query is used to select only the Admin 1 labels and
##    Admin 1 boundaries for the country of interest for that map.  In this example,
##    the admin 1 boundary files is a line file, so a separate file is needed for
##    labeling the areas.  These files have slightly different field names, so while
##    each definition query relies on the name of the country for defining the query,
##    the field names are different for the two feature layers.

    
print "*STARTING SCRIPT NOW*\n"

import arcpy

#Specify map document and data frame.  Note MXD must already have Data Driven Pages initiated
mxd = arcpy.mapping.MapDocument("Z://Yellow_Book_2016//AdministrativeFiles//Maps//MapTemplates//DataDrivenPages_ReferenceMap_MultiScale_v1.mxd")

print "Starting Data Driven Pages FOR loop"

for pageNum in range(1, mxd.dataDrivenPages.pageCount + 1):

    mxd.dataDrivenPages.currentPageID = pageNum
    outputFileName = mxd.dataDrivenPages.pageRow.getValue('MapTitle')
    
    #Retrieve and define query argument value from QryAdmin1 Field in DataDrivenPages Index File
    qryDefArg = mxd.dataDrivenPages.pageRow.getValue('QryAdmin1')
    print "\t...Defining query arguement as: " + qryDefArg
    
    #Create query text for Label and Line layers
    qryDefAdmin1Label = '"admin" = ' + "'" + qryDefArg + "'"
    qryDefAdmin1Line = '"adm0_name" = ' + "'" + qryDefArg + "'"
    
    #Loop through layers in Data Frame to identify Label and Line Layers, and then pass the Defenition Queries
    for lyr in arcpy.mapping.ListLayers(mxd):
        if lyr.name == "ne_10m_admin_1_label_points":
            lyr.definitionQuery = qryDefAdmin1Label
        if lyr.name == "ne_10m_admin_1_states_provinces_lines_geodb":
            lyr.definitionQuery = qryDefAdmin1Line
    print "\t...Definition queries completed"
    
    #Refresh the Active View
    arcpy.RefreshActiveView()
    
    #Run the export to AI process
    arcpy.mapping.ExportToAI(mxd, "C://Temp//DataDrivenPagesTest//" + outputFileName + ".ai")
    
    print "\tExport complete for map " + outputFileName
    
del mxd

print "\n*SCRIPT COMPLETED*"

```
