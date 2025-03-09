#Instructions for Using Tableau
## Download Tableau
>
   a. Go to the official Tableau website: https://www.tableau.com/
>
   b. Click on "Try Tableau for Free" if you don’t have a license, or download Tableau Desktop if you have an account. 
>
   c. If you’re a student, you can get Tableau for free by applying for a Tableau for Students license at https://www.tableau.com/academic
  [Image 1]
## Install Tableau 
  a. Open the downloaded installer (TableauDesktop-XX.exe for Windows or TableauDesktop-XX.dmg for Mac). 
>
  b. Follow the on-screen instructions to complete the installation.
>
  c. Once installed, open Tableau Desktop. 
## Load a Blank Map and Add CSV Files
  a. Connect to Your CSV File 
  >
    1. Open Tableau and go to the "Connect" pane.
    
    2. Click on "Text File" (since CSV is a text file). 
    
    3. Select your CSV file and click Open. 
    
    4. Tableau will automatically load the data into the Data Source tab. 
    
    [Image 2]
    [Image3]
  b. Open a Blank Map 
  
    1. Navigate to the "Sheet 1" tab. 
    
    2. Drag a geographical field (like "Country", "State", "City", or "Latitude/Longitude") onto the Columns or Rows shelf. 
    
    3. If you have explicit Latitude and Longitude columns, drag Longitude to Columns and Latitude to Rows. 
    
    4. If your dataset contains State or Country names, Tableau will recognize them as geographical fields. 
    
  c. Step 3: Adding Your Data to the Map 
  
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
      
  ## Finalizing and Customizing Your Map 
  
    1. Adjust the "Map Layers" (available under Map → Map Layers) to toggle different background styles. 
    
    2. Click "Show Me" to see other visualization options based on your dataset. 
    
    3. Use Filters to refine your data. 
    
    4. Save and export your visualization. 
    
  
