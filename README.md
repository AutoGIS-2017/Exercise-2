# Exercise-2

This week we will practice how to ...

### Due dates
 
 - 100 % of point total if you return your solution within 1 week (due date 14.11.2016) 
 - 85 % of point total if your return your solution within 2 weeks (due date 21.11.2016)
   - Detailed hints provided
 - 50 % of point total if you return your solution within 3 weeks (due date 28.11.2016)
   - Full solution provided

## Sections

 - [Problem 1: ]()
 - [Problem 2: ]()
 
 
## Problem 1: 

Something easy.
 
 - Create a polygon based on the points that are provided in the DUMMY-script and insert it into a GeoDataFrame that should be imported into a Shapefile
 - Plot the polygon using `data.plot()` -function and save it as png file that should be uploaded to GitHub
 - What does the figure represent?

## Problem 2: Points to map
 
The problem 2 this week continues the process that we started last week, i.e. creating geometric point -objects and putting them into a map. 
Here our aim is to plot a set of x and y coordinates that we should read from a text file that contains following kind of data:
 
```
```

The data consists of locations and times of social media posts inside Kruger national park in South Africa:

| Column | Description |
|--------|-------------|
| lat | y-coordinate of the post |
| lon | x-coordinate of the post |
| timestamp | Time when the post was uploaded |
| userid | userid |

*Note: although the data is based on real social media data, it is heavily anonymized. Userids are random numbers that does not match with real ones, also timestamps 
have been modified.*

- Download the data 
- Read the data into memory 
  - You can use numpy but recommendable way is to read it directly with Pandas into a DataFrame, [read hints]() how to do it.
- Create an empty column called `geometry` where you will store shapely Point objects
- Iterate over the rows of the DataFrame and insert Point objects into column geometry (you need to use .loc indexer to update the row, [see materials]() 
- Convert that DataFrame into a GeoDataFrame, [see hints]()
- Update the CRS for coordinate system as WGS84 (i.e. epsg code: 4326)
- Save the data into a Shapefile called `Kruger_posts.shp`
- Create a simple map of those points using either QGIS installed in the computer instance or using `.plot()` -funtion in Python. Save it to GitHub as png file. 

## Problem 3: Movements of individual user (optional task for advanced students)

This is an optional extra task for those who likes to learn even more. Write your codes into the same file as in previous Problem (2).

 - Group the data by userid
 - For each user, create LineString objects based on the points
 - Save the movements of each user into a separate Shapefile
   - Name the output Shapefile based on the userid number
 

