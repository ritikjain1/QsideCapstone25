# Instructions for Using Tableau
## Download Tableau
>
   a. Go to the official Tableau website: https://www.tableau.com/
>
   b. Click on "Try Tableau for Free" if you don’t have a license, or download Tableau Desktop if you have an account. 
>
   c. If you’re a student, you can get Tableau for free by applying for a Tableau for Students license at https://www.tableau.com/academic
  ![Image1](/Image1.png)
## Install Tableau 
  a. Open the downloaded installer (TableauDesktop-XX.exe for Windows or TableauDesktop-XX.dmg for Mac). 

  b. Follow the on-screen instructions to complete the installation.
 
  c. Once installed, open Tableau Desktop. 
## Load a Blank Map and Add CSV Files
 ### Connect to Your CSV File 
  
   1. Open Tableau and go to the "Connect" pane.
    
   2. Click on "Text File" (since CSV is a text file). 
    
   3. Select your CSV file and click Open. 
    
   4. Tableau will automatically load the data into the Data Source tab. 
    
   ![Image2](/Image2.png)
   ![Image3](/Image3.png)
   ### Open a Blank Map 
  
   1. Navigate to the "Sheet 1" tab. 
    
   2. Drag a geographical field (like "Country", "State", "City", or "Latitude/Longitude") onto the Columns or Rows shelf. 
    
   3. If you have explicit Latitude and Longitude columns, drag Longitude to Columns and Latitude to Rows. 
    
   4. If your dataset contains State or Country names, Tableau will recognize them as geographical fields. 
    
   ### Adding Your Data to the Map 
  
   1. Dragging a Geographic Field (e.g., Country, State, City) to "Detail" (Marks card) 
    
        - Will plot locations as points on the map. 
        
   2. Dragging a Numeric Field (e.g., Sales, Population) to "Color" 
    
      - Will create a color-coded map where values correspond to different intensities of color. 
      
   3. Dragging a Numeric Field (e.g., Sales, Population) to "Size" 
    
      - Will adjust the size of the points on the map based on the value of the field. 
      
   4. Dragging a Categorical Field (e.g., Region, Category) to "Filter" 
    
      - Allows you to filter your map based on the selected category.  
      
   5. Dragging a Numeric or Categorical Field to "Tooltip" 
    
      - Displays additional information when hovering over map points.
   ![Image4](/Image4.png)
      
  ## Finalizing and Customizing Your Map 
  
   1. Adjust the "Map Layers" (available under Map → Map Layers) to toggle different background styles. 
    
   2. Click "Show Me" to see other visualization options based on your dataset. 
    
   3. Use Filters to refine your data. 
    
   4. Save and export your visualization. 
    
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
   ### Option 2: Installing Overpass API Locall
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
    
# How to Install Excel
## Download Microsoft Excel 
- Go to the official Microsoft website: https://www.microsoft.com/
- Sign in to your Microsoft account (or create one if you don’t have one)
### Choose a Plan
   - If you have a Microsoft 365 subscription, Excel is included. 
   - If you need a one-time purchase, you can buy Excel separately.
   - Students may be eligible for free access via Microsoft Education.
Click "Install" to download the Excel setup file.
![Image5](/Image5.png)

### Install Microsoft Excel
- Open the downloaded installer (Setup.exe for Windows or .dmg for Mac). 
- Follow the on-screen instructions to complete the installation.
- Once installed, open Excel and sign in with your Microsoft account.
### Open and Load a CSV File in Excel
- Launch Excel and click on "File" > "Open."
- Select "Browse" and locate your .csv file.
- If the data doesn’t format correctly, use the Text Import Wizard
- Choose "Delimited" and click Next
- Select the correct delimiter (comma, tab, etc.), then click Finish.
- Your CSV file will be loaded into Excel.
![Image6](/Image6.png)
![Image7](/Image7.png)
![Image8](/Image8.png)

### Customizing Your Data in Excel
- Use Filters: Click on the filter icon (under "Data" > "Filter") to sort and filter values.
- Apply Conditional Formatting: Highlight values based on conditions.
- Create Pivot Tables: Summarize and analyze data efficiently.
- Use Formulas: Functions like SUM(), VLOOKUP(), and IF() help analyze data.
- Save and Export: Save your file in .xlsx, .csv, or .pdf format.






