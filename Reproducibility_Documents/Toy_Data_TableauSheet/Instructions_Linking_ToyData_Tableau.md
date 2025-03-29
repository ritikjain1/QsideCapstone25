# Instructions for creating Toy Data set specific Tableau sheets

To begin linking our toy data in Tableau, we need access to specific
software and files on your computer. First, ensure that Tableau Public
is installed on your machine. Please refer to the installation guide
[Installing_Tableau.docx](/Reproducibility_Documents/Tableau/Installing_Tableau.md)
for detailed instructions on this topic.

Once Tableau is installed, make sure you have the following files
downloaded to your computer:

[Student_Toy_data.xlsx](/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx)

[School_GEOID_Mapping.xlsx](/Reproducibility_Documents/Toy_Data_TableauSheet/School_GEOID_Mapping.xlsx)

[tl_2023_17_tabblock20
folder](Reproducibility_Documents/Toy_Data_TableauSheet/Download_tl_2023_17_tabblock20.md)

## Step 1: Adding our data sources into Tableau

Open Tableau, we should see options to connect to a file, navigate to
the Connect drop-down menu and click on the Microsoft excel file option
as we want to connect our toy data set first, which is an excel sheet.

![Add_Excel](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Add_Excel.png)

Navigate to where you have the student toy data set saved onto your
computer and then click \"Open\" to open the file into Tableau.

![Select_ToyData](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Select_ToyData.png)

Now the screen should look like this:

![ConnectionsPane1](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/ConnectionsPane1.png)

From here we want to click Add next to connections and then add in our
other files.

1.  Click \"Add\" next to Connections to include more files.

![Add_on_ConnectionPane](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Add_on_ConnectionPane.png)

a.  Adding the School_GEOID_Mapping.xlsx

    - Click on "Add"

    - Select the "Microsoft Excel" option

    - Navigate to where you have the School_GEOID_Mapping.xlsx saved
      onto your computer

    - Select School_GEOID_Mapping.xlsx

    - Click \"Open"

![Add_GEOID_Excel](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Add_GEOID_Excel.png)

b.  Add the Shape File (tabblock20.shp)

    - Click \"Add\" again.

    - Select \"Spatial File\" as the file type.

    - Navigate to the where you have the tabblock folder saved.

    - Select tabblock20.shp

    - Click "Open"

![Add_ShapeFile](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Add_ShapeFile.png)

Once you have added all the data files into Tableau, you have completed
step 1, your connections pane should look like this:

![Small_ConnectionPane](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Small_ConnectionPane.png)

## Step 2: Creating Links between Data Sources

We want to connect the different data sources which we have added in the
previous step in order to build a map by leveraging relationships
between the data and connecting our files appropriately.

Clicking on an Excel file in our connections pane will display the
individual sheets within the file.

![Large_ConnectionPane](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Large_ConnectionPane.png)

We want to start with
[School_GEOID_Mapping.xlsx](/Reproducibility_Documents/Toy_Data_TableauSheet/School_GEOID_Mapping.xlsx)
and build connections from that file.

Start by clicking on School_GEOID_Mapping in the connections pane. There
should be a sheet named "Sheet 1". Drag Sheet 1 into the empty space on
the right.

![Connection_Drag_GEOID](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Connection_Drag_GEOID.png)

Next, click on Student_Toy_Data in the connections pane. There will be
multiple sheets in the dropdown menu. Add "SchoolDemographics" as a
connection to Sheet1 by dragging the sheet next to the already existing
connection on the right.

![Connection_Drag_SchoolDemo](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Connection_Drag_SchoolDemo.png)

You can then set the relationship between the two files in the bottom
left

set School = School Name

![Relationship1](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Relationship1.png)

After adding the SchoolDemographics sheet to the connections, we want to
add StudentSchoolPresence and StudentDemographics sheets to the
connections. Repeat the process above adding in StudentSchoolPresence
sheet first and then the StudentDemographics sheet afterwards.

\*The relationships between all of the sheets should automatically fill
out for the connections. Now our data source should look like this:

![Connection_Drag_SSP_StudDemo](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Connection_Drag_SSP_StudDemo.png)

