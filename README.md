# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Data Scinece Immersive Course Project 1: 
## Local Traffic, Statistical Summaries and Inference
#### Name: Raghad Alharbi

Blog Post: 

[Saudi Arabia’s Local Traffic, Statistical Summaries and Inference](https://medium.com/@alharbiraghad/saudi-arabias-local-traffic-statistical-summaries-and-inference-a3b0ee63b7a1)

## Problem Statment

Road traffic injuries (RTIs) are leading causes of mortality and negatively affecting the quality of life in Saudi Arabia. Saudi Arabia have the highest number of deaths from RTAs among high income countries, and it is considered to be the country’s main cause of death for 16-30-year-old males. In 2016, WHO estimated that the rate of road traffic fatalities is 28.8 per 100 000 population [(1)](https://www.who.int/news-room/fact-sheets/detail/road-traffic-injuries)

 [WHO: Deaths on the roads](https://extranet.who.int/roadsafety/death-on-the-roads/#country_or_area/SAU)

As a part of the Quality of Life Program 2020, Saudi Arabia implemented preventative interventions intended to tackle the issue of RTI from multiple aspects, which includes enhancing social engagement, developing cities, providing services, and developing regulations. The goal is to reduce traffic deaths to reach the top 5 most livable countries.[(2)](https://vision2030.gov.sa/sites/default/files/attachments/QoL%20English_0.pdf)

The General Department of Traffic has finalized and forced the modified penalties for traffic violations at the end of 2016. Fines could go up to SR 60,000 (which is around USD 16,000)[(3)](https://www.moi.gov.sa/wps/portal/Home/sectors/publicsecurity/traffic/contents/!ut/p/z1/pVJdT8IwFP0r-sCj6V1b1vnYyGQ4DBkyxvpCat2ghn2ADei_txhjIsoGoU-3yTmn95xTJNAMiVJu9UIaXZVyZe-pcOcwoDRwKA77vagLPAr90aBHMPiAkt8A4N49cE6mQcAiPAoxEqfw7_o8oGwI4A37XRjwIB7fRoQAJ6fx4cjh0MafIoGEKk1tlig1G5nnWnXgZyikLjuw1dXqK5GrOrOpGJ297Wm10i8oZZQQ6QJQ6jrMUa5UBOcqIwo7dlTsMKK_O4hmBw9tHmxJ-nW9Ftw6qUqTvRs0O8dKsjfT8ATHh4B_am4EeM43oKnothxSmyM7noODkq3Odiguq01hv-7TGRUFrersAvVm6RhfIF0XcRwXHvm4Ec_u2B97u0m-XBTzR393_QnFrj5W/dz/d5/L2dBISEvZ0FBIS9nQSEh/).

The aim of this project is to analyze Saudi Arabia’s traffic accidents and driving licenses data seeking to identify trends, recognize underlying factors influencing traffic accidents, provide recommendations and key findings and insights. 

To study the effects of the enforced regulations, lets take a look at the traffic accidents and driving licenses datasets from [General Authority for Statistics](https://www.stats.gov.sa/en), which is a government agency in Saudi Arabia responsible for the implementation of statistical works including the conducting of national surveys.

## Executive Summary

Saudi Arabia is heading in the right direction in regards to strengthening traffic regulations and raising driver’s awareness. The decrease in traffic accidents is raped, especially in Riyadh region. Officials have to tackle the problem in other regions the same way they are controlling the situation in Riyadh. The rural areas need more strict measures to reduce traffic deaths and reach the goal of making Saudi Arabia one of the top 5 most livable countries.

### Overview
### Contents:
- **Jupyter notebook file**:
   - [Datasets Description](#Datasets-Description)
   - [Data Import & Cleaning](#Data-Import-and-Cleaning)
   - [Exploratory Data Analysis](#Exploratory-Data-Analysis)
   - [Data Visualization](#Visualize-the-data)
   - [Descriptive and Inferential Statistics](#Descriptive-and-Inferential-Statistics)
   - [Outside Research](#Outside-Research)
   - [Conclusions and Recommendations](#Conclusions-and-Recommendations)
- **Five CSV files**
- **A blog post that showcases the problem and key findings of this project**: link

### Install

This project requires **Python** and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org/)
- [matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)

You will also need to have software installed to run and execute a [Jupyter Notebook](http://ipython.org/notebook.html)

If you do not have Python installed yet, it is highly recommended that you install the [Anaconda](http://continuum.io/downloads) distribution of Python, which already has the above packages and more included. 


### Run

In a terminal or command window, navigate to the top-level project directory `project1/` (that contains this README), then write cd code and run one of the following commands:

```bash
ipython notebook Saudi_Arabia_Traffic.ipynb
```  
or
```bash
jupyter notebook Saudi_Arabia_Traffic.ipynb
```

This will open the Jupyter Notebook software and project file in your browser.

### Datasets
For this project, we are using 5 different datasets:

[Driving Licenses](https://datasource.kapsarc.org/explore/dataset/saudi-arabia-driving-licenses-issued-in-the-kingdom-2004-2008/information/?disjunctive.administritive_area&sort=time_period&location=5,24.37495,45.08024&basemap=jawg.streets)

This dataset contains Saudi Arabia Driving Licenses Issued By Administrative Area for 1993 - 2017. Data from General Authority for Statistics . Follow datasource.kapsarc.org for timely data to advance energy economics research.

|Feature|Type|Dataset|Description|
|---|---|---|---|
year|int|Driving Licenses|Year in which the licenses issued
region|object|Driving Licenses|Region in which the licenses issued
driving_licenses|int|Driving Licenses|Number of issued licenses per year
geo_point_2d|object|Driving Licenses|Location of center the city where  licenses issued
x|float|Driving Licenses|longitude of center the city
y|float|Driving Licenses|Latitude of center the city


[Traffic Accidents and Casualties](https://datasource.kapsarc.org/explore/dataset/saudi-arabia-traffic-accidents-and-casualties-injured-dead-2008/export/?disjunctive.region&disjunctive.indicator&sort=time_period)

This dataset contains Saudi Arabia Traffic Accidents and Casualties by Region for 2016-2017. Data from General Authority for Statistics. Follow datasource.kapsarc.org for timely data to advance energy economics research.

|Feature|Type|Dataset|Description|
|---|---|---|---| 
year|int|Traffic Accidents|Year in which the accident occured
region|object|Traffic Accidents|Region in which the accident occured
indicator|object|Traffic Accidents|Measurement about the demages (No. of accidents - No. of accidents - No. of dead)
value|int|Traffic Accidents|value of the indicator
geo_point_2d|object|Traffic Accidents|Location of center the city where the accident occured
x|float|Traffic Accidents|longitude of center the city
y|float|Traffic Accidents|Latitude of center the city

[2018 Driving Licenses](https://datasource.kapsarc.org/explore/dataset/saudi-arabia-driving-licenses-issued-in-the-kingdom-2004-2008/information/?disjunctive.administritive_area&sort=time_period&location=5,24.37495,45.08024&basemap=jawg.streets)

This dataset contains Saudi Arabia Driving Licenses Issued By Administrative Area for 2018. Data from General Authority for Statistics .

|Feature|Type|Dataset|Description|
|---|---|---|---|
year|int|2018 Driving Licenses|Year in which the licenses issued
region|object|2018 Driving Licenses|Region in which the licenses issued
driving_licenses|int|2018 Driving Licenses|Number of issued licenses per year

[2018 Traffic Accidents and Casualties](https://datasource.kapsarc.org/explore/dataset/saudi-arabia-traffic-accidents-and-casualties-injured-dead-2008/export/?disjunctive.region&disjunctive.indicator&sort=time_period)

|Feature|Type|Dataset|Description|
|---|---|---|---| 
year|int| 2018 Traffic Accidents|Year in which the accident occured
region|object|2018 Traffic Accidents|Region in which the accident occured
indicator|object|2018 Traffic Accidents|Measurement about the demages (No. of accidents - No. of accidents - No. of dead)
value|int|2018 Traffic Accidents|value of the indicator


This dataset contains Saudi Arabia Traffic Accidents and Casualties by Region for 2018. Data from General Authority for Statistics. 

[Population](https://datasource.kapsarc.org/explore/dataset/saudi-arabia-population-by-administrative-region-nationality-and-sex/information/?disjunctive.administrative_region&disjunctive.gender)

This dataset contains Saudi Arabia Population by Administrative Region and Gender for 2016-2018. Data from Saudi Arabian Monetary Agency. Follow datasource.kapsarc.org for timely data to advance energy economics research.

|Feature|Type|Dataset|Description|
|---|---|---|---|
year|int|population|Year 
region|object|population|Region of population
pop_total|int|population|Total Number of population
pop_female|int|population|Female population
pop_male|int|population|Male population