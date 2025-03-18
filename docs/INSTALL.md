# Instructions for Using OpenStreetMap API (The OSMnx Package)
## Utilizing the OSMnx package
The OSMnx package is a python interface for accessing OpenStreetMap's API. We can use this package concurrently with the Folium package to effectively use this tool for our project. 


## Introduction to OSMnx
In this section we will set up and install the necessary elements needed to use the OSMNX package in accordance with the Folium package

**You can follow along in the jupyter notebook file provided separately titled OSMAPI.ipynb**

      ```
      pip install osmnx folium
      
      import folium
      import osmnx as osm 
      
      
   Once you have imported the necessary packages we can move onto methodology and define an area of interest. In these install instructions, we use Lansing, Michigan, USA.
      
      area_1 = "Lansing, Michigan, USA"
   We can create a graph of our area of interest using the graph_from_place() method 
      
      graph = osm.graph_from_place(area_1, network_type='all')
      
      
   We can plot the graph using the plot_graph() method
      
      osm.plot_graph(osm.project_graph(graph))
      
   If we want to get certain amenities such as hospitals in the area of interest we can define these in the tags below
      
      tags = {'amenity': 'hospital'}
      
      hospitals = osm.features_from_place(area_1, tags)
      
      hospitals.plot()
   This produces a plot of the hospitals in Lansing. 
      
      
## References
[ChatGPT Prompt: "I am wondering how to use Open Street Map's api in jupyter?"](https://chatgpt.com)









      
