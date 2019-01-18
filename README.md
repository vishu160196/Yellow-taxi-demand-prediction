# Yellow-taxi-demand-prediction
Predict demand for yellow taxis in New York City
## Data source
http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml

## Problem type
Time series prediction/regression

## Divide NYC into regions and time values into pickup bins
Divide the time into bins of 10 minutes<br>
Use KMeans clustering to divide the city of New York into regions based on pickup density of 2015 values and average intercluster distance

## Feature extraction for time series prediction
1. Use jan, feb, march 2016 filled data (missing values filled with zeros) to extract exponentially weighted moving averges
   of past values
2. One hot encode days of week
3. Take pickup bin value one week earlier as a feature
4. Take pickup bin value one day earlier as a feature
5. Take last 5 pickup bin values as 5 features
6. Take max, min of last 5 pickup values as 2 features
7. Take std dev of last 10 values as 1 feature
8. Take 120 point DFT of pickup values in last 2 hours i.e. 120 bins
