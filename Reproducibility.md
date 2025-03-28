Qside's Reproducibility Documentation

This document provides a comprehensive guide to reproducing each figure
(mainly Tableau sheets) included in our project, detailing the steps,I
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

[The Toy Dataset]{.underline}

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

[Installing_Excel.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Installing_Excel.docx?d=wdc0506b050f24cf5827ef242fee686c3&csf=1&web=1&e=Ibozif)

[Sample_Excel.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Sample_Excel.xlsx?d=wc5dfca40a56c4996a52ce1a0148600e4&csf=1&web=1&e=JLuAaY)

[ChatGPT_Setup.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/ChatGPT_Setup.docx?d=w82b03c52807a4f64a68721c979ef55ec&csf=1&web=1&e=nqMv0v)

Reproducibility Documents:

\*Note that ChatGPT may give different names/values than what is
included in Qside's toy data. The process is still the same when
creating a toy dataset.\*

> [About_QSIDEs_ToyData.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/About_QSIDEs_ToyData.docx?d=w1c49109c774c40e19b0a9e191d09ebfb&csf=1&web=1&e=C3jQyh)

[Chatgpt_Prompts.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Chatgpt_Prompts.docx?d=w73865d9c968645f3b81d68fb55af4bfd&csf=1&web=1&e=n0HvET)

[Student_Toy_data.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx?d=w69dfa650517a49639e6bc556a33a0a96&csf=1&web=1&e=wjWtAM)

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

[Extracting GeoIDs using US Census API and Extracting Longitude and
Latitude Values]{.underline}

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

[Installing_USCensus_API.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/US_Census_API/Installing_USCensus_API.docx?d=w24fb23823330485897f4010cf6317797&csf=1&web=1&e=rth3IF)

[Test_USCensus_API.ipynb](https://michiganstate.sharepoint.com/:u:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/US_Census_API/Installing_USCensus_API.ipynb?csf=1&web=1&e=iOmOnS)

Reproducibility Documents:

[Instructions_using_API_ToyData.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/US_Census_API/Instructions_using_API_ToyData.docx?d=wb362f29c6e48491db88aa5437444ef9c&csf=1&web=1&e=fM7dTh)

> [USCensus_APICode.ipynb](https://michiganstate.sharepoint.com/:u:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/US_Census_API/USCensus_APICode.ipynb?csf=1&web=1&e=zwMeCJ)

[Student_Toy_data.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx?d=w69dfa650517a49639e6bc556a33a0a96&csf=1&web=1&e=wjWtAM)

[School_GEOID_Mapping.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/US_Census_API/School_GEOID_Mapping.xlsx?d=w150c6f9c082248128036b32da6ad0cb0&csf=1&web=1&e=XpIfir)

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

[Installing Tableau]{.underline}

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

[Installing_Tableau.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Installing_Tableau.docx?d=w7d347047f7124eb7a46f7fe31214c524&csf=1&web=1&e=NoUXyN)

Reproducibility Documents:

[Instructions_Tableau_State_Population.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Instructions_Tableau_State_Population.docx?d=w3df859ceac504313a95a8301dbaa01e5&csf=1&web=1&e=Y61m1y)

[demographic_acs_tract_2018-2022.csv](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/demographic_acs_tract_2018-2022.csv?d=w3bb88045ad2a41768d21556d6a8445e5&csf=1&web=1&e=M9hxk5)

[Shapefiles-20250212T213902Z-001.zip](https://michiganstate.sharepoint.com/:u:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Shapefiles-20250212T213902Z-001.zip?csf=1&web=1&e=kTcv9J)

[Demo_StatePopulation_TableauPublic](https://public.tableau.com/app/profile/gabriella.stickney/viz/Demo_StatePopulation/Sheet1)

The Tableau practice visualization of the state populations is used in
our [MVP
storyboard](https://michiganstate.sharepoint.com/:p:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Qside-CMSE495_MVP_Storyboard.pptx?d=w00b41b4390284164981b8d24a2f41113&csf=1&web=1&e=Yg8jcB)
and our [MVP storyboard
video.](https://michiganstate.sharepoint.com/:v:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/QSIDE-CMSE495_MVP_Presentation_Video.mp4?csf=1&web=1&e=bU1dQj)

[Creating visualizations of the Toy Dataset in Tableau]{.underline}

Bringing together our toy dataset, the Census API for retrieving GeoIDs
and Longitudes/Latitudes, and Tableau for visualization, we have created
a Tableau sheet that displays key information from our toy dataset. The
sheet displays the location of the schools along with the information
regarding the school (Geoid, School Name, ACT Average, and Unexcused
Absences). This integration allows us to map school locations, analyze
trends in student absences, and incorporate relevant metrics.

Install Instructions:

[Installing_Tableau.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Tableau/Installing_Tableau.docx?d=w7d347047f7124eb7a46f7fe31214c524&csf=1&web=1&e=NoUXyN)

Reproducibility Documents:

[Instructions_Linking_ToyData_Tableau.docx](https://michiganstate.sharepoint.com/:w:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Data_TableauSheets/Instructions_Linking_ToyData_Tableau.docx?d=w062efab906d044eda99fa6655a6f7855&csf=1&web=1&e=LgPGqP)

[tl_2023_17_tabblock20
folder](https://michiganstate.sharepoint.com/:f:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Data_TableauSheets/tl_2023_17_tabblock20?csf=1&web=1&e=7DQTca)

[Student_Toy_data.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx?d=w69dfa650517a49639e6bc556a33a0a96&csf=1&web=1&e=wjWtAM)

[School_GEOID_Mapping.xlsx](https://michiganstate.sharepoint.com/:x:/r/sites/Section_SS25-CMSE-495-001-225215054-EL-32-A26-QSIDE/Shared%20Documents/QSIDE/Project_deliverables/Reproducibility_Documents/Toy_Data_TableauSheets/School_GEOID_Mapping.xlsx?d=wf92676f0906d4231be0cdf2b9916f7bc&csf=1&web=1&e=bq25I5)

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
