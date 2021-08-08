
## Best Suburb to Open a Cafeteria in Melbourne 🇦🇺

Create a Machine Learning model which suggests a location to open a Cafeteria

  
## Acknowledgements

 - [Category:Suburbs of Melbourne](https://en.wikipedia.org/wiki/Category:Suburbs_of_Melbourne)
 - [Foursquare](https://foursquare.com/)
 - [Applied Data Science Capstone](https://www.coursera.org/learn/applied-data-science-capstone)

## Author

- [@PiyalBanik](https://twitter.com/PiyalBanik)

  
## Business Understanding
The main goal of this project is to collect and analyze data in order to select a location in Melbourne to open a Cafeteria. We want to help a business owner planning to open up a Cafe in a location by exploring better facilities around the Suburb. 

## Analytical Approach: 

This is an unsupervised machine learning problem where we need to group together suburbs having similar facilities. We will use K Means Clustering to solve this problem.

## Data Requirements:

We would need a list of suburbs, the location of each suburb, and how many cafes are present in the suburb. 

## Data Collection:

- List of Suburbs in Melbourne, Australia which I have extracted from: https://en.wikipedia.org/wiki/Category:Suburbs_of_Melbourne 
- Latitude & Longitude of all the suburbs using Geocoder
- venues in each suburb from foursquare API https://foursquare.com/


## Data Understanding

- The Wikipedia page contains a list of suburbs in Melbourne. There are 212 suburbs in Melbourne which I extracted using a web scraping technique with the help of Python BeautifulSoup and Request packages.
- the geographical coordinates such as latitude and longitude of each suburb were collected using Python’s Geocoder package.
- Then, Foursquare API was used to extract details about the various venues present in each suburb.
- Once, the location data was extracted by using Geocoder, I used the Folium package to visualize the data on a map. This ensured us that the data we retrieved was correct. 
- Foursquare API was used to obtain the top 100 venues within a radius of 2000 meters.


## Feature Engineering

- Converted the data into dummy variables using get_dummies method of Pandas package that will be essential for performing clustering algorithm
- Grouped the data by Suburb & also taking the mean of the frequency of occurrence of each category.
- I extracted the data of the Cafeteria only
- Our final data frame had two variables: suburb name and the mean of the frequency of occurrence of cafes

## Modeling

- Performed clustering on the data using K-means clustering. 

- Found out 3 clusters based on the frequency of occurrence of Cafes in each suburb. 

- Found out the suburb which had the highest concentration of Cafes and also the lowest concentration

### Results

Categorized the data into 3 categories using K-means clustering based on the frequency of occurrence for ‘Cafe’.
- Cluster 0: Suburbs with a low number of Cafes.
- Cluster 1: Suburbs with a moderate number of cafes.
- Cluster 2: Suburbs with a high concentration of Cafe.

## Evaluation

- Cluster 0 is displayed as the red color represents a greater opportunity and high potential but also suffers from the risk of having fewer customers as those areas are not busy areas. 

- As a new business owner it wouldn’t be wise enough to choose cluster 2. 

Therefore, I would recommend that cluster 1 represented by blue color, should be chosen where there is medium competition but greater opportunity.
