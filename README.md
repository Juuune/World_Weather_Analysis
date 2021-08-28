# World_Weather_Analysis

### Overview 
![Dream Vacation Spots with weather heatmap](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Heatmap_Hotel.PNG)

#### Background and purpose of the analysis
To help answering a question"How might we provide real-time suggestions for the ideal vacation spot?" The first task was to define what we meant by “ideal” 
So, over lots of considerations it's defined that were (1) within a given range of latitude and longitude and that (2) provided the right kind of weather for the customers.

#### Techniques used
- Python with pandas, numpy and scipy.stats for data analysis <br/>
- citipy and Numpy to generate random vacation location <br/>
- Tensorflow for data modeling<br/> 
- Open Weather Map API to request current weather data <br/>
- Gmaps with heatmap layer and marker for world weather data visualization <br/>
- jupyter notebook, git 

#### Data Source
- Current weather data : Open Weather map API (www.openweathermap.org)
- Hotel info : Google API near by place 
- Vacation Location : Randomly generated coordinates and corresponding city names from citypy 

### Analysis 

#### A. Weather Analysis 
[World weather analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WeatherPy.ipynb)
[Vacation location analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/VacaionPy.ipynb)

#### B. Weather and vacation location data model  
[Searching for ideal vacation spot with current weather info](https://github.com/Juuune/World_Weather_Analysis/blob/master/ItineraryAnalysis/Vacation_Search.ipynb)
[World weather and coordinate data modeling](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/Weather_ML_Model.ipynb)
![Linear Regression Model on the Northen Hemisphere and Temperature](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Regression_North_Temp.PNG)


#### Sample Itinerary Rcommendation 
[Search for the ideal vacation spot according to customer's preferences](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_Search.ipynb)
[Setting ideal itinerary for selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_itinerary.ipynb)

![Travel route with selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Gmap_itinerary/WeatherPy_travel_map.png)
