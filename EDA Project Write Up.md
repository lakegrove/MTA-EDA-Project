# Covid Impact on MTA Ridership 

Jonathan Wyatt

## Abstract

The goal of this project was to use exploratory data analysis to investigate Subway usage in New York City pre Covid through the pandemic to current day one year later (March 2021) from the initial national shutdown. The focus was to look at how MTA usage changed by Borough and stations within Boroughs.  Additionally the total ridership numbers were used to compare financial forecasted revenue shortfalls by the city to see how they were tracking (see PDF) in reality.    

## Design

The data is weekly information collected by [MTA](http://web.mta.info/developers/turnstile.html) in New York City from January 2020 to March 20 2021. Covid data was also used in this analysis, courtesy of the [New York City Health Department](https://github.com/nychealth/coronavirus-data/tree/master/trends). The stations for the MTA were mapped to a borough via a separately generated file using MTA data.  The data was then cleaned and combined to look at the ridership behavior trends by Borough and for the city to see how they compare with overall new daily covid cases.     

## Data

The MTA turnstile houses data from turnstiles and stations all over New York and parts of New Jersey.  The data shows date, time, total entries and exits from the turnstile at each station.  This data is collected multiple times days, usually in four hour cadences, but more in some instances where audits are performed (which were ignored for the purpose of this analysis). The Covid data used was tracking new cases of covid by day and by borough as the analysis wanted to focus on the spread of the disease and whether MTA seemed to accelerate or impact transmission. 

## Algorithms

Exploratory data analysis was used to remove duplicate values (audit values), blanks and stations not located in New York City.  Borough data was added to give more regional context to see how different parts of the city were impacted.  Additionally, the analysis used pandas to extract from the cumulative entries a daily inflow into stations.  This methodology produced inconsistencies in the form of negative counts as well as outliers well outside the reasonable range for a station.  These anomalies were explored via two methods one using statistics to create a range (with 4 standard deviations of mean traffic for a turnstile) as well as an alternative methodology of discarding turnstiles that averaged more than 4 people per second over a sustained period (the latter was used to present the analysis).  The data was then cut up into borough specific data and used to look at the top stations in Manhattan both before and after the pandemic.  Covid was also assessed on a city wide basis and total ridership was extrapolated into a rough assumption on lost revenues (more information in the PDF). 

## Tools
- SQL for data aggreggation
- Numpy and Pandas for data manipulation and cleaning
- Matplotlib and Seaborn for plotting

## Communication
The PDF of the slides with vis, [Tanzania Waterpoints](https://public.tableau.com/profile/arjun#!/vizhome/TanzaniaWater/TanzaniaWaterpoints) 