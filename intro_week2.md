Week 2: Introduction to Geospatial Operations with GeoPandas

Week 2 Focus: This week introduces geospatial operations using Python, particularly with the GeoPandas library. We will focus on manipulating geometries (such as points, lines, and polygons), buffering, and performing spatial joins. This week's labs continue to use the Nigerian dataset of cities and include a new dataset of state boundaries in Nigeria.
Objectives:
By the end of this week, students should be able to:
Understand and work with basic geometries (Points, Polygons, etc.).
Apply buffering operations to create zones around points and polygons.
Perform spatial joins to analyze relationships between geospatial datasets.

Topics Covered:
Introduction to Geometry Types:
Create and manipulate points, lines, and polygons.
Understand the use of geospatial geometries to represent real-world features.
Buffering Operations:
Learn how to create buffers around geometries, such as cities and state boundaries.
Understand how buffering can be used in proximity analysis and other spatial analyses.
Spatial Joins:
Perform spatial joins to combine datasets based on their spatial relationships.
Understand how spatial joins can help answer questions about which geometries lie within or intersect other geometries.

Lab Setup:
Data for Week 2:
Nigerian Cities Dataset: CSV file containing cities, their latitude, longitude, population, etc.
Nigerian State Boundaries Dataset: A shapefile (nigerian_states.shp) containing the boundaries of Nigerian states.
Both datasets should be uploaded to your working environment (e.g., Google Colab or Jupyter Notebook).
Packages to Install:
Before starting the labs, make sure the following packages are installed:
bash
# Install necessary libraries for geospatial operations
!pip install geopandas
!pip install matplotlib


Lab 1: Working with Geometries (Points, Lines, and Polygons)

Objective: In this lab, students will work with basic geospatial geometries (Points, Lines, and Polygons) using the GeoPandas library. Students will learn how to represent cities and state boundaries using these geometries.

Instructions:
Create Point geometries for some cities in Nigeria.
Create a simple Polygon to represent a state boundary.
Visualize the geometries using the matplotlib library.

Expected Learning Outcomes:
Understand how to represent geospatial data as points, lines, and polygons.
Be able to manipulate and visualize these geometries using Python.

Lab 2: Buffering Points and Polygons

Objective: This lab focuses on buffering operations around points (representing cities) and polygons (representing state boundaries). Students will learn how to apply buffers to geometries and visualize the results.

Instructions:
Buffer the cities by a distance of 50 km to create zones around each city.
Buffer the state boundary polygon by a distance of 100 km.
Visualize both the original and buffered geometries to compare them.

Expected Learning Outcomes:
Understand the concept of buffering in GIS.
Be able to apply buffer operations to points and polygons.
Understand the use of buffering in proximity analysis.

Lab 3: Spatial Joins with GeoPandas

Objective: This lab introduces the concept of spatial joins, where datasets are joined based on their spatial relationships. Students will perform a spatial join to find which cities fall within a buffer zone created around a state boundary.

Instructions:
Perform a spatial join between the cities dataset and the buffered state boundary to find cities that are within the 100 km buffer zone.
Identify the cities that fall within this buffer.
Visualize the results to highlight which cities are located inside the buffer zone.

Expected Learning Outcomes:
Understand how to perform spatial joins to analyze the spatial relationships between datasets.
Be able to apply spatial joins to answer real-world spatial questions.




Summary:
In Week 2, you will gain hands-on experience in manipulating geospatial data using GeoPandas. These foundational skills will allow you to perform more advanced spatial analyses in future labs. The focus on simplicity ensures that even complex topics like buffering and spatial joins are accessible to all students.
By the end of Week 2, you should:
Understand the basics of geospatial geometries.
Be comfortable applying buffer operations to points and polygons.
Be able to perform spatial joins to combine datasets based on spatial relationships.
Next week, we will build on these skills by introducing more complex spatial analyses, including overlays and proximity analysis.

