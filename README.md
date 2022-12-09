# Fuel-Forecasting
Traditional ML Regression on Fuel data

### By:
Alex B Tucker
12/05/2022

------------------------

## Dataset Info:
The data consists of gas station availability over numerous gas stations across 12 counties in Louisiana.
The data was taken in 8-hour intervals from 8/27/2021 to 10/6/2021, a period of time marked by the Atlantic Hurricane Season and the impact of Hurricane Ida.
Each data point has a timestamp, FIP (county) code, zip code, and gas station availiablity data.
The dataset was provided by Dr. Raju, from the University of Louisiana at Lafayette.

------------------------

## Target Variable
The target variable is to try and predict the avalability of fuel in a county 24-hours in advance, which is useful during emergencies, such as a hurricane.

------------------------

## Data Processing:
Gas stations were grouped based on county. This gave a set of 12 counties, with gas station avalability projected over time per county.
The percentage operational for each county was created by dividing the number of gas stations with fuel and power by the number of total gas stations in the respective county.
Multiple features were generated from the percentage operational, such as moving averages, moving standard deviations, etc.
Data was organized in two different ways, as described below:

### Long Feature Table:
In this method, a column describing which county the data belonged to was one-hot encoded. The target variable in this case was to simply predict the percentage operational, and see if the county code had any effect on the model.

### Wide Feature Table:
In this method, each 'percentage operational' type feature mas mutiplied by the number of counties.  For example, there was a moving average for the counties of Ascension, Orleans, East Baton Rouge, etc. This led to a 'wide' feature table due to the sheer number of features.

------------------------

## Models Used:

Linear Regression, Ridge Regression, Lasso Regression, PCA feature selection + Lin Reg

------------------------

## Files:

Dataset:
GasStationDataSet_Partial.csv

Data Visualization:
Python_FuelForecasting_VISUALIZATION.ipynb

Long Feature Table models:
FuelForecasting2-LONG.ipynb

Wide Feature Table models:
FuelForecasting3-WIDE.ipynb
