# Exporting an ArcGIS Map Document to Adobe Illustrator

ArcGIS Desktop software is a great place to *begin* making a map, but often I find that there are additional types of graphic map styling.  Fortunately ArcGIS makes this process pretty easy, but there are a few tips and tricks which will help make the exported AI file an easier document to work with.  One of the primary reasons for exporting ArcGIS Maps to adobe illustrator is because you apply additional styles to vector artwork, such as blured lines, and for laying out type on curved paths.  

If your map includes raster data, you will want to export that data as individual TIFF files, and not have them turned on during the AI Export.  If you do not do this, the raster layers will export and be included in the AI file, *but* it will be divided into multiple striped images, and not a single layer.

## Work to be done in ArcGIS before exporting:
1. Load your map data
2. Style your map data  * **See detailed description below of styles to avoid** *
2. Assign a map projection
3. Define your output map size
4. Adjust your map position
5. Create a bookmark of the final map size and position


## ArcGIS Map style settings that cause problems in Illustrator
  * Transparency:  Transparent vector layers are converted to raster data, and are not exported as editable vector features. As such, if you want your final map to include transparent features, you will want to apply these style setting in Illustrator after the export.

  * Vector Fill Patterns:

  * Dashed lines:  A broken line (any combination of dashes or dots) exports each individual dash or dot as a single line   object, not as a single line wiht a continuous style applied to it.  Like transparency, this style effect is best applied in Adobe Illustrator.

## ArcGIS Type Style settings to avoid
While the MapLex Labeling Engine does a great job of placing text, several different type settings limit the editability of the type after it has been exported, thus I choose to avoid using them.

## Export settings for Adobe Illustrator (AI) files.
On the General Tab:  
1) set the Resolution to '300' dpi  
2) set the Output Image Quality to 'Best'  
3) check the option-box for 'Clip Output Graphics Extent'  

On the format tab:  
1) set the Destination Colorspace to 'CMYK'  
2) set the Picture Symbol to 'Vectorize layers with bitmap markers/fills'  
3) uncheck 'Convert Marker Symbols to Polygons.'  The result that is produced when ArcGIS generalizes the shapes of these marker symbols is inconsistent.  Much more desirable results are achieved by using the Type -> Create Outlines operations.
