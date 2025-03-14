# Instructions for Using OpenStreetMap API
## Understanding the OpenStreetMap API 
The OpenStreetMap (OSM) API allows users to interact with OSM data, retrieve maps, query geolocation data, and contribute edits to the global map. 

### OSM provides several APIs, including: 
   - OSM REST API (for editing and retrieving raw data)
   - Overpass API (for querying OSM data)
   - Mapnik & Tile Server (for rendering OSM tiles)
   - Nominatim (for geocoding and reverse geocoding)
     

## Installing OpenStreetMap API Locally
   ### Option 1: Access OpenStreetMap API via a Web Endpoint
   - Access Overpass API: https://overpass-turbo.eu/
   - Access Nominatim API: https://nominatim.openstreetmap.org/
   - Start making API requests directly from your browser.
   ### Option 2: Installing Overpass API Local
   - Install dependencies, for Linux/macOS, open a terminal and run
        1. sudo apt update && sudo apt install overpass-api
   - For Windows, use the WSL (Windows Subsystem for Linux) or install Docker
   - To Download the OSM data run the following command:
        1. wget Http://download.geofabrik.de/europe/germany-latest.osm.bz2/
   - Replace germany-latest.osm.bz2 with your desired region
   - Set up the Overpass server - Extract and initialize the database:
        1. mkdir -p overpass_db
        2. ./bin/init_osm3s.sh overpass_db < path/to/osm-file.osm.bz2
   - Start the Overpass API server
        1. bin/dispatcher --osm-base --db-dir=overpass_db
   - The Overpass API will now be running locally.
   ### Option 3: Installing Nominatim (Geocoding API)
   - Install dependencies
        1. sudo apt install postgresql postgis
   - Clone the Nominatim repository
        1. git clone --recursive https://github.com/openstreetmap/Nominatim.git
        2. cd Nominatim
   - Download the OSM Data
        1. wget https://download.geofabrik.de/north-america/us-latest.osm.pbf
   - Import data into the database
        1. ./utils/setup.php --osm-file us-latest.osm.pbf --all
   -  Start the Nominatim API
        1. ./utils/start.sh
   - **Making API Requests**
   - Overpass API Example 
   - Use Overpass Turbo to find points of interest (POIs)
        1. https://overpass-api.de/api/interpreter?data=[out:json];node["amenity"="restaurant"](50.6,7.0,50.8,7.3);out;
   - Nominatim API Example (Geocoding) 
   - Find coordinates of a location:
        1. https://nominatim.openstreetmap.org/search?q=New+York&format=json
   - Reverse geocode a latitude/longitude:
        1. https://nominatim.openstreetmap.org/reverse?lat=40.7128&lon=-74.0060&format=json
   - Finalizing Setup
   - Test your installation by running API queries, Use Python to interact with OSM API
        1. pip install requests folium #Install the required Python libraries
   - Example API call in Python
        1. import requests			 
        2. response = requests.get("https://nominatim.openstreetmap.org/searchq=Chicago&format=json") 
        3. print(response.json())
   - Optimize performance: Configure caching for faster queries & Regularly update your OSM data
   - Exporting and Visualizing Data - Export OSM data using the osmconvert tool
        1. osmconvert us-latest.osm.pbf -o=us-latest.o5m
   - Visualize map data in QGIS or Python (folium)
        1. import folium
        2. map = folium.Map(location=[40.7128, -74.0060], zoom_start=12)
        3. map.save("map.html")
