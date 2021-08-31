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

#### Data management
- Location : Randomly generated coordinates and corresponding city names from citypy </br>
- Current weather data : Open Weather map API (www.openweathermap.org)</br>
- Hotel info : Google API near by place </br>

Before jumping into analysis, Data collection and data transformation was needed for simpler format and analysis usage. 
First, random latitude and longitude number was genereated using np.random.uniform and it was stored in zip, together with matched city names from citipy, created the coordinates list. For the current weather information, Open Weather map API was used and current weather description with, wind humidity, max temperature, cloudiness data was added to weather dataframe. Addition to that the country code and time data was collected and transformed into '%Y-%m-%d %H:%M:%S' format for further use. </br>


[World weather analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WeatherPy.ipynb)</br>


#### Step 1. World weather data exploration   


[World weather analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WeatherPy.ipynb)</br>
[World weather linear regression analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WorldWeather_Regression.ipynb)</br>

![Latitute vs Max Temperature scatter plot](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/CityLatitudenTemp.png)</br>

![Linear Regression Model on the Northen Hemisphere and Temperature](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Regression_North_Temp.PNG)</br>

![Correlation table of Weather factors (Northen Hemisphere)](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Correlation_North_Weather.PNG)</br>
![Correlation table of Weather factors (Southen Hemisphere)](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Correlation_North_Weather.PNG)

#### Step 2. World weather data clustering model 

To help find patterns or groups of weather data the unsupervised learning model was used on 4 weather facotrs(max temperature, humidity, cloudiness, wind speed).</br>

[World weather data ML modeling](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/Weather_ML_Model.ipynb)</br>

#### Step 3. Customized vacation spot search 
For the customized vacation spot recommendation, the lodging information and preferred weather input code was needed. 
From the customer's preferred temperature input the prefered city was selected and nearby lodging informations for cities was parsed from google API.
For the better view for the available location options, created the Gmap with weather heatmap and hotel info marker.</br>

[Vacation location analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/VacaionPy.ipynb)</br>
[Searching for ideal vacation spot with current weather info](https://github.com/Juuune/World_Weather_Analysis/blob/master/ItineraryAnalysis/Vacation_Search.ipynb) </br>


##### Sample Itinerary Rcommendation 
According to cutomer's preference, customer could make choose set of cities for a dream vacation from recommended search result. With this set of cities, the vacation itinerary code would suggest ideal travel route for the driving. </br>

[Search for the ideal vacation spot according to customer's preferences](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_Search.ipynb) </br>
[Setting ideal itinerary for selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_itinerary.ipynb)</br>
![Travel route with selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Gmap_itinerary/WeatherPy_travel_map.png)

### Challenges 

#### API data extraction challenge

#### Weather data modeling challenge
