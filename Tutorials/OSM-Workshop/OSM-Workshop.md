### *Learn OpenStreetMap in an Afternoon*, Tuesday, October 14, 2014

My name is Ryan Lash, and I am excited to share with you some things I have learned about OpenStreetMap.  I first heard of OSM in 2010 after the Haiti Earthquake, but I didn't start contributing to OSM until about 2 years ago when I was interested in mapping my neighborhood in Atlanta.  Since then, my time and energy spent mapping has increased, and my interest in using OSM in my public health work has grown.  I am now using OSM data for some of my CDC projects, as are several other CDC friends, and I would like to share this knowledge with you so we can begin to grow a CDC OSM community.

1:00, **Make sure computers and wi-fi are working** 
  - Go to the [OSM Account Login webpage](https://www.openstreetmap.org/login?referer=%2F) and create an account.  If you already have an account, make sure you can login.  

1:10, **Introductions by workshop attendees**  

1:25, **Show some slides**  
  - Data Coverage
  - Data License  
  - Digital Data format (Tags; Key:Value)  

1:45, **Start Editing OSM in a web-browser [iD Editor](http://learnosm.org/en/editing/id-editor/)**  
  - Add your house  
  - Add your driveway  
  - Add 4 more POIs
  - Take a look at MapRoulette

2:00, **Discuss Editing Experience**  
  - Demoonstrate mapping in [Potlatch](http://wiki.openstreetmap.org/wiki/Potlatch_2) (incase you have to edit with MS Internet Explorer!)
  - Demonstrate advanced editing with [JOSM](http://learnosm.org/en/beginner/start-josm/)
  - Explore all the different things that are already mapped in OSM by browsing the [map](openstreetmap.org) and by visiting the [OSM Wiki Map Features](http://wiki.osm.org/wiki/Map_Features) page.  
    - [Taginfo](http://taginfo.openstreetmap.org/): See word cloud of most popular OSM tag Keys, and invidual statistics for each tag used.    
    - [Neis One!](http://neis-one.org/): The personal website of Pascal Neis, there are lots of great webtools for tracking and analyzing edits to OSM by location, individual user name, and change sets. [How did you contributed to OpenStreetMap](http://hdyc.neis-one.org/) generates a custom activity report for a specific username. [Your OSM HeatMap](http://yosmhm.neis-one.org/) generates a custom heat map based on aggregating the location of a single users edits globally.   [Who's around me](http://resultmaps.neis-one.org/oooc) shows the location of other users based on a mean location of their edits for a specific point in time, or averages over 6 months.  
    - [ito! OSM Mapper](http://www.itoworld.com/static/openstreetmap_tools/osm_mapper.html) Account required.  Generate maps and reports of editing activity by user, by tag, or by time for a user defined area.  Maps and tables are exportable in several easily accessible formats.

  
2:15,  -- Break --  


2:20, **More background on OSM and Humanitarian OpenStreet Map (HOT)**  
  - HOT History and Community (State Department MapGive, Red Cross, MSF, CDC?)  
  - HOT Coordination between organizations
    - Ex: OSM wiki-page [2014 West Africa Ebola Response](https://wiki.openstreetmap.org/wiki/2014_West_Africa_Ebola_Response)
  - HOT Mapping from Bing
    - [Use this map](http://ant.dev.openstreetmap.org/bingimageanalyzer/) to find out if there is high-resolution Bing Coverage
  - HOT External Data Sources  
    - Connecting to a Web-Mapping Service (WMS)
  - Using the Tasking Manager
    - [HOT Tasking Manager](http://tasks.hotosm.org/)

2:35, **Hands-on HOT Mapping**
  - Head on over to the [HOT Tasking Manager](http://tasks.hotosm.org/)
  - Review tagging conventions for less-developed countries- OSM wiki-page [Africa Highway Tag](https://wiki.openstreetmap.org/wiki/Highway_Tag_Africa)
  - Review the [West Africa HOT Mapping Tips](http://wiki.openstreetmap.org/wiki/User:Bgirardot/Typical_Road_and_Residential_Task)

  
3:15, **Hands-on Data Download** 
  - Screenshots from OSM Main Page
  - [GEOFABRIK downloads](http://download.geofabrik.de/): No account needed. Data for download is Updated roughly once every 24hrs. Download zipped .shp and .osm files based on a given country or administrative units.  
  - [WeoGeo.com](http://www.weogeo.com/data/OpenStreetMap_Data.html): Free account required. Data for download is refreshed  roughly once every month. Define a custom AOI and download in a vareity of different common geospatial data formats.    
  - [Overpass Turbo](http://overpass-turbo.eu/): No account needed.  Use Query Wizard to select specific features from current OSM data server for a user defined AOI.  Export data into any number of common geospatial data formats (No direct export to shapefil option). Data downloaded is from current OSM database. [Example Tutorial](/Tutorials/OSM-Export_Tools.md).  
  - [Mapzen](https://mapzen.com/metro-extracts/): No account needed.  Data refreshed weekly.  Coverage is for approximately 240 major cities in the world.  Download zipped .osm, .shp, and .geoJSON files.
  - [HOT Exports](http://export.hotosm.org/): Free account required. Users can select their own AOI. Download only the features/tags you want by creating your own download preset, or choose from a tag presets.  Data downloaded is from current OSM database. Queries can be saved to the users account, and can be rerun whenever refreshed data is desired. A significant limitation to this tool is that it does not support exports for all parts of the globe.  See the [OSM Wiki- HOT Export](http://wiki.openstreetmap.org/wiki/HOT_Exports) page for a map of areas covered by this tool, and for more information on how to use it.

3:30, **Quick survey of other OSM tools and applications**  
  - [MapOSMatic](http://www.maposmatic.org/): Create mapbooks from Mapnik for easy download and printing.
  - [MapBox](https://www.mapbox.com/): Design and publish beautiful online maps
  - [NPTiles](http://www.nps.gov/npmap/park-tiles/#4/39.00/-96.00): Pretty good for a federal agency
  - There are [a lot of different ways](http://wiki.openstreetmap.org/wiki/Mapping_techniques) to add data to osm  
    - I am still waiting for the right project to use [Field Papers](http://fieldpapers.org/)!
  - OSM-wiki list of [iOS Mobile Apps](http://www.nps.gov/npmap/park-tiles/#4/39.00/-96.00)
    - [Pushpin](http://wiki.openstreetmap.org/wiki/Pushpin_OSM):  efficiently add POI data from Bing Imagery or GPS with this very easy to use interface.  Unfortunately, it doesn't work for disconnected editing
    - [GoMap!](http://wiki.openstreetmap.org/wiki/Go_Map!!):  good for editing lines and polygons, although the interface is a little clunky
    - [CityMaps2Go](http://wiki.openstreetmap.org/wiki/City_Maps_2Go): Not sure you will have mobile-data access?  With a little planning ahead of time, you can quickly grab lots of maps for offline navigation
  - OSM-wiki list of [Android Apps](OSM-wiki list of )
    - [OsmAND](http://wiki.openstreetmap.org/wiki/OsmAnd):  this app supports data collection even while not connected to the internet.
  - Gamify map editing with [MapRoulette](http://wiki.openstreetmap.org/wiki/MapRoulette)

4:00, **Wrap-up Discussion**
  - Complete course evalutions

   5. Help out others by contribuing to specific mapping projects, by joining the [Humanitarian OpenStreetMap Team (HOT)](http://hot.openstreetmap.org/get-involved) or by participating in a [Missing Maps](http://wiki.openstreetmap.org/wiki/Missing_Maps_Project) mapathon.

_____
### Additional Resources (list is woefully incomplete):  
_____
#### Learn about OSM Tools
  - [LearnOSM.org](http://learnosm.org/en/editing/id-editor/) provides free tutorials written at beginner, intermediate, and advanced levels using all open-source and freely available software, including: iD, JOSM, PostGIS, and QGIS software.  

#### OpenStreetMap Community Communication Channels  
  - [Talk directly to other mappers](http://wiki.openstreetmap.org/wiki/Beginners_Guide_1.6#Community) in realtime using IRC 
  - Join and post messages to email listservs, [OSM mailing lists](http://wiki.openstreetmap.org/wiki/Mailing_lists)
  - Follow OSM leaders on Twitter  
  - Attend a *State of the Map* OSM conference;  explore archives of [previous OSM conferences](http://wiki.openstreetmap.org/wiki/State_of_the_Map_US#State_of_the_Map_U.S._.28SotM-US.29) including [slides and video recordings](http://wiki.openstreetmap.org/wiki/State_Of_The_Map_U.S._2014/Video_recordings) of presentations!
  - Organize or attend a local #mapathon  

#### Volunteer Technical Communities  
  - Digital Humanitarian Network, *[Guidance for Collaborating with Formal Humanitarian Organizations](http://reliefweb.int/report/world/guidance-collaborating-formal-humanitarian-organizations)*  
  - Digital Humanitarian Network, *[Guidance for Collaborating with Volunteer & Technical Communities](http://reliefweb.int/report/world/guidance-collaborating-volunteer-technical-communities)*
