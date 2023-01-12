# What is the chance for white Christmas in Poland?
  
## OBJECTIVE

The aim of this project is to answer a simple question based on meteorological data - what is the chance of snow during Christmas in Poland?

<br>

## JUPYTER NOTEBOOKS

- Data collection and cleaning
- Data analysis
- Data interpolation and visualization 

<br>
  
## BACKGROUND

There is a common belief in Poland that we should expect snow during Christmas and in the past it was the norm.. During this analysis, I decided to check on hard historical data how exactly that day looked like in terms of weather over the past 70 years. The main goal will be to create a map of Poland showing areas with a snow occurence on December 25th.

<br>

## TOOLS

| Task      | Package / tools |
| --------- | ----------- |
| Data Collection | BeautifulSoup, requests|
| Data Preprocessing   | pandas, tabula |
| Data Analysis   | pandas, numpy, pykrige |
| Data Visualization   | matplotlib, Basemap |
| Environment / Platforms   | python 3.8+, Jupyter Notebook|

<br>

## DATA COLECTION

In this analysis, I will rely on the official meteorological data provided by IMGW (Official Polish Meteo Institute) [on their website](https://danepubliczne.imgw.pl/data/dane_pomiarowo_obserwacyjne/dane_meteorologiczne/dobowe/klimat/). The oldest data date back to 1951, which gives a period of over 70 years.

All data is sorted in directories in the form of csv files.

<br>

## DATA PREPROCESSING

Data cleaning:
- Fixing station names with unwanted characters
- Finding the geographical coordinates of the weather stations – using tabula package to fetch data from PDF document
- Looking for duplicates and fixing missing values
- Merging main dataframe with weather stations coordinates
- Converting longitude/latitude data to decimal degrees format

<br>

## DATA ANALYSIS
