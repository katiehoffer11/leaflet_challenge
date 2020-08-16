# Leaflet Homework - Visualizing Data with Leaflet

## Background

![1-Logo](Images/1-Logo.png)

### Your Mission

To give the class a break after projects, this assignment has been slightly amended. The solution has been provided to you, and your task is to analyze the code and explain a few component of the solution. Here are the topics to address:
1.	Briefly explain the logic for generating the base map.
   -Var map set where the base map will center and how far it will zoom in/out. graymap creates the tile layer that will be the background of our map

2.	Describe how the JSON was loaded and how was the data traversed. Explain how was the information from the JSON used to render data on the map.
   -The JSON is loaded in d3.json() and we use feature.properties.mag to retrieve the magnitude data in order to set the size and color of the markers. With the geoJson() we create circle markers based on the lat and lng from the JSON and build a popup to show the magnitude and location of the earthquake.

3.	Explain the logic for generating the circles and amending the size of them. What does this communicate?
   -The getRadius function determines the size (or radius) of the markers based on the magnitude of the earthquake. The larger the magnituted the larger the marker. A zero magnitude will return an error the function changes zero magnitude to 1.  The getColor function changes the color based on magnitude.
   
4.	Describe how the layer for the Tectonic plates was generated. 
   -The tectonic plate data is retrieved using the geoJSON() and then the data is added to the tectonicplates varibale which is added as a layer on the map


5.	What are the components in the layer control? How were they generated? 
   -The components of the layer control are the baseMaps group (satellitemap, Grayscale, Outdoors) and the overlays group (the tectonicplates and the earthquake markers). They are separate groups so that you can

6.	Explain the difference between the base map (tile layer) and the data layer(s).
   -They base map is one group of all the map styles and is mutually exclusive. With data layers you can select more than one at the same time. 

7.	Walk through the logic of how the legend was generated and rendered on the page.
   -The legend is created with var legend = L.control() where the position is set in the bottom right. The legend.onAdd = function() sets the color scale and legend is added to the map with legend.addTo(map)

### General Description

Welcome to the United States Geological Survey, or USGS for short! The USGS is responsible for providing scientific data about natural hazards, the health of our ecosystems and environment; and the impacts of climate and land-use change. Their scientists develop new methods and tools to supply timely, relevant, and useful information about the Earth and its processes. As a new hire, you will be helping them out with an exciting new project!

The USGS is interested in building a new set of tools that will allow them visualize their earthquake data. They collect a massive amount of data from all over the world each day, but they lack a meaningful way of displaying it. Their hope is that being able to visualize their data will allow them to better educate the public and other government organizations (and hopefully secure more funding..) on issues facing our planet.

### Before You Begin

1. Add a folder to your homework repository called `leaflet-challenge`.

2. Inside your local git repository, create a directory for the Leaflet challenge. Use the folder names to correspond to the challenges: **Leaflet-Step-1** and **Leaflet-Step-2**.

3. This homeworks utilizes both **html** and **Javascript** so be sure to add all the necessary files. These will be the main files to run for analysis.

4. Push the above changes to GitHub or GitLab.

## Your Task

### Level 1: Basic Visualization

![2-BasicMap](Images/2-BasicMap.png)

Your first task is to visualize an earthquake data set.

1. **Get your data set**

   ![3-Data](Images/3-Data.png)

   The USGS provides earthquake data in a number of different formats, updated every 5 minutes. Visit the [USGS GeoJSON Feed](http://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php) page and pick a data set to visualize. When you click on a data set, for example 'All Earthquakes from the Past 7 Days', you will be given a JSON representation of that data. You will be using the URL of this JSON to pull in the data for our visualization.

   ![4-JSON](Images/4-JSON.png)

2. **Import & Visualize the Data**

   Create a map using Leaflet that plots all of the earthquakes from your data set based on their longitude and latitude.

   * Your data markers should reflect the magnitude of the earthquake in their size and color. Earthquakes with higher magnitudes should appear larger and darker in color.

   * Include popups that provide additional information about the earthquake when a marker is clicked.

   * Create a legend that will provide context for your map data.

   * Your visualization should look something like the map above.

- - -

### Level 2: More Data 

![5-Advanced](Images/5-Advanced.png)

The USGS wants you to plot a second data set on your map to illustrate the relationship between tectonic plates and seismic activity. You will need to pull in a second data set and visualize it along side your original set of data. Data on tectonic plates can be found at <https://github.com/fraxen/tectonicplates>.

In this step we are going to..

* Plot a second data set on our map.

* Add a number of base maps to choose from as well as separate out our two different data sets into overlays that can be turned on and off independently.

* Add layer controls to our map.

- - -

### Assessment

Your final product will be assessed on the following metrics:

* The overall thoughtfulness, clarity, and completeness of your writeup

**Good luck!**

### Copyright

Trilogy Education Services © 2019. All Rights Reserved.
