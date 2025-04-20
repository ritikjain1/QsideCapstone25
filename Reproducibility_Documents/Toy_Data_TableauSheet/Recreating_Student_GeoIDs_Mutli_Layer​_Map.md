# Recreating Student GeoIDs Multi-Layer Map 

<img width="624" alt="image" src="https://github.com/user-attachments/assets/5a570788-566c-4235-9b53-c83863bc86b3" />

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
dataset in the Instructions_Linking_ToyData_Tableau document (Steps 1 and 2). 

# Step 2: Creating our calculated field 

The next thing we do to recreate our map is to create a calculated field, so we can click through different variables to see different correlations. 

How we do this is first click on the little downwards arrow on the left-hand side next to the search icon and click create parameter. 

<img width="403" alt="image" src="https://github.com/user-attachments/assets/4e4950d6-9129-4ff6-b35e-757e94bf99c9" />

This will pop up a table to create your parameter, name it whatever you want, make the data type as string, and change the allowable values to list. After you change the allowable values to list, a table will pop up underneath. In this table you can add whatever variable from the toy data set that you want to compare with, however you have to make sure the value section is consistent with the name of the variable you want (e.g. SES in my value table is named “SES” in my to dataset). Below is how I did my parameters table, after you have recreated this, you can click ok. 

<img width="626" alt="image" src="https://github.com/user-attachments/assets/7f28c3a7-3636-46c4-801c-6b6b5c920500" />

After you created the parameter, click on the downward arrow again and now this time click on “create calculated field”.  

<img width="216" alt="image" src="https://github.com/user-attachments/assets/a084cd25-38c5-4cbb-8971-96d15b428414" />

Once the pop up comes up, you can name the field whatever (make sure you remember what it is called). For this we are coming up with a little script based on our parameters, below is a picture of my calculated field. The case is the parameter we created earlier, and a bunch of when and then statements based on the variables we added to the parameters. 

<img width="626" alt="image" src="https://github.com/user-attachments/assets/192c8ccd-24c4-4b42-9880-aa40edc0cc0c" />









