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

    ```{=html}
    <!-- -->
    ```
    -   Connecting your files (CSV and Shape)

        -   Open Tableau and go to the \"Connect\" pane.

        -   Click on \"Text File\" (since CSV is a text file).

![](/media/image.png){width="4.96875in" height="2.0in"}

-   Select the CSV file, in this demo, please open
    [demographic_acs_tract_2018-2022](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/demographic_acs_tract_2018-2022.csv?d=w3bb88045ad2a41768d21556d6a8445e5&csf=1&web=1&e=HC2n4r)
    and click Open.![](/media/image2.png){width="3.4895833333333335in"
    height="2.7604166666666665in"}

-   Tableau will automatically load the data into the Data Source tab.

![](/media/image3.png){width="5.072915573053368in"
height="3.4166666666666665in"}

-   To add in the Shapefiles-20250212T213902Z-001.zip, first open the
    .zip file

-   Click on "Add", then click "Spatial file"

![](/media/image4.png){width="3.7291666666666665in"
height="3.3541666666666665in"}

-   Add in
    "tract_shapes_2020.shp"![](/media/image5.png){width="4.520833333333333in"
    height="2.5208333333333335in"}

-   To add in the tract names, click on "Add" once again, then click
    > "Text file" and select "tract_names_2020.csv"

![](/media/image6.png){width="5.14583552055993in" height="2.9375in"}

-   If all the files were added correctly, your connections area should
    look like this

![](/media/image7.png){width="3.3645833333333335in"
height="5.33333552055993in"}

2.  Creating Connections throughout the different data sources

    -   Drag "tract_shapes_2020.shp" next to the
        "demographic_acs_tract\_\..." and create the connection. In this
        demo, we will be creating a connection via the GeoID.

![](/media/image8.png){width="4.458333333333333in"
height="4.458333333333333in"}

-   To get rid of the connection alert, you will need ensure that the
    GeoID type is a string for both files.

    -   To change the value types within the data sources, click onto
        the drop down to select the individual files

![](/media/image9.png){width="3.65625in" height="3.5729166666666665in"}

-   Click on "tract_shapes_2020.shp", click on value in the Type column
    associated with the GeoID row, then click on String.
    ![](/media/imagea.png){width="3.0520833333333335in"
    height="3.1770833333333335in"}

-   Repeat this process for the "demographic_acs_tract\..." file

> ![](/media/imageb.png){width="2.8333333333333335in"
> height="2.9479166666666665in"}

-   Drag in the "tract_names_2020.csv" into the connections pane,
    connecting it to "demographic_acs_tract\_\..." file

-   \*You will receive the same connection alert as before, follow the
    same steps by converting the GeoID into a string to get rid of it

-   Your connections chart should look like the one below
    ![](/media/imagec.png){width="5.75in" height="3.1458333333333335in"}

3.  Open a Blank Map

    -   Navigate to the \"Sheet 1\" tab that is located along the bottom

> ![](/media/imaged.png){width="4.604166666666667in"
> height="3.9166666666666665in"}

-   You will then see a blank sheet

> ![](/media/imagee.png){width="5.95833552055993in"
> height="2.8958333333333335in"}

4.  Adding in the elements to recreate the
    [Demo_StatePopulation.twb](https://michiganstate.sharepoint.com/:u:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Demo_StatePopulation.twb?csf=1&web=1&e=96qEx2)

    -   Drag the Latitude (generated) into the Rows section at the top
        and the Longitude (generated) into the Columns at the top. This
        will produce a blank map of the world

![](/media/imagef.png){width="6.5in" height="2.9479166666666665in"}

-   Drag the "State Name" over the Label Marker. This will show all the
    State abbreviations over their respective locations

![](/media/image10.png){width="5.58333552055993in"
height="2.6458333333333335in"}

-   Finally, drag "Population" over the color marker. This will make the
    color of each state reflect the population number for each state.
    You can then hover over each state with your mouse, and it will show
    the state name and the population number.

-   This is how the final Tableau sheet should appear, with the same
    functionalities.

![](/media/image11.png){width="5.83333552055993in" height="3.0in"}

Exporting Tableau files

Exporting these Tableau files will be important when it comes to sharing
the Tableau sheets to others. There are two methods when it comes to
exporting Tableau files, downloading the .twb file or adding your
visualization into the [Tableau Public
website](https://public.tableau.com/app/discover) under your account. We
will show you both methods.

Downloading .twb files:

1.  Click on "File" at the top of your computer and select "Save As\..."

![](/media/image12.png){width="3.4375in" height="3.1041666666666665in"}

2.  Fill in the name of your Tableau sheet and select where you would
    like the file saved onto your computer, then click "Save"

![](/media/image13.png){width="3.9375in" height="2.1875in"}

Posting your visualization to Tableau Public:

1.  Click on "File" at the top of your computer and select "Save to
    Tableau Public\..."

> ![](/media/image14.png){width="4.364583333333333in"
> height="3.9791666666666665in"}

2.  You will then be prompted to sign into your Tableau Public account

![](/media/image15.png){width="2.9166666666666665in"
height="3.8229166666666665in"}

3.  Once you have signed in, the following popup will appear on your
    screen, do not click anything, a browser window will automatically
    open once this process is completed

![](/media/image16.png){width="5.09375in" height="1.4791666666666667in"}

4.  Your completed Demo workbook is now published onto Tableau Public.

![](/media/image17.png){width="4.927083333333333in" height="2.875in"}

-   You can also click onto your account dashboard and the Tableau Sheet
    will appear there

> ![](/media/image18.png){width="4.322916666666667in"
> height="3.3958333333333335in"}

Now that you have Tableau downloaded, you can use the following sources
to learn more about the capabilities of Tableau and practice your
Tableau skills. <https://www.tableau.com/learn/training>
