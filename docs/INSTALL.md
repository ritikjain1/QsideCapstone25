# Instructions for Using OSMnx Package (OSM API)
## Utilizing the OSMnx package
The OSMnx package is a python interface for visualizations and analysis of OpenStreetMap networks. We use this package concurrently with the Folium package to effectively create visualizations for our project. 


## Introduction to OSMnx
In this section we will set up and install the necessary elements needed to properly utilize the OSMNX package.

**You can follow along in the jupyter notebook file provided separately titled osmapi.ipynb in the [following directory: ](/src/osmapi.ipynb)**

      ```
      pip install osmnx folium
      
      import folium
      import osmnx as osm 
      
      
   First, we will use "pip install" to install osmnx and folium. These are the necessary packages needed in this tutorial. 

## Defining Graphs given an Area of Interest
   
   Once you have imported the necessary packages we can move onto methodology and define an area of interest. In these install instructions, we use Lansing, Michigan, USA.
      
      area_1 = "Lansing, Michigan, USA"
   We can create a graph of our area of interest using the graph_from_place() method 
      
      graph = osm.graph_from_place(area_1, network_type='all')
      
   We can plot the graph using the plot_graph() method
      
      osm.plot_graph(osm.project_graph(graph))

## Final Plot of Specified Amenities given an Area of Interest
      
   If we want to get certain amenities such as hospitals in the area of interest we can define these in the tags below
      
      tags = {'amenity': 'hospital'}
      
      hospitals = osm.features_from_place(area_1, tags)
      
      hospitals.plot()
   This produces a plot of the hospitals in Lansing. 
## Number of Amenities in an Area of Interest

In order to find the number of hospitals within Lansing, we can find the length of the hospitals attribute we created earlier. 

      num_hosp = len(hospitals)
      print("There are", num_hosp, "hospitals in Lansing, Michigan as shown in the plot above.")

## Conclusion
   Overall this package has a lot of attributes that are useful for visualization and analysis. In this tutorial, we are able to visualize the hospitals within Lansing. Along with hospitals, there are a multitude of different amenities that this package can measure. OSMnx is a very useful way to utilize OpenStreetMap!
   
      
      
## References
[ChatGPT Prompt: "I am wondering how to use Open Street Map's api in jupyter?"](https://chatgpt.com)
[OpenStreetMap OSMnx Documentation](https://osmnx.readthedocs.io/#:~:text=OSMnx%20is%20a%20Python%20package,then%20analyze%20and%20visualize%20them.)









      
