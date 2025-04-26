# Recreating the Bar Plot 

**You can also download the [Final Tableau Storyboard workbook](https://gofile.io/d/qANdv6). Once downloaded, users can download the Tableau workbook and open it within Tableau Public.** 

The below steps are the steps that the team took in order to create the final workbook.

__________________________________________________________________________________________________________

<img width="627" alt="image" src="https://github.com/user-attachments/assets/e2c95191-3ceb-4df7-aa9c-3b67bd7c379c" />

To begin, make sure you have successfully installed Tableau Public following these instructions: [Install_Instructions.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Deliverables/Install_Instructions.md)

Once Tableau is installed, you will want to begin by linking our toy data in Tableau, we need access to specific
software and files on your computer. 

Once Tableau is installed, make sure you have the following files
downloaded to your computer:

[Student_Toy_data.xlsx](/Reproducibility_Documents/Toy_Dataset/Student_Toy_data.xlsx)

[School_GEOID_Mapping.xlsx](/Reproducibility_Documents/Toy_Data_TableauSheet/School_GEOID_Mapping.xlsx)

[tl_2023_17_tabblock20
folder](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Data_TableauSheet/Download_tl_2023_17_tabblock20.md)

# Step 1: Adding and linking our data
Our first step to recreate this map is adding our data into Tableau and linking them together based on a common ID. We have documentation on how we add and link out
dataset in the [Instructions_Linking_ToyData_Tableau](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Data_TableauSheet/Instructions_Linking_ToyData_Tableau.md) document (Steps 1 and 2). 

# Step 2: Creating our calculated field 
The next thing we do to recreate our map is to create a calculated field, so we can click through different variables to see different correlations. We have documentation on how to create a calculated field in the [Recreating_Student_GeoIDs_Mutli_Layer_Map.md](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Data_TableauSheet/Recreating_Student_GeoIDs_Mutli_Layer%E2%80%8B_Map.md) document (Step 2). 

# Step 3: Creating the Visualization 

First thing I did is I dragged school name to the column section at the top, and then I took the example field that we made earlier (step 2) and dragged the count of the field to the columns section, and dragged the same field with no count to the rows section, like this:

<img width="635" alt="image" src="https://github.com/user-attachments/assets/c9a8f843-7e95-494f-898e-0c56a07e04be" />

Next step in the “marks” column, add the example field as the color and school name as the detail, like this:  

<img width="625" alt="image" src="https://github.com/user-attachments/assets/50d0f1da-25f4-4876-b583-c68e2f8f77d5" />

Lastly add school name to the filters tab. Then to add an interactive view for this plot, hover over the “school name” field in the filter tab and the example parameter on the left-hand side, click the drop down and click on show filter to be able to add an interactive plot. Now you should have the full plot recreated. 

<img width="626" alt="image" src="https://github.com/user-attachments/assets/0224cbc5-5b52-4512-9898-cbf8afb0444b" />

<img width="623" alt="image" src="https://github.com/user-attachments/assets/9d44f851-edbb-4d64-958a-b406aa84b1e9" />

<img width="626" alt="image" src="https://github.com/user-attachments/assets/eb8c9046-9461-4821-a6d7-f76959d5edff" />

<img width="626" alt="image" src="https://github.com/user-attachments/assets/d15b1bbb-ad3b-43c3-a760-814410d515ee" />








