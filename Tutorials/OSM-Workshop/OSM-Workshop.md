#Learn OpenStreetMap in an Afternoon
## Tuesday, October 14, 2014

### 1:30 Get Started

### 4:00 Start wraping things up


### List of OpenStreetMap (OSM) tools     
A summary of the different tools I use for querying and downloading OSM data.  

##### OpenStreetMap (OSM) and Humanitarian OpenStreetMap Team (HOT)
I think OSM is an incredibly valuable tool, and I think everyone should know about it. Here's how you can get started.   

   1. Start with [MapGive](http://wwww.mapgive.state.gov), and wathc the [Why you should map](http://mapgive.state.gov/why-map/) video.  Follow the instructions on the [Learn to map](http://mapgive.state.gov/learn-to-map/) webpage to create an OpenStreetMap account.  
   2. Learn how to edit OSM using the iD Editor- it only takes a few minutes! You can continue to follow along with the MapGive [Learn how to map in OpenStreetMap](http://mapgive.state.gov/learn-to-map/) video (11 minutes), or follow along with this succint tutorial from [learnOSM.org](http://learnosm.org/en/editing/id-editor/).
   3. Explore all the different things that are already mapped in OSM by browsing the [map](openstreetmap.org) and by visiting the [OSM Wiki Map Features](http://wiki.osm.org/wiki/Map_Features) page.  [TagInfo](https://taginfo.openstreetmap.org/) provides nice tools for visualizing the different tags currently used in the OSM database.
   4. Connect with others in the OSM Community.  Join one (or a couple) of the [OSM mailing lists](http://wiki.openstreetmap.org/wiki/Mailing_lists).
   5. Help out others by contribuing to specific mapping projects, by joining the [Humanitarian OpenStreetMap Team (HOT)](http://hot.openstreetmap.org/get-involved) or by participating in a [Missing Maps](http://wiki.openstreetmap.org/wiki/Missing_Maps_Project) mapathon.

##### Data Export  
   * [GEOFABRIK downloads](http://download.geofabrik.de/): No account needed. Data for download is Updated roughly once every 24hrs. Download zipped .shp and .osm files based on a given country or administrative units. 
   * [Mapzen](https://mapzen.com/metro-extracts/): No account needed.  Data refreshed weekly.  Coverage is for approximately 240 major cities in the world.  Download zipped .osm, .shp, and .geoJSON files.
   * [WeoGeo.com](http://www.weogeo.com/data/OpenStreetMap_Data.html): Free account required. Data for download is refreshed  roughly once every month. Define a custom AOI and download in a vareity of different common geospatial data formats.   
   * [Overpass Turbo](http://overpass-turbo.eu/): No account needed.  Use Query Wizard to select specific features from current OSM data server for a user defined AOI.  Export data into any number of common geospatial data formats (No direct export to shapefil option). Data downloaded is from current OSM database. [Example Tutorial](/Tutorials/OSM-Export_Tools.md).  
   * [bbox finder](http://bboxfinder.com/): No account needed.  This handy tool allows you to quickly get the Lat/Long values for any user defined AOI in the web-mercator projection.  
   * [HOT Exports](http://export.hotosm.org/): Free account required. Users can select their own AOI. Download only the features/tags you want by creating your own download preset, or choose from a tag presets.  Data downloaded is from current OSM database. Queries can be saved to the users account, and can be rerun whenever refreshed data is desired. A significant limitation to this tool is that it does not support exports for all parts of the globe.  See the [OSM Wiki- HOT Export](http://wiki.openstreetmap.org/wiki/HOT_Exports) page for a map of areas covered by this tool, and for more information on how to use it.
   * [MapOSMatic](http://www.maposmatic.org/) Create mapbooks from Mapnik for easy download and printing.

##### OSM database Visualization and summary statistic tools  
   * [Taginfo](http://taginfo.openstreetmap.org/): See word cloud of most popular OSM tag Keys, and invidual statistics for each tag used.  
   * [Neis One!](http://neis-one.org/): The personal website of Pascal Neis, there are lots of great webtools for tracking and analyzing edits to OSM by location, individual user name, and change sets. [How did you contributed to OpenStreetMap](http://hdyc.neis-one.org/) generates a custom activity report for a specific username. [Your OSM HeatMap](http://yosmhm.neis-one.org/) generates a custom heat map based on aggregating the location of a single users edits globally.   [Who's around me](http://resultmaps.neis-one.org/oooc) shows the location of other users based on a mean location of their edits for a specific point in time, or averages over 6 months.  
   * [ito! OSM Mapper](http://www.itoworld.com/static/openstreetmap_tools/osm_mapper.html) Account required.  Generate maps and reports of editing activity by user, by tag, or by time for a user defined area.  Maps and tables are exportable in several easily accessible formats.