Finally, we want to add the spatial data connection. Click on the
tl_2023_17_tabblock20 in the connections pane. Then click on the
"tl_2023_17_tabblock20" file under files. Drag this file next to Sheet1,
a branch will begin to appear to create a connection between Sheet1 and
tl_2023_17_tabblock20.

![Connection_Drag_Shape](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Connection_Drag_Shape.png)

You will once again have to define the relationship

set Geoid = Geoid20.

![Relationship2](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Relationship2.png)

This is what the connections should look like after finishing step 2:

![Final_ConnectionPane](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Final_ConnectionPane.png)

## Step 3: Creating the visualization

Now we want to leverage our toy data to create the map, click on the new
sheet option at the bottom of the Tableau dashboard to get started with
creating the map, it should look like this:

![Tableau_Sheet1](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Tableau_Sheet1.png)

From here we want to drag some variables from our Tables drop down menu
into our marks menu in order to create the map showing the state,
schools and some relevant metrics.

![Tableau_Tables_Marks](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Tableau_Tables_Marks.png)

The first thing we want to do is scroll down to the tabblock folder in
the Tables menu. Look for the "Geometry" file (it has a little globe
icon next to it).

![Add_Geometry](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Add_Geometry.png)

We want to drag and drop this Geometry file straight into the whitespace
under the Marks tab, doing this should generate a map of Illinois for
us. \*This may take a little time depending on your computer.

![Geometry_Map](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Geometry_Map.png)

Now that we have a map of the state, we can mark the schools and provide
relevant data.

Let's add other elements in the Marks tab to complete the visualization.

- Click on Sheet1 in the Tables menu.

- drag and place Geoid over the color box under Marks tab, to filter the
  Geoid's by color (though it may not be clear)

- drag and place \"School\" onto the Label box under Marks tab, this
  will mark the schools location on the map and show the appropriate
  labels.

This is what your map will look like for now:

![GEOID_School_Map](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/GEOID_School_Map.png)

Now let\'s go ahead and remove the null values, we should see a Geoid
menu on the right-side of the dashboard this will include colors and
null values, we want to remove nulls by clicking on the colored box to
the left of "Null" then selecting "Exclude"

![Exclude_Null](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Exclude_Null.png)

Now our map should show the schools in Illinois and exclude null values,
would look like this (The image below is zoomed in) :

![New_Map](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/New_Map.png)

Finally, we want to check SAT and ACT averages between these schools and
have them show up in the map.

To do this scroll to the "SchoolDemographics" under the Tables menu and
then drag and drop "SAT Average" and "ACT Average" over the tooltip
square under the Marks tab.

Now if we hover over a school in the map we can see information like the
average SAT and ACT scores as well as the GeoID.

![Final_Map](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Final_Map.png)

## Step 4: Exporting Tableau Sheets

Exporting these Tableau files will be important when it comes to sharing
the Tableau sheets to others. There are two methods when it comes to
exporting Tableau files, downloading the .twb file or adding your
visualization into the [Tableau Public
website](https://public.tableau.com/app/discover) under your account. We
will show you both methods.

<ins>Downloading .twb files:</ins>

1.  Click on "File" at the top of your computer and select "Save As\..."

![SaveAs](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/SaveAs.png)

2.  Fill in the name of your Tableau sheet and select where you would
    like the file saved onto your computer, then click "Save"

![RenameSaveAs](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/RenameSaveAs.png)

<ins>Posting your visualization to Tableau Public:</ins>

1.  Click on "File" at the top of your computer and select "Save to
    Tableau Public\..."

![Save_TableauPublic](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Save_TableauPublic.png)

2.  You will then be prompted to sign into your Tableau Public account

![TableauSignIn](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/TableauSignIn.png)

3.  Once you have signed in, the following popup will appear on your
    screen, do not click anything, a browser window will automatically
    open once this process is completed

![SavingWorkbook](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/SavingWorkbook.png)

4.  Your completed Demo workbook is now published onto Tableau Public.

![Map_TableauPublic](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/Map_TableauPublic.png)

- You can also click onto your account dashboard and the Tableau Sheet
  will appear there

![TableauPublic_Profile](/Reproducibility_Documents/Toy_Data_TableauSheet/images/Instructions_Linking_ToyData_Tableau_imgs/TableauPublic_Profile.png)
