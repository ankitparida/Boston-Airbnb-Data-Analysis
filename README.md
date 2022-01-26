# BOSTON AIRBNB EXPLORATORY DATA ANALYSIS USING CRISPDM

## Introduction

Boston, officially the City of Boston, is the capital and most populous city of the Commonwealth of Massachusetts in the United States and 24th-most populous city in the country. According to the Airbnb datasets, there are around 3,349 Airbnb homes present including private rooms, shared rooms and entire apartments in Boston itself.
Before booking any Airbnb homes we have several questions running on our mind related to Price, Reviews, locations etc. Here I am trying to answer some of the basic questions with the help of the datasets which we have using CRISP DM Methodology. The whole analysis is divided into two parts- EDA and Predictive Analysis.

## CRISP-DM
![CRISP-DM Workflow](https://www.kdnuggets.com/wp-content/uploads/crisp-dm-deployment-fig1.png)


## STAGE ONE – DETERMINE BUSINESS OBJECTIVES

Before booking any Airbnb homes we have several questions running on our mind related to Price, Reviews, locations etc. The main business objective here is to uncover the hidden trends and information present in the airbnb datasets to answer some basic questions.

## What are the main questions which we are trying to answers?
  1. Which time of the year is the peak tourist season?
  2. How price of a room is corelated with other attributes?
  3. Which streets accommodates the most expensive AirBnb Homes?

Apart from this above questions what if someone needs estimates what the price of a airbnb home could be. So I am also trying to build a predictive model which will predict the price of a AirBnb using different attributes. The algorithms used are MultiLinear Regression, KNN Regressor and Random Forest Regressor.

## STAGE TWO – DATA UNDERSTANDING

This repository contains Datasets which were Released by AirBnb and a jupyter notebook with detailed Data analysis performed on these datasets. The AirBnb Boston datasets compromised of 3 parts:
  
  1.listings.csv: Summary information and metrics for listings in Boston. 
  
  2.calender.csv: Detailed Calendar Data for listings in Boston (day to day basis).
  
  3.reviews.csv: Summary Review data and Listing ID (to facilitate time based analytics and visualisations linked to a listing).
  
## STAGE THREE – DATA PREPARATION

I am mainly focusing on first two datasets.

- To answer the first question 'Which time of the year is the peak tourist season?', I am using the Calender dataset. The availability column contains two values- 't' and 'f' which I have converted into boolean type( t--> True and f--> False) and then divided the datasets into two parts- boston_calender_available & boston_calender_not_available based on the availability column.

![boston_calender_available](https://user-images.githubusercontent.com/30798966/151104880-4b8d5e95-e637-4cb8-8d34-1939bed28ebd.JPG)
![boston_calender_not_available](https://user-images.githubusercontent.com/30798966/151104887-343cabc1-3ddb-4c5e-92e3-e5dec9711af4.JPG)

- To answer the second question 'How price of a room is corelated with other attributes?', I am using the listings dataset. The Price column contains string values which needs to be converted into floating type before finding the correlation between price and other attributes.

- To answer the third question- 'Which streets accommodates the most expensive AirBnb Homes?', I am using the listings dataset again. Initially the street column contains the full address of the airbnb home. So I have written a function to filter out the street names from the full addresses.

- After performing statistical analysis, the attributes which I am using to predict the price of a Airbnb homes are 'accommodates','bedrooms','bathrooms','beds','minimum_nights','maximum_nights','number_of_reviews','room_type','bed_type','guests_included'. These attributes were present in the listing dataset. 

-To convert the categorical variables I have used the pandas's get_dummies function and then used the standard scaler to transform the data before model creation step.

## STAGE FOUR – MODELLING

For Visualizing the data and to answers the business questions we have used various plotting techniques provided by matplotlib and seaborn libraries 

Finally, we train a model using a Machine learning library like scikit-learn to pick an appropriate algorithm and built a model that can make a prediction using a validation set. We use the k-nearest neighbors (kNN)algorithm, Multi Linear Regression and Random Forest Regressor Algorithm. 

## STAGE FIVE – EVALUATION

To evaluate the performance of the Prediction Model, we use a metric called root mean squared error(RMSE). RMSE is frequently used measure of the differences between values (sample or population values) predicted by a model or an estimator and the values observed.
The RMSE of Multi Linear Regression Model: 104.106612459728, RandomForest Regressor: 106.42255556446031, RMSE of KNN: 109.57867318952867. The lesser the difference between predicted and Actual Values, the better the model. 

To answer the first three business questions, we used various visualization Techniques.

![1](https://user-images.githubusercontent.com/30798966/151108610-fc639615-89a1-405b-a4ec-b1f9ab8f1c56.JPG)
![2](https://user-images.githubusercontent.com/30798966/151108616-c2e9c505-85f9-40b8-9a26-6977613c280a.JPG)
![3](https://user-images.githubusercontent.com/30798966/151108621-7e5ed58e-770b-4942-ad4c-9950034b57c4.JPG)

# Results & Conclusion

1. We found that the month of October and September are the peak tourist season.
2. The variables such as 'accommodates','bedrooms','beds','bathrooms','guests_included' are strongly correlated with Price which means these attributes strongly define the price of airbnb property.
3. Boston Wharf Road followed by Congress Street & 8th Street are the most expensive Streets.
4. Out of three models (multilinear Regression, Random Forest and KNN Regressor), the rmse value of Multi Linear Regression model is low. However the value is quite high, this model needs to be optimized further.

# Libraries Used

  1. Numpy
  2. Pandas
  3. Seaborn
  4. Matplotlib
  5. Warnings
  6. Sklearn: model_selection,preprocessing, metrics, Linear Model, Ensemble, neighbors

# Acknowledgements
I would like to give credit to:

* ![Inside Airbnb](http://insideairbnb.com/get-the-data.html)
* ![Github Docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* ![Udacity](https://classroom.udacity.com/nanodegrees/nd025)
* ![ML Algos](https://machinelearningmastery.com/)



I have also written a post regarding boston airbnb data analysis which can be accessed by below link:
https://medium.com/@ankitparida/airbnb-boston-exploratory-data-analysis-a8dc4d45c946
