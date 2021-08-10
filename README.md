# World_Weather_Analysis
This project contains 3 parts, with details of each part as follows:

**1. Create a Weather Database (Weather_Database.ipynb)**
	- Generate a list of 2,000 random numbers assigned to latitute, and 2,000 random numbers assigned to longitude, and zip together as lat,long coordinates
	- Create a list for holding the cities, and use citipy extension to find nearest city to each coordinate pair; add city name to a list if it is a new city name
	- Import weather map API and iterate through the list of all cities found in prior step, finding the coordinates, max temp, humidity %, cloud %, wind speed, country & description of the current weather. Add each city's data to the list created holding the cities. 
	- Convert the dictionary created with city weather information into a dataframe, export to CSV

**2. Create Vacation Search (Vacation_Search.ipynb; utilizes data found in step 1)**
  - Import the CSV data found in the 1st part of the project into a new data frame to be used in this stage
  - Ask user for input on what is the minimum & maximum temperature they would like for their vacation; inputs are used to pair down the list of cities only including max temps between the user inputs
  - Drop any cities with a null weather value
  - Create a new dataframe with a blank placeholder to store hotel names
  - User Google Maps API nearby search functionality to find hotels near each city in the dataframe and add them to the dataframe; then drop any that did not find a hotel value
  - Create an output CSV with all of the cities & hotel information
  - User Google Maps API to create a map of all hotels in the list; if marker is clicked on, each will display the hotel name, city, country, current weather & max temp
  - ![WeatherPy_vacation_map](https://user-images.githubusercontent.com/85597801/128798204-7a4d9560-f03a-4ec7-8e49-26da6c93e461.png)

**3. Create Vacation Itinerary (Vacation_Itinerary.ipynb; dependent on step 1 & step 2)**
  - Import CSV created in previous project as a dataframe
  - Recreate map (same as previous with location markers)
  - Locate 4 cities in the same country relatively close to one another; New York State was chosen out of this dataset
  - Attach one city to be a start & end point, and then select 3 cities to be stops along the way. Create a dataframe with data for each of the cities selected.
  - Get lat&lng coordinates for each city in the list and store as a value
  - Create a map with a route using Google Maps API
  - Create a dataframe containing each dataframe created earlier with city data for the 4 selected cities
  - Create another map displaying only the 4 cities selected, with pop up markers again noting hotel name, city, country, weather & max temp.
  -![WeatherPy_travel_map](https://user-images.githubusercontent.com/85597801/128798171-a6c244ba-5898-42b8-8f3c-46ddd7ae7a73.png)
  -![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/85597801/128798176-703f676e-69cc-42a8-a9c0-df2e91e897db.png)
   
Notes of adjustments to be made for different data:
- A new list will be generated each time part 1 is run
- Different temperature range can be entered in part 2
- Rename cities in box 5 to match your choices, with start & end being the same
- Travel mode may be changed from "Driving" which was used in the example
- To change default map position, use the lat & lng coordinates for one of the cities on the route