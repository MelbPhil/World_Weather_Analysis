# World_Weather_Analysis
A script that collects and analyzes current weather data across cities worldwide.

## Overview of World Weather Analysis
Purpose: PlanMyTrip will use the data to recommend ideal hotels based on clients' weather preferences.

Method: Create a Pandas DataFrame with 500 or more of the world's unique cities and their weather data in real time. With the list of cities, search for nearby hotels and add those hotel names to a new DataFrame. Map out the location markers on gmaps. 

## Resources
- Data Sources: OpenWeatherMap API, GMAPs Places API, GMAPs Directions API
- Software: Python 3.7.13, Jupyter Notebook

## World Weather Analysis Results
Creating list of random cities:
- The Weather_Database.ipynb script uses the numpy.random.uniform() function to generate a list of 2000 random latitude and longitude cominations, then finds the nearest cities to those locations using the citipy module, specifically citipy.nearest_city().city_name
- Using the OpenWeatherMap API, the adds the current weather data for each city to a dataframe, exporting the data to the 'WeatherPy_Database.csv'

Mapping the Data:
- _World map of hotel locations, based on current temperatures:_
<img width="1440" alt="WeatherPy_vacation_map" src="https://user-images.githubusercontent.com/106599446/177377330-480a52d5-4f75-4953-ace8-356287e1f401.png">

- The above map was created with the Vacation_Search.ipynb script, specifying that the user would like to view hotels in cities (*of the cities on the 'WeatherPy_Database.csv'*) currently experiencing high temperatures of between 60 and 70 degrees Fahrenheit.
- The list of preferred cities is subsequently exported to the 'WeatherPy_vatation.csv' 
- Rerunning the code, the next user would specify their prefferences for maximum temperatures, and the script would generate a new map, and repopulate the CSV file accordingly.

Vacation Itinerary:
- After selecting four of the preferred cities (*of the cities on the 'WeatherPy_vacation.csv'*), the script Vacation_Itinerary.ipynb generates directions for driving to each city.
- _Mapped itinerary:_
<img width="784" alt="WeatherPy_travel_map" src="https://user-images.githubusercontent.com/106599446/177377445-5ddd4a1b-7bf1-45a4-b3e4-6f645b7504fd.png">

- _locations marked:_
<img width="987" alt="WeatherPy_travel_map_markers" src="https://user-images.githubusercontent.com/106599446/177377473-eaf61391-7714-4871-8252-3fa95a62af43.png">

## World Weather Analysis Summary
The scripts outlined above rely on the initial generation of a list of cities nearest to randomly generated longitudes and latitudes, for this reason, it is quite possible that the cities most desired by our users are not being considered. 

Additionally, the Vacation_Itinerary.ipynb script should be refactored further to allow users to input which cities they'd like to visit. (The process for selecting the cities currently is manual.) Using a Try-Except statement, the script could report back to the user if the cities they asked to visit were not actually on the list.
