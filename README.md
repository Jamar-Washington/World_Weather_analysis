# World_Weather_analysis


### Tools used in this project
**Jupyter notebook**
**OpenWeatherMap API**
**Google Maps API**

This project was built around providing functionality to an traveling app called PlanMyTrip. The key deliverables were:

retrieve weather data from the OpenWeatherMap.org API;
create a map of potential travel destinations using the Google Map API, based on customer's temperature preference input;
create a travel itinerary map, using Google Maps Directions API and a selection of four destinations.

## Summary of the project

First, numpy is impoorted to generate a new set of 2,000 random latitudes and 2,000 longitudes. Next, citipy module was imported to get the nearest city for each latitude and longitude combination. An OpenWeatherMap's API key is imported to assemble the API call URL as a string variable.
With an API call, we retrieves the following information:
* Latitude and longitude
* Maximum temperature
* Percent humidity
* Percent cloudiness
* Wind speed
* Weather description (for example, clouds, fog, light rain, clear sky)

All of the infomation was added to a new DataFrame as shown below.
![Weather_Database](https://user-images.githubusercontent.com/109183214/203423716-88fc9ffa-e662-4c6b-95a5-f89dc6026be3.png)

The dataframe from above is converted to a csv file. This is so it can be referred to the next dataframe. Next, prompt is generated to ask the user what their minimum and maximum temperature criteria was for their vacation. From there, a new dataframe is created by using the loc Pandas method to filter the dataframe for temperature criteria collected.

A for loop was used to iterate through the dataframe, retrieve the latitude and longitude of each city to find the nearest hotel based on the search parameters provided, then add the hotel name to the dataframe. If a hotel isn't found, skip to the next city. Finally, any rows in the dataframe where a hotel name is not found was dropped and the remaining rows were stored into a new dataframe. The dataframe below is the result.  
![Weather_Search_ipynb](https://user-images.githubusercontent.com/109183214/203424321-732f9e7a-7a37-4559-9e01-d008dde75db5.png)  

The map below shows the hotels in the dataframe.
![WeatherPy_vacation_map](https://user-images.githubusercontent.com/109183214/203424369-abce38ca-79dd-44b8-8b7e-d292542a4c98.png)


![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/109183214/203424695-0d45fddc-6dfa-4b41-8321-fcc4ef888873.png)
![WeatherPy_travel_map](https://user-images.githubusercontent.com/109183214/203424701-b402fb61-a2ec-4716-8d2b-c5afc0d62997.png)

