# Bike-sharing-MLR
Bike sharing Multilinear regression

# Problem Statement

A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

## Business Understanding

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 


### Business Objectives

BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.


They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

- Which variables are significant in predicting the demand for shared bikes.
- How well those variables describe the bike demands

Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 


### Business Goal

We are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

### Data Preparation

- We can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
- We might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, we might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 

### Model Building

In the dataset provided, We will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. The model should be built taking this 'cnt' as the target variable.

### BUILDING A LINEAR MODEL

### Recursive feature elimination: 

- We will be using the **** LinearRegression function from SciKit Learn **** for its compatibility with RFE (which is a utility from sklearn)

- Building Linear Model using 'STATS MODEL'

### Model Evaluation

Once done with model building and residual analysis and have made predictions on the test set, just make sure we use the following two lines of code to calculate the R-squared score on the test set. 

```
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
``` 

where y_test is the test data set for the target variable, and y_pred is the variable containing the predicted values of the target variable on the test set.
Please don't forget to perform this step as the R-squared score on the test set holds some marks. The variable names inside the 'r2_score' function can be different based on the variable names we have chosen.

### Final Result Comparison¶
- Train R^2 :0.819
- Train Adjusted R^2 :0.816
- Test R^2 :0.808
- Test Adjusted R^2 :0.799
- This seems to be a really good model that can very well 'Generalize' various datasets

### Final result

As per our final Model, the top 3 predictor variables that influences the bike booking are:

- Temperature (temp) - A coefficient value of ‘0.563445’ indicated that a unit increase in temp variable increases the bike hire numbers by 0.563445 units.
- Weather Situation 3 (weathersit_3) - A coefficient value of ‘-0.301879’ indicated that, w.r.t Weathersit1, a unit increase in * Weathersit3 variable decreases the bike hire numbers by 0.301879 units.
- Year (yr) - A coefficient value of ‘0.231012’ indicated that a unit increase in yr variable increases the bike hire numbers by 0.231012 units.

So, it's suggested to consider these variables utmost importance while planning, to achive maximum Booking The next best features that can also be considered are

- season_4: - A coefficient value of ‘0.126749’ indicated that w.r.t season_1, a unit increase in season_4 variable increases the bike hire numbers by 0.126749 units.
- windspeed: - A coefficient value of ‘-0.157640’ indicated that, a unit increase in windspeed variable decreases the bike hire numbers by 0.157640 units.

### NOTE:

The details of weathersit_1 & weathersit_3

- weathersit_1: Clear, Few clouds, Partly cloudy, Partly cloudy

- weathersit_3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds

The details of season1 & season4
- season1: spring

- season4: winter


