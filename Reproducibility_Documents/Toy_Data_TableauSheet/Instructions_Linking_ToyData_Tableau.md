Instructions for creating Toy Data set specific Tableau sheets

To begin linking our toy data in Tableau, we need access to specific
software and files on your computer. First, ensure that Tableau Public
is installed on your machine. Please refer to the installation guide
[Installing_Tableau.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Installing_Tableau.docx?d=w7d347047f7124eb7a46f7fe31214c524&csf=1&web=1&e=NoUXyN)
for detailed instructions on this topic.

Once Tableau is installed, make sure you have the following files
downloaded to your computer:

[Student_Toy_data.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx?d=w69dfa650517a49639e6bc556a33a0a96&csf=1&web=1&e=wjWtAM)

[School_GEOID_Mapping.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Data_TableauSheets/School_GEOID_Mapping.xlsx?d=wf92676f0906d4231be0cdf2b9916f7bc&csf=1&web=1&e=bq25I5)

[tl_2023_17_tabblock20
folder](https://michiganstate.sharepoint.com/:f:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Data_TableauSheets/tl_2023_17_tabblock20?csf=1&web=1&e=7DQTca)

**Step 1: Adding our data sources into Tableau**

Open Tableau, we should see options to connect to a file, navigate to
the Connect drop-down menu and click on the Microsoft excel file option
as we want to connect our toy data set first, which is an excel sheet.

![](/media/image.png){width="5.260416666666667in"
height="2.5206167979002623in"}

Navigate to where you have the student toy data set saved onto your
computer and then click \"Open\" to open the file into Tableau.

![](/media/image2.png){width="4.219323053368329in"
height="2.3825535870516186in"}

Now the screen should look like this:

![](/media/image3.png){width="6.5in" height="3.7395833333333335in"}

From here we want to click Add next to connections and then add in our
other files.

1.  Click \"Add\" next to Connections to include more files.

![](/media/image4.png){width="3.8645833333333335in"
height="2.6321281714785654in"}

a.  Adding the School_GEOID_Mapping.xlsx

    - Click on "Add"

    - Select the "Microsoft Excel" option

    - Navigate to where you have the School_GEOID_Mapping.xlsx saved
      onto your computer

    - Select School_GEOID_Mapping.xlsx

    - Click \"Open"

![](/media/image5.png){width="6.5in" height="2.375in"}

b.  Add the Shape File (tabblock20.shp)

    - Click \"Add\" again.

    - Select \"Spatial File\" as the file type.

    - Navigate to the where you have the tabblock folder saved.

    - Select tabblock20.shp

    - Click "Open"

![](/media/image6.png){width="7.07659230096238in"
height="2.5062937445319333in"}

Once you have added all the data files into Tableau, you have completed
step 1, your connections pane should look like this:

![](/media/image7.png){width="2.708523622047244in"
height="1.8056824146981627in"}

**Step 2: Creating Links between Data Sources**

We want to connect the different data sources which we have added in the
previous step in order to build a map by leveraging relationships
between the data and connecting our files appropriately.

Clicking on an Excel file in our connections pane will display the
individual sheets within the file.

![](/media/image8.png){width="1.801415135608049in"
height="3.4166666666666665in"}

We want to start with
[School_GEOID_Mapping.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Data_TableauSheets/School_GEOID_Mapping.xlsx?d=wf92676f0906d4231be0cdf2b9916f7bc&csf=1&web=1&e=bq25I5)
and build connections from that file.

Start by clicking on School_GEOID_Mapping in the connections pane. There
should be a sheet named "Sheet 1". Drag Sheet 1 into the empty space on
the right.

![](/media/image9.png){width="4.958333333333333in"
height="3.36117782152231in"}

Next, click on Student_Toy_Data in the connections pane. There will be
multiple sheets in the dropdown menu. Add "SchoolDemographics" as a
connection to Sheet1 by dragging the sheet next to the already existing
connection on the right.

![](/media/imagea.png){width="4.059195100612423in" height="4.9375in"}

You can then set the relationship between the two files in the bottom
left

set School = School Name

![](/media/imageb.png){width="6.55924978127734in"
height="4.446415135608049in"}

After adding the SchoolDemographics sheet to the connections, we want to
add StudentSchoolPresence and StudentDemographics sheets to the
connections. Repeat the process above adding in StudentSchoolPresence
sheet first and then the StudentDemographics sheet afterwards.

\*The relationships between all of the sheets should automatically fill
out for the connections. Now our data source should look like this:

![](/media/imagec.png){width="6.5in" height="1.4583333333333333in"}

Finally, we want to add the spatial data connection. Click on the
tl_2023_17_tabblock20 in the connections pane. Then click on the
"tl_2023_17_tabblock20" file under files. Drag this file next to Sheet1,
a branch will begin to appear to create a connection between Sheet1 and
tl_2023_17_tabblock20.

![](/media/imaged.png){width="6.5in" height="4.333333333333333in"}

You will once again have to define the relationship

set Geoid = Geoid20.

![](/media/imagee.png){width="3.1157983377077865in"
height="3.0350437445319334in"}

This is what the connections should look like after finishing step 2:

![](/media/imagef.png){width="6.5in" height="4.083333333333333in"}

**Step 3: Creating the visualization**

Now we want to leverage our toy data to create the map, click on the new
sheet option at the bottom of the Tableau dashboard to get started with
creating the map, it should look like this:

![](/media/image10.png){width="6.5in" height="4.145833333333333in"}

From here we want to drag some variables from our Tables drop down menu
into our marks menu in order to create the map showing the state,
schools and some relevant metrics.

![](/media/image11.png){width="3.934796587926509in" height="5.0625in"}

The first thing we want to do is scroll down to the tabblock folder in
the Tables menu. Look for the "Geometry" file (it has a little globe
icon next to it).

![](/media/image12.png){width="1.5792771216097987in"
height="3.8645833333333335in"}

We want to drag and drop this Geometry file straight into the whitespace
under the Marks tab, doing this should generate a map of Illinois for
us. \*This may take a little time depending on your computer.

![](/media/image13.png){width="6.5in" height="5.4375in"}

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

![](/media/image14.png){width="6.5in" height="4.8125in"}

Now let\'s go ahead and remove the null values, we should see a Geoid
menu on the right-side of the dashboard this will include colors and
null values, we want to remove nulls by clicking on the colored box to
the left of "Null" then selecting "Exclude"

![](/media/image15.png){width="5.3125in" height="3.0308497375328085in"}

Now our map should show the schools in Illinois and exclude null values,
would look like this (The image below is zoomed in) :

![](/media/image16.png){width="4.066575896762904in"
height="3.8971347331583552in"}

Finally, we want to check SAT and ACT averages between these schools and
have them show up in the map.

To do this scroll to the "SchoolDemographics" under the Tables menu and
then drag and drop "SAT Average" and "ACT Average" over the tooltip
square under the Marks tab.

Now if we hover over a school in the map we can see information like the
average SAT and ACT scores as well as the GeoID.

![](/media/image17.png){width="6.5in" height="6.29166447944007in"}

**Step 4: Exporting Tableau Sheets**

Exporting these Tableau files will be important when it comes to sharing
the Tableau sheets to others. There are two methods when it comes to
exporting Tableau files, downloading the .twb file or adding your
visualization into the [Tableau Public
website](https://public.tableau.com/app/discover) under your account. We
will show you both methods.

Downloading .twb files:

1.  Click on "File" at the top of your computer and select "Save As\..."

![](/media/image18.png){width="3.1146369203849518in"
height="3.012755905511811in"}

2.  Fill in the name of your Tableau sheet and select where you would
    like the file saved onto your computer, then click "Save"

![](/media/image19.png){width="3.8649037620297464in"
height="2.1729352580927386in"}

Posting your visualization to Tableau Public:

1.  Click on "File" at the top of your computer and select "Save to
    Tableau Public\..."

> ![](/media/image1a.png){width="4.111750874890639in"
> height="3.9759853455818024in"}

2.  You will then be prompted to sign into your Tableau Public account

![](/media/image1b.png){width="2.90625in" height="3.8125in"}

3.  Once you have signed in, the following popup will appear on your
    screen, do not click anything, a browser window will automatically
    open once this process is completed

![](/media/image1c.png){width="5.09375in" height="1.46875in"}

4.  Your completed Demo workbook is now published onto Tableau Public.
    ![](/media/image1d.png){width="6.5in" height="3.5625in"}

- You can also click onto your account dashboard and the Tableau Sheet
  will appear there

![](/media/image1e.png){width="6.5in" height="3.4270833333333335in"}
