# Open-Resturants-in-Toronto
IBM-Capstone

As a part of the IBM Data Science program capstone project, I worked on the real datasets to get an experience of what a data scientist goes through in the real life, Main object of this project were to define business problem, using the web data through web scraping, and using Foursquare location data to compare different neighborhoods of Toronto to figure out which neighborhood is profitable for starting a new restaurant. In this project, I will go through the whole process step by step manner from problem targeting, data preparation to final analysis result. Last but not the least, I will provide my suggestion which can be leveraged by the business stakeholders to make their decisions.

## 1. Description of the Business Problem

In this project, I will go through all steps to make a decision whether it is a good idea to open a Chinese restaurant.
I analyze the neighborhoods in Toronto to identify the most profitable area to place it.


Target Audience:

Business personnel who wants to invest or open a Chinese restaurant in Toronto.
Freelancers who loves to have their own restaurant as a side business.
Chinese crowd who wants to find neighborhoods with lots of option for Chinese restraurants.

## 2. Data acquisition & cleaning:

2.1 Data Sources
I used (https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M) wiki page to get all the information about the neighborhoods present in Toronto. This page has the postal code, borough & the name of all the neighborhoods present in Toronto.
Then I used (“https://cocl.us/Geospatial_data”)csv file to get all the geographical coordinates of the neighborhoods.
To get information about the distribution of population by their ethnicity I’m using “Demographics of Toronto”(https://en.m.wikipedia.org/wiki/Demographics_of_Toronto#Ethnic_diversity) wiki page. Using this page, I’m going to identify the neighborhoods which are densely populated with Indians as it might be helpful in identifying the suitable neighborhood to open a new Chinese restaurant.
To get location and other information about various venues in Toronto I’m using Foursquare’s explore API.( https://developer.foursquare.com/docs)

2.2 Data Cleaning

Firstly, I scraped Toronto neighborhoods table from Wikipedia.

Then I added geographical coordinates to the neighborhoods by extracting the data present in the Geospatial Data csv file.

Thirdly, I scraped the distribution of population from Wikipedia, examining those neighborhood’s population to identify the densely populated neighborhoods with Chinese population.

Fourthly, I got location data from Foursquare, by choosing 100 popular spots for each neighborhood within a radius of 1km.

## 3. Exploratory Data Analysis

3.1 Visualization
The next step, I used Folium Library and Leaflet Map to draw an interactive map using coordinate data.

![alt text](https://github.com/YiqingFan/Open-Resturants-in-Toronto/blob/main/vis-map.png)
3.2 Relationship between neighborhood and Chinese restaurants
I used bar plots to identify the boroughs with densely populated Chinese restaurants.

![alt_text](https://github.com/YiqingFan/Open-Resturants-in-Toronto/blob/main/boroughs.png)
3.3 Relationship between neighborhood and Chinese population
I analyzed the neighborhoods and identified the neighborhoods with the highest number of Chinese populations.

![alt_text](https://github.com/YiqingFan/Open-Resturants-in-Toronto/blob/main/neighborhood.png)

## 4. Predictive Modeling

4.1 Clustering neighborhoods of Toronto

First step in k-means clustering is to identify best K value, which is the number of clusters in a given dataset. To do so I used elbow methods on the Toronto dataset with Chinese restaurants’ percentage, aiming to do k-means cluster.

![alt_text](https://github.com/YiqingFan/Open-Resturants-in-Toronto/blob/main/elbow%20method.png)
After analyzing using elbow method with distortion score and squared error for each k value, K=7 is the best value.

4.2 Examining the clusters

We have total of 7 clusters such as 0,1,2,3,4,5,6. 
We find that Cluster 4 contains Boroughs with large numbers of Chinese Restaurants. It represents opening a new Chinese restaurant in North York and Scarborough will be very competitive.

![alt_text](https://github.com/YiqingFan/Open-Resturants-in-Toronto/blob/main/result.png)

## 5. Results

We have reached the end of the analysis, in this section we will document all the findings from above clustering & visualization of the dataset. In this project, we started off with the business problem of identifying a good neighborhood to open a new Chinese restaurant. To achieve that we looked into all the neighborhoods in Toronto, then analyzed the Chinese population in each neighborhood & number of Chinese restaurants in those neighborhoods to come to conclusion about which neighborhood would be a better spot. We have used variety of data sources to set up a very realistic data-analysis scenario. We have found out that —

In those 10 boroughs we identified that only North York & Scarborough & Etobicoke have high amounts of Chinese restaurants with the help of bar plots between Number of Chinese restaurants in Borough of Toronto.

In those neighborhoods in Toronto, Bayview Village & Dorset Park Wexford ScarboroughTown Centre & Steeles West L’Amoreaux West have high amounts of Chinese restaurants with the help of bar plots between Number of Chinese restaurants in neighborhoods of Toronto.

In all the ridings, Scarborough & Don Valley North(North York) & Willowdale(North York) & Spadina_Fort York(East York) are densely populated with Chinese crowd ridings.

Since Scarborough and North York are taken by a large amounts of Chinese Restaurants, it is a better idea to leave those boroughs out and consider East York for the new restaurant’s location.

After careful consideration it is a good idea to open a new Chinese restaurant in East York borough since it has high number of Chinese populations which gives a higher number of customers possibility and lower competition since very less Chinese restaurants in the neighborhoods.
