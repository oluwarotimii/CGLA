Here’s a well-structured format for your Week 1 course module on "Introduction to GIS and Python Programming." 

---

# Week 1: Introduction to GIS and Python Programming

## Objective
The goal of Week 1 is to introduce participants to the basics of GIS and Python programming, laying a strong foundation for the more advanced geospatial analysis to come. This week will cover the fundamental concepts of GIS, essential Python programming constructs, and a hands-on exploration of Nigerian geospatial data.

## Theory

### Introduction to GIS
- **What is GIS?**  
  Geographic Information Systems (GIS) are systems designed to capture, store, manipulate, analyze, manage, and present all types of geographic data. GIS helps users visualize spatial data in the form of maps, analyze geographical patterns, and perform location-based queries.

- **Basic GIS Concepts:**
  - **Spatial Data:** Information about the physical location and shape of objects (features) on Earth. Spatial data is categorized into two types:
    - **Vector Data:** Represents features as points, lines, or polygons.
    - **Raster Data:** A grid of cells or pixels, typically used to represent continuous data (e.g., elevation, temperature).
  - **Attribute Data:** Information that describes the characteristics of spatial features.

- **GIS Applications in Nigeria:**
  - Urban planning and land management (e.g., Lagos and Abuja).
  - Environmental monitoring (e.g., deforestation in Cross River).
  - Disaster management (flood mapping in states like Bayelsa).

- **How Python Fits into GIS:**  
  Python is commonly used in GIS because of its ability to handle large datasets, automate workflows, and perform complex analyses. Libraries like Geopandas, Shapely, and Geemap make Python a powerful tool for GIS professionals.

### Installing Required Packages
To set up the environment for this week’s labs, you need to install several Python packages. You can do this directly in your Google Colab notebook by running the following commands:

```python
# Install necessary libraries
!pip install pandas geopandas matplotlib
!pip install shapely
!pip install geemap
```
**Note:** If you're using a local Jupyter Notebook or Python environment, omit the exclamation mark `!` at the beginning of each command.

### Introduction to Python for GIS
- **Why Python for GIS:**  
  Python is a versatile programming language that allows for powerful data analysis, making it suitable for spatial data manipulation and visualization.

- **Python Essentials:**
  - Data types: Integers, floats, strings, lists, and dictionaries.
  - Control structures: If-else conditions, loops (for and while).
  - Functions: How to create and use functions in Python.
  - Working with libraries: Introduction to Pandas and Geopandas for data manipulation.

- **Setting Up the Python Environment:**
  - Using Google Colab for cloud-based Python programming.
  - Installing and importing essential Python libraries (e.g., Pandas, Geopandas, Matplotlib).

## Labs
The labs in Week 1 are designed to progressively introduce Python programming and geospatial data handling with real Nigerian examples. Each lab will have step-by-step instructions, followed by a reflection and assessment.

### Lab 1: Exploring Nigerian City Data with Pandas
**Objective:**  
Introduce participants to basic data handling using Python’s Pandas library by exploring a dataset of Nigerian cities.

**Dataset:**  
A CSV file containing a list of Nigerian cities, including their names, population, latitude, and longitude.

**Steps:**
1. Load the CSV file into Pandas.
2. Inspect the dataset to understand its structure (columns, data types, etc.).
3. Filter cities with populations above 1 million.
4. Sort the dataset by population.
5. Display basic statistics about the dataset (e.g., average population).

**Code Example:**
```python
import pandas as pd

# Load the dataset
cities_df = pd.read_csv('nigerian_cities.csv')

# Inspect the dataset
print(cities_df.head())

# Filter cities with population over 1 million
large_cities = cities_df[cities_df['population'] > 1000000]

# Sort by population
large_cities_sorted = large_cities.sort_values(by='population', ascending=False)

# Basic statistics
print(large_cities_sorted.describe())
```

**Expected Output:**  
A table showing cities with populations greater than 1 million, sorted in descending order of population.

**Reflection:**
- What insights can you draw from this dataset?
- How do large cities in Nigeria compare in terms of population?

### Lab 2: Plotting Nigerian Cities on a Map
**Objective:**  
Learn to visualize geographic data by plotting the Nigerian cities on a map using Matplotlib and basic Python plotting functions.

**Steps:**
1. Use the Matplotlib library to create a scatter plot of Nigerian cities based on their latitude and longitude.
2. Customize the plot by adding labels for each city and adjusting marker sizes based on population.

**Code Example:**
```python
import matplotlib.pyplot as plt

# Extract latitude, longitude, and population
latitudes = cities_df['latitude']
longitudes = cities_df['longitude']
populations = cities_df['population'] / 100000  # Scale population for marker size

# Create a scatter plot
plt.figure(figsize=(10, 8))
plt.scatter(longitudes, latitudes, s=populations, c='blue', alpha=0.5)

# Add labels and title
plt.title('Nigerian Cities')
plt.xlabel('Longitude')
plt.ylabel('Latitude')

# Show the plot
plt.show()
```

**Expected Output:**  
A scatter plot with Nigerian cities, where marker size corresponds to population size.

**Reflection:**
- Which cities are geographically clustered?
- How does the size of the marker (population) compare across cities?

### Lab 3: Loading and Visualizing Nigerian State Boundaries
**Objective:**  
Introduce participants to handling vector data in Geopandas by visualizing Nigerian state boundaries.

**Dataset:**  
Shapefile containing Nigerian state boundaries.

**Steps:**
1. Load the Nigerian state boundaries shapefile into a GeoDataFrame using Geopandas.
2. Plot the boundaries of Nigerian states.
3. Overlay the city dataset from Lab 1 on top of the state boundaries.

**Code Example:**
```python
import geopandas as gpd

# Load the shapefile
nigeria_states = gpd.read_file('NGA_adm2.shp')

# Plot Nigerian states
nigeria_states.plot(figsize=(10, 8), color='lightgrey', edgecolor='black')

# Show the plot
plt.title('Nigerian State Boundaries')
plt.show()

# To overlay the cities:
from shapely.geometry import Point

# Convert the cities DataFrame to a GeoDataFrame
cities_df['geometry'] = cities_df.apply(lambda x: Point((x['longitude'], x['latitude'])), axis=1)
cities_gdf = gpd.GeoDataFrame(cities_df, geometry='geometry')

# Plot states and cities together
base = nigeria_states.plot(figsize=(10, 8), color='lightgrey', edgecolor='black')
cities_gdf.plot(ax=base, marker='o', color='red', markersize=5)
plt.title('Nigerian Cities and State Boundaries')
plt.show()
```

**Expected Output:**  
A map of Nigerian states with cities overlaid as red markers.

**Reflection:**
- What spatial relationships can be observed between the cities and state boundaries?
- How evenly are large cities distributed across Nigeria?

## Assessment for Week 1
At the end of Week 1, students will submit a report containing:
- A summary of their exploration of Nigerian city data in Lab 1.
- A customized map of Nigerian cities from Lab 2.
- A map showing Nigerian state boundaries with city data overlaid from Lab 3.

---

Feel free to adjust any section as necessary for your course needs!