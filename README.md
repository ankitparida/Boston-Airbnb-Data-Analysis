# BOSTON AIRBNB EXPLORATORY DATA ANALYSIS

## Introduction
This repository contains Datasets which were Released by AirBnb and a jupyter notebook with detailed Data analysis performed on these datasets. The AirBnb Boston datasets compromised of 3 parts:
  
  1.listings.csv: Listings and their details.
  
  2.calender.csv: Availability information at a day-by-day level.
  
  3.reviews.csv: Reviews for each listing .

## What are the main questions which we are trying to answers?
  1. Which time of the year is the peak tourist season?
  2. How price of a room is corelated with other attributes?
  3. Which streets accommodates the most expensive AirBnb Homes?

We are also trying to build a predictive model which will predict the price of a AirBnb using different attributes. The algorithms used are MultiLinear Regression, KNN Regressor and Random Forest Regressor.

## Libraries Used

  1. Numpy
  2. Pandas
  3. Seaborn
  4. Matplotlib
  5. Warnings
  6. Sklearn: model_selection,preprocessing, metrics, Linear Model, Ensemble, neighbors

# Results & Conclusion

1. We found that the month of October and September are the peak tourist season.
2. The variables such as 'accommodates','bedrooms','beds','bathrooms','guests_included' are strongly correlated with Price which means these attributes strongly define the price of airbnb property.
3. Boston Wharf Road followed by Congress Street & 8th Street are the most expensive Streets.
4. Out of three models (multilinear Regression, Random Forest and KNN Regressor), the rmse value of Multi Linear Regression model is low. However the value is quite high, this model needs to be optimized further.

I have also written a post regarding boston airbnb data analysis which can be accessed by below link:
https://medium.com/@ankitparida/airbnb-boston-exploratory-data-analysis-a8dc4d45c946
