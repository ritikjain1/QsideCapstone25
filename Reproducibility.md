# Qside's Reproducibility Documentation

This document provides a comprehensive guide to reproducing each figure
(mainly Tableau sheets) included in our project, detailing the steps,
code, and tools used. We include instruction files that outline how each
Tableau sheet was generated. Our documentation covers key aspects of the
project, starting with the creation of a **toy dataset**, including a
description of the process and the dataset itself. We then provide
instructions on **extracting geographic identifiers (GeoIDs) and
Longitude/Latitude coordinates** using a script that interacts with the
[U.S. Census Geocoder
API](https://geocoding.geo.census.gov/geocoder/geographies/address).
This allows others to replicate this step and extract GeoIDs and
Longitude/Latitude for other locations. Finally, we detail the process
of **loading both the toy dataset and the generated GeoIDs into
Tableau** to reproduce our visualizations, which maps school locations
and presents key metrics such as SAT averages and the number of
unexcused absences. Each figure in our project is accompanied by a
corresponding instruction file to ensure complete transparency and
reproducibility.

### <ins>The Toy Dataset</ins>

The toy dataset was created due to the lack of real data, serving as a
structured example to guide future data collection. It consists of five
Excel sheets covering student demographics, metadata, school
trajectories, school demographics, and attendance. The dataset includes
25 fictional students with attributes like name, address,
race/ethnicity, birthdate, siblings, socioeconomic status, and food
insecurity levels. It also incorporates data from six real Illinois
schools and 80 fake excused absence letters to simulate attendance
records.

Install Instructions:

[Installing_Excel.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Dataset/Installing_Excel.md)

[Sample_Excel.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Dataset/Sample_Excel.xlsx)

[ChatGPT_Setup.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Dataset/ChatGPT_Setup.md)

Reproducibility Documents:

\*Note that ChatGPT may give different names/values than what is
included in Qside's toy data. The process is still the same when
creating a toy dataset.\*


[Chatgpt_Prompts.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Dataset/About_QSIDEs_ToyData.md)

[Student_Toy_data.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx)

The toy dataset figures are used throughout various stages of our
project to illustrate data organization and analysis. Specifically,
snippets of the toy dataset appear in the [MVP
storyboard](https://michiganstate.sharepoint.com/:p:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Qside-CMSE495_MVP_Storyboard.pptx?d=w00b41b4390284164981b8d24a2f41113&csf=1&web=1&e=kZFDtu)
and [MVP storyboard
video](https://michiganstate.sharepoint.com/:v:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/QSIDE-CMSE495_MVP_Presentation_Video.mp4?csf=1&web=1&e=Y1v2sn),
where they help visualize the structure and application of our dataset.
Additionally, the dataset is integrated into multiple Tableau sheets
found on our Tableau Public:
<https://public.tableau.com/app/profile/ritik.jain1728/vizzes>

### <ins>Extracting GeoIDs using US Census API and Extracting Longitude and
Latitude Values</ins>

While working with the toy dataset, we identified the need to obtain
GeoIDs to accurately map schools in Tableau. Since our dataset included
school addresses, we developed a Python script that leveraged the [U.S.
Census Geocoder
API](https://geocoding.geo.census.gov/geocoder/geographies/address) to
retrieve these unique geographic identifiers. The script processed each
school's address, sent requests to the API, and extracted the GeoID from
the \"2020 Census Blocks\" section of the response. Once retrieved, the
GeoIDs were merged with sections of the original dataset and saved as an
Excel file, which is then used to create the Tableau visualizations.

While obtaining GeoIDs for mapping, we also needed to retrieve the
longitude and latitude coordinates for each school address. Using a
similar approach, we leveraged the [U.S. Census Geographies
API](https://geocoding.geo.census.gov/geocoder/geographies/address) to
extract these values. Our Python script processed each address, sent
requests to the API, and extracted the corresponding longitude and
latitude from the response. Once retrieved, these coordinates were
integrated into the dataset and used to accurately visualize school
locations on a Tableau map.

Install Instructions:

[Testing_US_Census_API.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/Testing_US_Census_API.md)

[Installing_USCensus_API.ipynb](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/Installing_USCensus_API.ipynb)

Reproducibility Documents:

[Instructions_using_API_ToyData.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/Instructions_using_API_ToyData.md)

[USCensus_APICode.ipynb](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/USCensus_APICode.ipynb)

[Student_Toy_data.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/Student_Toy_data.xlsx)

[School_GEOID_Mapping.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/School_GEOID_Mapping.xlsx)

The values gained from running these codes and adding onto our Toy Data
set are used to help map our toy data geographically onto Tableau.
Specifically, visualizations using the GeoID and Longitude/Latitude
values appear in the [MVP
storyboard](https://michiganstate.sharepoint.com/:p:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Qside-CMSE495_MVP_Storyboard.pptx?d=w00b41b4390284164981b8d24a2f41113&csf=1&web=1&e=kZFDtu)
and [MVP storyboard
video](https://michiganstate.sharepoint.com/:v:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/QSIDE-CMSE495_MVP_Presentation_Video.mp4?csf=1&web=1&e=Y1v2sn),
where they help visualize the different school locations onto a Tableau
map of Illinois. Additionally, the dataset is integrated into multiple
Tableau sheets found on our Tableau Public:
<https://public.tableau.com/app/profile/ritik.jain1728/vizzes>

### <ins>Installing Tableau</ins>

We are using Tableau to create visualizations that will help identify
geographical trends in school absences. By mapping school locations and
integrating key data points such as SAT averages and unexcused absences,
we aim to uncover patterns that may highlight disparities or areas
requiring intervention. To ensure our Tableau installations were set up
correctly and to familiarize ourselves with their features, we also
worked with example data, which mapped out the population of each state.
This allowed us to experiment with different visualization techniques,
explore Tableau's functionality, and refine our approach before
integrating our own dataset for analysis.

Install Instructions:

[Installing_Tableau.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Tableau/Installing_Tableau.md)

Reproducibility Documents:

[Instructions_Tableau_State_Population.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Tableau/Instructions_Tableau_State_Population.md)

[demographic_acs_tract_2018-2022.csv](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Tableau/demographic_acs_tract_2018-2022.xlsx)

[Shapefiles-20250212T213902Z-001.zip](https://github.com/ritikjain1/QsideCapstone25/tree/main/Reproducibility_Documents/Tableau/Shapefiles)

[Demo_StatePopulation_TableauPublic](https://public.tableau.com/app/profile/gabriella.stickney/viz/Demo_StatePopulation/Sheet1)

The Tableau practice visualization of the state populations is used in
our [MVP
storyboard](https://michiganstate.sharepoint.com/:p:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Qside-CMSE495_MVP_Storyboard.pptx?d=w00b41b4390284164981b8d24a2f41113&csf=1&web=1&e=Yg8jcB)
and our [MVP storyboard
video.](https://michiganstate.sharepoint.com/:v:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/QSIDE-CMSE495_MVP_Presentation_Video.mp4?csf=1&web=1&e=bU1dQj)

### <ins>Creating visualizations of the Toy Dataset in Tableau</ins>

Bringing together our toy dataset, the Census API for retrieving GeoIDs
and Longitudes/Latitudes, and Tableau for visualization, we have created
a Tableau sheet that displays key information from our toy dataset. The
sheet displays the location of the schools along with the information
regarding the school (Geoid, School Name, ACT Average, and Unexcused
Absences). This integration allows us to map school locations, analyze
trends in student absences, and incorporate relevant metrics.

Install Instructions:

[Installing_Tableau.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Tableau/Installing_Tableau.md)

Reproducibility Documents:

[Instructions_Linking_ToyData_Tableau.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Tableau/Instructions_Tableau_State_Population.md)

[tl_2023_17_tabblock20
folder](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Data_TableauSheet/Download_tl_2023_17_tabblock20.md)

[Student_Toy_data.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/Student_Toy_data.xlsx)

[School_GEOID_Mapping.xlsx](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/US_Census_API/School_GEOID_Mapping.xlsx)

[School_Mapping_TableauPublic](https://public.tableau.com/app/profile/ritik.jain1728/viz/Toydataset_17429213767350/Sheet2?publish=yes)

The visualizations created by following the above instructions appear in
the [MVP
storyboard](https://michiganstate.sharepoint.com/:p:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Qside-CMSE495_MVP_Storyboard.pptx?d=w00b41b4390284164981b8d24a2f41113&csf=1&web=1&e=kZFDtu)
and [MVP storyboard
video](https://michiganstate.sharepoint.com/:v:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/QSIDE-CMSE495_MVP_Presentation_Video.mp4?csf=1&web=1&e=Y1v2sn),
where they help visualize the different school locations onto a Tableau
map of Illinois. Additionally, the dataset is integrated into multiple
Tableau sheets found on our Tableau Public:
<https://public.tableau.com/app/profile/ritik.jain1728/vizzes>

Looking ahead, we plan to refine our Tableau visualizations and expand
our analysis as real data becomes available. Our goal is to develop an
interactive system where users can seamlessly upload CSV files, select
data visualization types such as bar charts, scatter plots, and pie
charts, and choose key attributes to analyze, including Student ID,
School ID, and Dates Absent. Additionally, we aim to enhance our Tableau
mapping capabilities by allowing users to personalize their
visualizations---adjusting filters, selecting data types, and setting
thresholds to highlight specific trends.
