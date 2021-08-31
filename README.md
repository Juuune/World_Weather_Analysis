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

## Analysis 

### Data management
- Location : Randomly generated coordinates and corresponding city names from citypy </br>
- Current weather data : Open Weather map API (www.openweathermap.org)</br>
- Hotel info : Google API near by place </br>

Before jumping into analysis, Data collection and data transformation was needed for simpler format and analysis usage. 
First, random latitude and longitude number was genereated using np.random.uniform and it was stored in zip, together with matched city names from citipy, created the coordinates list. For the current weather information, Open Weather map API was used and current weather description with, wind humidity, max temperature, cloudiness data was added to weather dataframe. Addition to that the country code and time data was collected and transformed into '%Y-%m-%d %H:%M:%S' format for further use. </br>

</br>
[World weather analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WeatherPy.ipynb)</br>
</br>

### Step 1. World weather data exploration   

From the scatter plots, there is obvious pattern on maximum temperature by latitute. other Weather factor also shows some pattern but is doesn't look linear pattern. 
[World weather analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WeatherPy.ipynb)</br>
</br>
![Latitute vs Max Temperature scatter plot](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/CityLatitudenTemp.png)</br>
![Latitute vs Humidity scatter plot](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/CityLatitudenHumidity.png)</br>
![Latitute vs Cloudiness scatter plot](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/CityLatitudenCloud.png)</br>
![Latitute vs Wind Speed scatter plot](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/CityLatitudenWindSpeed.png)</br>
</br>
</br>
To See the linear relationship between weather factor and latitude, first seperate the weather data into northern hemisphere and southern hemisphere. Then plot the data with linear regression model to see the linear pattern. </br>
[World weather linear regression analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/WorldWeather_Regression.ipynb)</br>
</br>
![Linear Regression Model on the Northen Hemisphere and Temperature](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Regression_North_Temp.PNG)</br>
![Linear Regression Model on the Northen Hemisphere and Wind Speed](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Regression_North_Wind.PNG)</br>

Since weather factors influence each other, It is better to check the correlation between weather factors. From the coefficient, the maximum temperature shows the strongest correlation with other weather factors. </br>
![Correlation table of Weather factors (Northen Hemisphere)](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Correlation_North_Weather.PNG)</br>
![Correlation table of Weather factors (Southen Hemisphere)](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Correlation_North_Weather.PNG)</br>
</br>
</br>
</br>


### Step 2. World weather data clustering model 

To help find patterns or groups of weather data the unsupervised learning model was used on 4 weather facotrs(max temperature, humidity, cloudiness, wind speed). With this Model I can understand whether there is a pattern of weather by location. </br>

[World weather data ML modeling](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/Weather_ML_Model.ipynb)</br>
</br>
![Weather data clustering with K-means : k=4](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/3D_plot_4clusters.PNG)</br>
![Weather data clustering with K-means : k=5](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/3D_plot_5clusters.PNG)</br>
</br>
To Decide best number of cluster the elbow curve analysis was used. According to the curve the elbow lies between 4 and 5 clusters. </br>
</br>
![Elbow curve plot](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/ElbowCurve.PNG)</br>

</br>
</br>
</br>

### Step 3. Customized vacation spot search 

For the customized vacation spot recommendation, the lodging information and preferred weather input code was needed. 
From the customer's preferred temperature input the prefered city was selected and nearby lodging informations for cities was parsed from google API.
For the better view for the available location options, created the Gmap with weather heatmap and hotel info marker.</br>

[Vacation location analysis](https://github.com/Juuune/World_Weather_Analysis/blob/master/WeatherAnalysis/VacaionPy.ipynb)</br>
[Searching for ideal vacation spot with current weather info](https://github.com/Juuune/World_Weather_Analysis/blob/master/ItineraryAnalysis/Vacation_Search.ipynb) </br>
</br>
#### Sample Itinerary Rcommendation 

According to cutomer's preference, customer could make choose set of cities for a dream vacation from recommended search result. With this set of cities, the vacation itinerary code would suggest ideal travel route for the driving. </br>

[Search for the ideal vacation spot according to customer's preferences](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_Search.ipynb) </br>
[Setting ideal itinerary for selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/IternaryAnalysis/Vacation_itinerary.ipynb)</br>
</br>
![Select vacation spots from recommended locations](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Gmap_itinerary/WeatherPy_travel_map_markers.png)</br>
![Travel route with selected cities](https://github.com/Juuune/World_Weather_Analysis/blob/master/image/Gmap_itinerary/WeatherPy_travel_map.png)</br>


</br>
</br>


## Challenges 

### API data extraction challenge

### Weather data modeling challenge



## Next Step 

### Weather data model 
To avoid overfitting feature elimination can be used, so the model would not use the entire weather factor. 
Feature elimination and feature extraction can be done by principal componant analysis using sklearn.decomposition 

### Vacation spot search 
For better recommendation algorythm, other weather preference can be added to model (ex, Rain, Snow or Humidity at location) 
Adding another preference would require some refactore vacation_search code with for loop and pandas loc. 
