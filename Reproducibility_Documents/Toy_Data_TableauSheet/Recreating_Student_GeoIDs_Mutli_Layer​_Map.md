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
dataset in the [Instructions_Linking_ToyData_Tableau](https://github.com/ritikjain1/QsideCapstone25/blob/main/Reproducibility_Documents/Toy_Data_TableauSheet/Instructions_Linking_ToyData_Tableau.md) document (Steps 1 and 2). 

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

One you have created this calculated field, you can click “ok” and it should show up in the tables section. Now you have this field that you can use on any map you would like. 

# Step 3: Creating our Visualizations  

Now we want to leverage our toy data to create the map, click on the new sheet option at the bottom of the Tableau dashboard to get started with creating the map, it should look like this  

<img width="627" alt="image" src="https://github.com/user-attachments/assets/443a0987-f44f-4591-a0f3-9fed3e98ca6c" />

From here we want to drag some variables from our Tables drop down menu into our marks menu in order to create the map showing the state, schools and some relevant metrics. 

<img width="215" alt="image" src="https://github.com/user-attachments/assets/3e8eea37-3010-4856-8d24-6f4431d3888b" />

From the “tl_2023_17_tabblock20.shp” table, get the geometry variable (which is a spatial file) and drag it into the marks column. When you do that, a map of Illinois should show up, the map is split into little block sections. 

<img width="621" alt="image" src="https://github.com/user-attachments/assets/5bfa425c-cd1c-4388-926f-5ffd274d935c" />

<img width="616" alt="image" src="https://github.com/user-attachments/assets/57ed2a40-99fe-4dc5-bcc2-1b460e90d492" />

After you have created the map, go into the table that has the student geo IDS (in my case its Sheet 1) and drag the Geoid variable into the color marks and click “add all members” when the pop up appears:

<img width="588" alt="image" src="https://github.com/user-attachments/assets/b2c87c3d-a90d-404c-b97f-ce085ede2ca8" />

Now the legend on the right side should appear, from that legend please click on null and select exclude values like this: 

<img width="628" alt="image" src="https://github.com/user-attachments/assets/18d933d8-784f-4c3c-b971-a77ff1d5ecbc" />

Now your map should look like this (exclude no match found as well if it comes up): 

<img width="628" alt="image" src="https://github.com/user-attachments/assets/a31acd98-e19a-4d81-9123-377a00c20e34" />

Next to make a multi-layer map, take the latitude (generated) varaible in the left-hand side and drag it to the rows. From there a weird 2-layer map will appear, to combine them into 1 map, click the drop-down menu and click dual axis.  

<img width="533" alt="image" src="https://github.com/user-attachments/assets/d06282f1-b194-4540-9644-47a7e7426a55" />

<img width="626" alt="image" src="https://github.com/user-attachments/assets/3e4f1ac5-426b-45e8-b438-f6986b09b2f7" />

Now that we have one map we can start recreating it. On the left side, you can now see that there are 2 “Latitude (generated)” icons and an “all” icon, click on the “all” icon and drag the student Geo ID onto detail (this is essential to be able to get variables based on the geo ID). 

<img width="331" alt="image" src="https://github.com/user-attachments/assets/4adf2347-e2ac-49f6-ba80-b2a7a291ee7c" />

Next click on the first “Latitude (generated)” icon and drag unexcused absences to the color icon. Make sure you get the average unexcused absence as well. How you do this is when you hover the unexcused absences variable in the marks area, click the upside-down triangle and click measure and change it to average. In the tool tip ypu can add whatever variable you want to see when you hover over block, I chose the count of student ids in the block and the average stable living situation in that area. 

<img width="353" alt="image" src="https://github.com/user-attachments/assets/3cecd571-78fa-4ad5-a577-0aa96279f85f" />

<img width="444" alt="image" src="https://github.com/user-attachments/assets/a8a83812-d855-469c-9790-40d4d572b83e" />

To change the color of the map, click on the color icons and press edit colors. From there we can choose any color we want to visualize it; however, I chose from green to red. 

<img width="476" alt="image" src="https://github.com/user-attachments/assets/3e8f7108-e56b-4901-bfbb-a7d402ab99c3" />

<img width="608" alt="image" src="https://github.com/user-attachments/assets/b27e17e3-af2f-4b1d-8815-7d51ab0d1b7e" />

Now go into the second “Latitude (Generated)” icon. From the dropdown right above the color, size and label icons, change the way you see the geoid from automatic to circle. This will create a point so we can compare the unexcused absences from the area to the variables we want. 

<img width="263" alt="image" src="https://github.com/user-attachments/assets/b31b96e7-5179-4bbb-b5e0-19e7c6a3f96f" />

<img width="268" alt="image" src="https://github.com/user-attachments/assets/241be687-5a95-4012-9511-67630c1095e0" />

Next, we drag the calculated field we created earlier (e.g. mine is called “Example Field”) and drag it to the color icon so the points will be colored by the metric. Now you can drag whatever variable in the tool tip that you want to see when you hover over the point (I added the count of student ID and average excused absence. I also added Geoid and School name to the filters box right above the marks box. 

<img width="628" alt="image" src="https://github.com/user-attachments/assets/5cdade53-806c-4e91-9931-534422390b9d" />

<img width="624" alt="image" src="https://github.com/user-attachments/assets/c37a4c07-ea49-4f09-aa75-2cf0ebca07f5" />

The last thing you must do to recreate this map is to add an interactive way to filter the map or go through different metrics. You do this by first clicking on the dropdown from the “example” parameter and click on show filter. Do the same things for “school name” in the filter box and the “Example Field” in the marks box. You can adjust how the map looks based on personal preference. You will now get an interactive map where you can compare different variables to unexcused absences. 

<img width="627" alt="image" src="https://github.com/user-attachments/assets/49014799-acce-45ce-8e83-c062661c59d4" />

<img width="624" alt="image" src="https://github.com/user-attachments/assets/49c52e42-bf22-4902-a19a-5d9ca1240173" />


















