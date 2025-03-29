# Instructions to use the US Census API with Qside’s ToyData 

## 1. Setting Up Your Jupyter Notebook 
To begin, open a Jupyter Notebook where you will run the provided code. You can either download the provided notebook file [USCensus_APICode.ipynb](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/USCensus_APICode.ipynb) or copy and paste the code into a new notebook to ensure it runs correctly. Before executing the code, you need to install the necessary Python packages. This script requires three key libraries: 

1. Requests – used for making API requests to the U.S. Census Bureau’s Geocoder. 

2. Pandas – used for handling and manipulating datasets. 

3. Time – a built-in Python module used to introduce delays between API calls (to prevent rate limits). 

After these are installed, if you look further down you can see there are 3 different pieces of code, one with the header “Producing Unique School Address Identifier GeoIDs” one other with the header “Producing Unique Address Identifier GeoIDs” one with the header “Producing LAT and LONG for Schools” and the last one with the header “Producing LAT an Long for students“.  

## 2. Retrieving GEOIDs Using the U.S. Census Geocoder API 

The first part of the code retrieves GEOIDs (Geographic Identifiers) for each school based on its address. These GEOIDs allow us to map each school to its respective Census Block, which can later be used for further demographic analysis. *Please remember to change the path files to your specific files* 

Here how the code works: 

1. Loading the School Data 

    a. The script first reads an Excel file containing the school dataset. 

        i. In the first line “file_path”, replace the current file path with the path your toy dataset is downloaded too on your computer. 

        ii. To do this on a Mac:  

            1. Open Finder and navigate to the location of your toy dataset. Use a two-finger click (or right-click) on the file icon, then select “Get Info” from the menu. In the information window that appears, look for the section labeled “Where,” which shows the folder path to the file. Copy that entire path. After pasting it into your code or document, add a slash at the end of the path and then type the exact name of your dataset file as it appears on your computer. For example: “.../Community partners/Student_Toy_data.xlsx”.  

 

            2. If this does not work, you can try adding ~ before your desktop to get this code working. Ex: “~/desktop/Student_Toy_data.xlsx”. 

 

    b.It extracts data from the "SchoolDemographics" sheet, which contains school names, addresses, cities, and states. 

2. Making API Requests to Retrieve GEOIDs 

    a. The script uses the U.S. Census Geocoder API endpoint: 

    [https://geocoding.geo.census.gov/geocoder/geographies/address](https://geocoding.geo.census.gov/geocoder/geographies/address)

    b. For each school, the script formats the request by sending: 

        i. Street Address 

        ii. City 

        iii. State 

        iv. Benchmark (set to "4" to use the most recent Census data) 

        v. Vintage (set to "4" to use the latest geography data) 

3. Processing the API Response 

    a. If the API successfully finds a match, it extracts the GEOID from the "2020 Census Blocks" section. 

    b. If no match is found, it records "No Match Found" instead. 

    c. If the API request fails, it records "Error" 

4. Saving the Results 

    a. The extracted GEOIDs, along with school names and addresses, are stored in a Pandas DataFrame. 

    b. The DataFrame is then saved as an Excel file, which can later be used for analysis in Tableau. 

        i. In the line that starts with “geoid_df.to_excel”, replace the current file path with the path you want the GEOID file to be downloaded too. 

        ii. On a Mac, locate the folder where you'd like your output Excel file to be saved. Open Finder and navigate to that folder. Then, two-finger click (or right-click) anywhere in the folder (or on any file inside it), and select “Get Info.” In the window that pops up, look at the “Where” section to find the full file path. Copy this folder path. Once you’ve pasted it into your code, add a slash (/) at the end, then type in the name of your output file “School_GEOID_Mapping.xlsx”, make sure to keep the file name as we have it. For example: /Community partners/School_GEOID_Mapping.xlsx 
        
        iii. If this does not work, you can try adding ~ before your desktop to get this code working. Ex: “~/desktop/Student_Toy_data.xlsx”. 
        
If you want to just get the geoids excel sheet just click on this link: [School_GEOID_Mapping.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/School_GEOID_Mapping.xlsx)


## Things You May Need to Modify 

1. File Path (file_path) – Change this to the correct location where your dataset is stored. (Line 1) *Reading File* 

2. Sheet Name (sheet_name) – If your Excel sheet name is different from "SchoolDemographics", update this accordingly. 

3. Column Names in address_params – If your dataset has different column names for street, city, and state, modify: 

    a. "street": row["YourStreetColumn"] 

    b. "city": row["YourCityColumn"] 

    c. "state": row["YourStateColumn"] 

4. Saving the Output File (output_file) – Change the file path where you want to save the results. (“geoid_df.to_excel” Line) *Writing File* 

 

## 3. Retrieving Latitude and Longitude Coordinates 

After obtaining GEOIDs, the next step is to retrieve the latitude and longitude of each school using the same Census API. This allows us to create accurate geospatial visualizations in Tableau. 

The code works mainly the same as the first 2 code scripts but here are the key main differences: 

1. Benchmark (set to "Public_AR_Current", which ensures up-to-date data) 

2. If the API successfully finds a match, it extracts: 

    a. Latitude (y coordinate) 

    b. Longitude (x coordinate) 

 

## 4. Running the Code Step-by-Step 

1. Run the Jupyter Notebook cell-by-cell 

    a. First, retrieve the GEOIDs.  

    b. Then, retrieve the latitude and longitude values. 

    c. Save the results as separate Excel files. 

2. Verify the Results 

a. Open the Excel file (School_Lat_Lon.xlsx) and check if latitude and longitude values were extracted correctly. 

b. If any values appear as "No Match", check If the address is formatted correctly or If the Census API recognizes the location. 

3. Load the Data into Tableau 

    a. Import the latitude and longitude dataset into Tableau. 

    b. Assign Latitude to the Rows shelf and Longitude to the Columns shelf. 

    c. Adjust visualization settings to properly display the schools on a map. 

    d. How to fully operate this in tableau is on Instructions_Linking_ToyData_Tableau.docx 

 

 

 

 

 