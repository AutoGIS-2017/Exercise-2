# Exercise 2

This week we will focus on how to create geometries in Geopandas.

### Due dates
 
 - 100 % of point total if you return your solution within 1 week (due date 14.11.2016) 
 - 85 % of point total if your return your solution within 2 weeks (due date 21.11.2016)
   - Detailed hints provided
 - 50 % of point total if you return your solution within 3 weeks (due date 28.11.2016)
   - Full solution provided

## Sections

 - [Problem 1: Create Polygon from lists of coordinates](#problem-1-create-polygon-from-lists-of-coordinates)
 - [Problem 2: Points to map](#problem-2-points-to-map)
 - [Problem 3: Movements of individual user (optional task for advanced students)](#problem-3-movements-of-individual-user-optional-task-for-advanced-students)
  
## Problem 1: Create Polygon from lists of coordinates

In the first problem you should: 
 - create a Polygon out of the the x and y coordinates that are provided in the `create_polygon.py` -script. 
 - insert the polygon into a GeoDataFrame 
 - save the Polygon into a Shapefile. 
 - plot and save a figure out of the Polygon. 
 
The [**create_polygon.py**](create_polygon.py) starter script has all necessary steps listed and also some hints are provided. There are all together 6 steps that you need to fill to accomplish
the problem 1. Each step that you need to fill is marked with capital P -letter (P1 to P6).  

## Problem 2: Points to map
 
The problem 2 this week continues the process that we started last week, i.e. creating geometric point -objects and putting them into a map. 
Here our aim is to plot a set of x and y coordinates that we should read from a `some_posts.csv` comma separated file that contains following kind of data:
 
```
lat,lon,timestamp,userid
-24.980792492,31.484633302,2015-07-07 03:02,66487960
-25.499224667,31.508905612,2015-07-07 03:18,65281761
-24.342578456,30.930866066,2015-03-07 03:38,90916112
-24.85461393,31.519718439,2015-10-07 05:04,37959089
```

The data has 81379 rows and consists of locations and times of social media posts inside Kruger national park in South Africa:

| Column | Description |
|--------|-------------|
| lat | y-coordinate of the post |
| lon | x-coordinate of the post |
| timestamp | Time when the post was uploaded |
| userid | userid |

*Note: although the data is based on real social media data, it is heavily anonymized. Userids and timestamps have been randomized, i.e. they do not not match with real ones, 
also spatial accuracy of the data have been lowered.*

- [Download the data](https://raw.githubusercontent.com/Automating-GIS-processes/Exercise-2/master/data/some_posts.csv?token=AGWdzhgsQbNFI3lk6a5GxrjguPnmuhwoks5YKVWrwA%3D%3D) (Click on the link ==> CNTRL + S)  
- Read the data into memory 
  - You can use numpy but recommendable way is to read it directly with Pandas into a DataFrame, [read hints](https://github.com/Automating-GIS-processes/Lesson-2-Geo-DataFrames/blob/master/Lesson/Hints-Exercise-2.md) how to do it.
- Create an empty column called `geometry` where you will store shapely Point objects
- Iterate over the rows of the DataFrame and insert Point objects into column geometry (you need to use .loc indexer to update the row, [see materials](https://github.com/Automating-GIS-processes/Lesson-2-Geo-DataFrames/blob/master/Lesson/pandas-geopandas.md#creating-geometries-into-geodataframe) 
- Convert that DataFrame into a GeoDataFrame, [see hints](https://github.com/Automating-GIS-processes/Lesson-2-Geo-DataFrames/blob/master/Lesson/Hints-Exercise-2.md)
- Update the CRS for coordinate system as WGS84 (i.e. epsg code: 4326)
- Save the data into a Shapefile called `Kruger_posts.shp`
- Create a simple map of those points using either QGIS installed in the computer instance or using `.plot()` -funtion in Python. Save it to GitHub as png file. 

## Problem 3: Movements of individual user (optional task for advanced students)

This is an optional extra task for those who likes to learn even more. Write your codes into the same file as in previous Problem (2).

 - Group the data by userid
 - Create an empty GeoDataFrame
 - For each user: 
    - [sort](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.sort_values.html) the rows by timestamp 
    - create LineString objects based on the points
    - [add](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.append.html) the geometry and the userid into the GeoDataFrame you created in the last step
 - Determine the CRS of your GeoDataFrame to WGS84 (epsg code: 4326)
 - Save the movements of each user into a separate Shapefile
   - Name the output Shapefile based on the userid number
   
 

