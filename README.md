# World_Weather_Analysis

![Dream Vacation Spots with weather heatmap](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Heatmap_Hotel.PNG)

#### Background and purpose of the analysis
To help answering a question"How might we provide real-time suggestions for the ideal vacation spot?" The first task was to define what we meant by “ideal” 
So, over lots of considerations it's defined that were (1) within a given range of latitude and longitude and that (2) provided the right kind of weather for the customers.

#### Techniques used
- Python with pandas, numpy and scipy.stats for data analysis <br/>
- citipy and Numpy to generate random vacation location <br/>
- Tensorflow, sklearn for data modeling and clustering<br/> 
- Open Weather Map API to request current weather data <br/>
- Gmaps with heatmap layer and marker for world weather data visualization <br/>
- jupyter notebook, git 

### Analysis 

#### Step 1. Data management
Before jump into analysis, Data collection and data transformation was needed for simpler format and analysis usage. 
First, random latitude and longitude number was genereated using np.random.uniform and it was stored in zip, together with matched city names from citipy, created the coordinates list. For the current weather information, Open Weather map API was used and current weather description with, wind humidity, max temperature, cloudiness data was added to weather dataframe. Addition to that the country code and time data was collected and transformed into '%Y-%m-%d %H:%M:%S' format for further use. 

##### Data Source
- Location : Randomly generated coordinates and corresponding city names from citypy 
- Current weather data : Open Weather map API (www.openweathermap.org)
- Hotel info : Google API near by place 


#### Step 2. World weather data analysis  

[World weather analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WeatherPy.ipynb)</br>
[World weather data ML modeling](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/Weather_ML_Model.ipynb)</br>
![Linear Regression Model on the Northen Hemisphere and Temperature](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Regression_North_Temp.PNG)

#### Step 3. Customized vacation spot search 
For the customized vacation spot recommendation, the lodging information and preferred weather input code was needed. 
From the customer's preferred temperature input the prefered city was selected and nearby lodging informations for cities was parsed from google API.
For the better view for the available location options, created the Gmap with weather heatmap and hotel info marker.
[Vacation location analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/VacaionPy.ipynb)
[Searching for ideal vacation spot with current weather info](https://github.com/Juuune/World_Weather_Analysis/blob/master/ItineraryAnalysis/Vacation_Search.ipynb) </br>


##### Sample Itinerary Rcommendation 
According to cutomer's preference, search results might recommend few 
[Search for the ideal vacation spot according to customer's preferences](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_Search.ipynb) </br>
[Setting ideal itinerary for selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_itinerary.ipynb)</br>

![Travel route with selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Gmap_itinerary/WeatherPy_travel_map.png)
