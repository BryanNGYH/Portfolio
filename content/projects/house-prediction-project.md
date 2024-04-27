---
title: "House Prediction Project"
description: "Using Machine Learning to make a smart purchase (not getting a huge lump of debt)"
dateString: March 2024 
draft: false
tags: ["Python", "Numpy", "Scikit Learn", "xgboost", "Linear Regression", "Decision Tree", "Lasso Regression", "Flask", "HTML", "CSS","JavaScript"]
showToc: false
weight: 202
cover:
    image: "projects/house-price-prediction/display.webp"
--- 
### 🔗 [Github](https://github.com/BryanNGYH/House-Price-Prediction-Project)

## Description
In this project, I utilized Data Analysis & Machine Learning methods to help interested buyers to estimate house prices in Bangalore (India).
Furthermore, I built a website using HTML, CSS and JavaScript which user can input features like number of bedrooms, location or size to get an estimated price of the house.

## Data Preprocessing
To train the Machine Learning model, I preprocessed and cleaned the data to ensure the model can accurately predict with consistent performance. Here are the steps that I have took:-

- Check for duplicated data input and remove them
- Used mean imputation to fill in missing value for 'balcony' column
- Remove missing values that are less than 1% of the total dataset
- Feature engineered 'total_sqft' which have inconsistent metrics :-
    1. Replaced range values with mean value of the min and max value
    2. Converted other metrics into square feet 
- Feature engineered 'bhk' columns to extract the number of rooms
- Performed Label Encoding on 'availability' column
- Feature engineered 'location' columns to reduce the number of unique values by labelling location with less than or equal to 10 entries as 'others'
- Removed outliers to ensure consistent model training

## Model Building
Before the data is loaded into the model for training, once again I check the correlation between features used for prediction to avoid multicollinearity.

Below is the screenshot of correlation between features.
![correlation between features](/projects/house-price-prediction/correlation_of_features.png)

As 'bath' and 'rooms' have high correlation, I have selected only 'rooms' feature for training and prediction. The final features used to predict the models are as follows:-
- **availability**
- **balcony**
- **rooms**
- **locations**

I used dummy variable to transform 'location' columns as it is a categorical variable. Then I used 80% of the dataset for training and the remaining as test set.

Here, I tested 4 regression model to predict the house prices. 

- **Linear Regression** - Used as a baseline model
- **Lasso Regression** - Used to avoid overfitting with its penalty term and also its ability to perform feature selection, as it eliminates irrelevant or redundant predictors from the model which results in a sparse model
- **Decision Tree Regressor** - Used to capture possible non-linear relationship between features for the variable.
- **XG Boost Regressor** - Chosen as it trains on weak learner (tree) and *usually* have higher accuracy


## Model Performance
As expected, XG Boost Regressor is the best model and outperformed (Accuracy) others on the test dataset.

    1. XG Boost Regressor - 0.77
    2. Decision Tree Regressor - 0.70
    3. Linear Regression - -19.70
    4. Lasso Regression - -24.43

## Productionization of the model
![UI](/projects/house-price-prediction/UI_picture.png)
In the last step, I used the pickled model and exported it to a Python Flask server. The server is hosted on a local web server and provides HTTP endpoints to handle incoming requests.

Furthermore, I have also built a simple website using HTML, CSS and JavaScript which allows users to input entries and make an estimation (prediction) of house prices with the model running on FLask. With GET and POST requests to the Flask server, users can key in neccesary entries and gain access to the list of locations.
