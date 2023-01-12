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
| Environment / Platforms   | Python 3.8+, Jupyter Notebook|

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

The main question that was sought for an answer during the analysis is to determine what is the chance of snow in Poland on Christmas.

By the way, we will try to answer the following questions:

- What was the average snow cover and temperature on this day over 70 years?
- How many weather stations do we have data for each year? Where exactly are they located?
- Are there weather stations that recorded measurements for the entire period of 71 years?
- What is the snow occurence ratio for each station?
- Where are the places with the highest/least chance of snow?
- What was the situation with snow on Christmas in particular decades?

<br>
  
<u>Data interpolation</u>

In order to create maps showing areas with a certain chance of snow occurrence, it is necessary to interpolate input data from several dozen weather stations scattered throughout Poland. For this purpose, the Ordinary Krigging algorithm from the pykrige library was used. After data interpolation, the resulting meshgrid can be displayed on a map using the Basemap library.

<br>

## DATA VISUALIZATION

**Snow occurrence during Christmas Day in Poland (58 years period)**

<img src="/img/snow_occur_ratio_cover.png" width="450" height="">

---

**Snow occurrence in 1950s**

<img src="/img/snow_occur_50s.png" width="450" height="">

---

**Snow occurrence in 1960s**

<img src="/img/snow_occur_60s.png" width="450" height="">

---

**Snow occurrence in 1970s**

<img src="/img/snow_occur_70s.png" width="450" height="">

---

**Snow occurrence in 1980s**

<img src="/img/snow_occur_80s.png" width="450" height="">

---

**Snow occurrence in 1990s**

<img src="/img/snow_occur_90s.png" width="450" height="">

---

**Snow occurrence in 2000s**

<img src="/img/snow_occur_2000s.png" width="450" height="">

---

**Snow occurrence in 2010s**

<img src="/img/snow_occur_2010s.png" width="450" height="">

---

<br>

# RESULTS

- The average occurrence of snow on Christmas Day (based on 58 years of data) in most areas of Poland ranges from 0.2-0.4 (which means 2-4 snowy Christmas per 10 years)
- It is clear that the western part of the country has less chance of snow on Christmas. In some places, only 1 in 10 Christmas Days fall with snow.
- The greatest chance of snow (often 0.8-1) is in the south in the mountains, which is pretty obvious. We can also expect snow more often on Christmas in the north-east and east of Poland (with an average chance of 0.4-0.5).
- Over the course of 70 years of measurements, more and less snowy periods can be observed. The snowiest decades were in the 1950s and 1960s, and the least snow on Christmas was in the 1970s, 1980s and 2010s.
- Every few years (5-10) exceptionally snowy Christmas can be observed with an average snow cover thickness of more than 10 cm. This has happened 9 times in 70 years of measurements. Typically, the average snow cover is only several cm.

<br>

# CONCLUSION

Based on historical data from the last 70 years, it can be concluded that the so-called a white Christmas in Poland is less than likely. In addition, a truly white Christmas, when there was an average of over 10 cm of snow, occurred only 9 times. Therefore, we should not expect snow on December 25th. Also, the occurrence of snow does not depend on time, which means that once there were completely snow-free Christmas, e.g. in the late 1950s or in the 1970s.
