# Manhattan Crime Unit


![ManhattanZipcodeCrime.gif](https://github.com/gordonchen07/Manhattan-Crime/blob/master/ManhattanZipcodeCrime.gif)

## Project Description
This project is an analysis on NYC Open Data Crime Data and predicting crime rates in the Manhattan by zipcode. I utilized Time Series Analysis to study the crime data in Manhattan and to forecast what the crime rate will be in the future. There are two layers to the Time Series Analysis; first layer is to look at the forecasts of 3 types of Crime(Misdeamoner, Felony, Violation) and the second layer is to look at the forecasts of crime in each zipcode of Manhattan. Bokeh and Matplotlib were used to create visualizations of the Time Series forecasts.

![TimeSeriesPlot.png](https://github.com/gordonchen07/Manhattan-Crime/blob/master/TimeSeriesPlot.png)

### Data Sources
#### NYC Open Data
NYPD Complaint Data Historic
https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i

This dataset contains details on every crime reported to NYPD from January 1, 2006 to December 31, 2017. Such details include: date and time of occurrence, type of crime, precinct jurisdication, borough, latitude, longitude, suspect race, victim age, etc.


### Deliverables
#### Jupyter Notebooks
* [FindManhattanCrime.ipynb] Start with this notebook to find all crimes reported in Manhattan. Data cleaning is performed to focus on the date/time of crime, type of crime and location of occurrence.

##### Manhattan Borough Crime
* [MisdemeanorTimeSeries.ipynb] Next use this notebook to separate and save the 3 types of crime into 3 dataframes. This notebook will also analyze and perform a Time Series forecast of the Misdemeanor crimes.
* [FelonyTimeSeries.ipynb] This notebook analyzes and performs a Time Series forecast of the Felony crimes.
* [ViolationTimeSeries.ipynb] This notebook analyzes and performs a Time Series forecast of the Violation crimes.

##### Manhattan Zipcode Crime
* [ConvertToEPSG2263.ipynb] This notebook converts the latitude/longitude provided by the NYPD crime dataset from EPSG4326 to EPSG2263 because the Shapefile I am using only recognizes EPSG2263. The notebook segments the converted data into 15 batch files because there is over 1.4million data points to process.
* [CoorZipConverter.ipynb] This notebook will take the new EPSG2263 coordinates and search through the Shapefiles records for the zipcode that the coordinates exist in.
* [CheckZipcodeinMhtn.ipynb] This notebook will take zipcodes and cross reference with a list of known Manhattan zipcodes.
* [ConcatenatingBatches.ipynb] This notebook will take all the batches of cross-referenced datasets with zipcodes and concatenate them together.
* [Zipcode Pipeline.ipynb] This notebook is a pipeline to analyze and perform a Time Series forecast for an input zipcode of Manhattan.
* [MakingHeatMap.ipynb] This notebook will take all the data series and forecasts of each zipcode of Manhattan and aggregate the data into a heat map that changes colors depending on the density of crime in each zipcode.

#### Visualizations
* [ManhattanCrimeBokehPlot.html] A Bokeh Plot of the 3 types of crime in Manhattan with forecasting of crime rates.
* [ManhattanZipcodeCrime.mp4] A video of stitched images of Manhattan crime density plotted by zipcode on a heat map.


### Conclusion and Presentation
* https://docs.google.com/presentation/d/1Y7x_JoiwTzxWsEeGOYmsuFzWwbbDQoAcLNlERFJTkxk/edit?usp=sharing
