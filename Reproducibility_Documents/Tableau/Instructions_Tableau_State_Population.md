Now that you have installed Tableau, you can reproduce our testing
tableau sheet
[Demo_StatePopulation_TableauPublic.](https://public.tableau.com/app/profile/gabriella.stickney/viz/Demo_StatePopulation/Sheet1)
This simple tableau sheet displays the population of each state.

1.  Loading a Blank Map and Adding CSV Files and Shape Files

    -   Download
        [demographic_acs_tract_2018-2022](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/demographic_acs_tract_2018-2022.csv?d=w3bb88045ad2a41768d21556d6a8445e5&csf=1&web=1&e=HC2n4r)
        and
        [Shapefiles-20250212T213902Z-001.zip](https://michiganstate.sharepoint.com/:u:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Shapefiles-20250212T213902Z-001.zip?csf=1&web=1&e=8bATvS)
        which was provided


    -   Connecting your files (CSV and Shape)

        -   Open Tableau and go to the \"Connect\" pane.

        -   Click on \"Text File\" (since CSV is a text file).

  ![TextFile](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/TextFile.png)

-   Select the CSV file, in this demo, please open
    [demographic_acs_tract_2018-2022](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/demographic_acs_tract_2018-2022.csv?d=w3bb88045ad2a41768d21556d6a8445e5&csf=1&web=1&e=HC2n4r)
    and click Open.
    
      ![Select_Demographic_File](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Select_Demographic_File.png)

-   Tableau will automatically load the data into the Data Source tab.

  ![ConnectionPane1](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/ConnectionPane1.png)

-   To add in the Shapefiles-20250212T213902Z-001.zip, first open the
    .zip file

-   Click on "Add", then click "Spatial file"

  ![Add_SpatialFile](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Add_SpatialFile.png)

-   Add in
    "tract_shapes_2020.shp"
      ![Select_ShapeFile](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Select_ShapeFile.png)

-   To add in the tract names, click on "Add" once again, then click "Text file" and select "tract_names_2020.csv"

  ![Select_TractNameFile](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Select_TractNameFile.png)

-   If all the files were added correctly, your connections area should
    look like this

  ![Tiny_ConnectionPane](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Tiny_ConnectionPane.png)

2.  Creating Connections throughout the different data sources

    -   Drag "tract_shapes_2020.shp" next to the
        "demographic_acs_tract\_\..." and create the connection. In this
        demo, we will be creating a connection via the GeoID.

  ![ConnectionPane2](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/ConnectionPane2.png)

-   To get rid of the connection alert, you will need ensure that the
    GeoID type is a string for both files.

    -   To change the value types within the data sources, click onto
        the drop down to select the individual files

  ![Change_ConnectPane_File](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Change_ConnectPane_File.png)

-   Click on "tract_shapes_2020.shp", click on value in the Type column
    associated with the GeoID row, then click on String.

  ![Change_to_String](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Change_to_String.png)

-   Repeat this process for the "demographic_acs_tract\..." file

  ![Change_to_String2](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Change_to_String2.png)

-   Drag in the "tract_names_2020.csv" into the connections pane,
    connecting it to "demographic_acs_tract\_\..." file

-   \*You will receive the same connection alert as before, follow the
    same steps by converting the GeoID into a string to get rid of it

-   Your connections chart should look like the one below

      ![Connections_Tree](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Connections_Tree.png)

3.  Open a Blank Map

    -   Navigate to the \"Sheet 1\" tab that is located along the bottom

  ![Move_to_Sheet1](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Move_to_Sheet1.png)

    -   You will then see a blank sheet

  ![BlankSheet](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/BlankSheet.png)

4.  Adding in the elements to recreate the
    [Demo_StatePopulation.twb](https://public.tableau.com/app/profile/gabriella.stickney/viz/Demo_StatePopulation/Sheet1)

    -   Drag the Latitude (generated) into the Rows section at the top
        and the Longitude (generated) into the Columns at the top. This
        will produce a blank map of the world

  ![Add_LongLat](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Add_LongLat.png)

-   Drag the "State Name" over the Label Marker. This will show all the
    State abbreviations over their respective locations

  ![Add_StateName](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Add_StateName.png)

-   Finally, drag "Population" over the color marker. This will make the
    color of each state reflect the population number for each state.
    You can then hover over each state with your mouse, and it will show
    the state name and the population number.

-   This is how the final Tableau sheet should appear, with the same
    functionalities.

  ![Add_Population](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Add_Population.png)

### Exporting Tableau files

Exporting these Tableau files will be important when it comes to sharing
the Tableau sheets to others. There are two methods when it comes to
exporting Tableau files, downloading the .twb file or adding your
visualization into the [Tableau Public
website](https://public.tableau.com/app/discover) under your account. We
will show you both methods.

<ins>Downloading .twb files: </ins>

1.  Click on "File" at the top of your computer and select "Save As\..."

  ![Tableau_SaveAs](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Tableau_SaveAs.png)

2.  Fill in the name of your Tableau sheet and select where you would
    like the file saved onto your computer, then click "Save"

  ![Tableau_Rename_Save](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Tableau_Rename_Save.png)

<ins>Posting your visualization to Tableau Public: </ins>

1.  Click on "File" at the top of your computer and select "Save to
    Tableau Public\..."

  ![Save_to_TableauPublic](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Save_to_TableauPublic.png)

2.  You will then be prompted to sign into your Tableau Public account

  ![TableauPublic_Signin](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/TableauPublic_Signin.png)

3.  Once you have signed in, the following popup will appear on your
    screen, do not click anything, a browser window will automatically
    open once this process is completed

  ![Saving_TableauPublic](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Saving_TableauPublic.png)

4.  Your completed Demo workbook is now published onto Tableau Public.

  ![Published_Workbook](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/Published_Workbook.png)

-   You can also click onto your account dashboard and the Tableau Sheet
    will appear there

  ![TableauProfile](/Reproducibility_Documents/Tableau/images/Tableau_StatePop_imgs/TableauProfile.png)

Now that you have Tableau downloaded, you can use the following sources
to learn more about the capabilities of Tableau and practice your
Tableau skills. <https://www.tableau.com/learn/training>
