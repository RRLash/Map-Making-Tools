# Exporting an ArcGIS Map Document to Adobe Illustrator

ArcGIS Desktop software is a great place to *begin* making a map, but often I find that there are additional types of graphic map styling.  Fortunately ArcGIS makes this process pretty easy, but there are a few tips and tricks which will help make the exported AI file an easier document to work with.  One of the primary reasons for exporting ArcGIS Maps to adobe illustrator is because you apply additional styles to vector artwork, such as blured lines.  

If your map includes raster data, you will want to export that data as individual TIFF files, and not have them turned on during the AI Export.  If you do not do this, the raster layers will export and be included in the AI file, *but* it will be divided into multiple striped images, and not a single layer.

## Work to be done in ArcGIS before exporting:
1. Load your map data
2. Style your map data **See detailed description below of styles to avoid**
2. Assign a map projection
3. Define your output map size
4. Adjust your map position
5. Create a bookmark of the final map size and position


## Map styles to avoid using
*Transparency:  Transparent vector layers are converted to raster data, and are not exported as editable vector features.  As such, if you want your final map to include transparent features, you will want to apply these style setting in Illustrator after the export.

*Vector Fill Patterns:
