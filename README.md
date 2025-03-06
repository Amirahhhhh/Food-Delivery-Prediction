# Food-Delivery-Prediction
Predict the estimated delivery time for food orders using machine learning.

# 1.	📌 PROJECT OVERVIEW

This project aims to predict the estimated delivery time for food orders using machine learning. By analyzing various factors such as order details, restaurant location, delivery distance, weather conditions, and traffic patterns, we aim to build a robust model that provides accurate delivery time estimates. 

# 2.	📊 ABOUT THE DATASET
The dataset includes key details influencing delivery time, such as:

|     Feature names                  |     Description                                                                          |
|------------------------------------|------------------------------------------------------------------------------------------|
|     ID                             |     Represents a unique   identification of an entry.                                    |
|     Delivery_person_ID             |     Represents a unique   identification of a delivery person.                           |
|     Delivery_person_Age            |     Represents the age of a delivery   person.                                           |
|     Delivery_person_Ratings        |     Represents the average ratings   given to the delivery person                        |
|     Restaurant_latitude            |     Represents the latitude of the   restaurant.                                         |
|     Restaurant_longitude           |     Represents the longitude of the   restaurant.                                        |
|     Delivery_location_latitude     |     Represents the latitude of the   delivery location.                                  |
|     Delivery_location_longitude    |     Represents the longitude of the   delivery location.                                 |
|     Order_Date                     |     Represents the date when the   order was placed.                                     |
|     Time_Orderd                    |     Represents the time when the   order was placed.                                     |
|     Time_Order_picked              |     Represents the time when the   order was picked from the restaurant.                 |
|     Weatherconditions              |     Represents the weather   conditions                                                  |
|     Road_traffic_density           |     Represents the road traffic   density                                                |
|     Vehicle_condition              |     Represents the condition of the   vehicle (Smooth, Good, or Average).                |
|     Type_of_order                  |     Represents the type of order   (Snack, Meal, Buffet, Drinks, etc.).                  |
|     Type_of_vehicle                |     Represents the type of vehicle   used                                                |
|     multiple_deliveries            |     Represents the number of orders   to be delivered in one attempt.                    |
|     Festival                       |     Represents whether the day is   festive or not.                                      |
|     City                           |     Represents the city.                                                                 |
|     Time_taken(min)                |     Represents the time taken by the   delivery person to deliver the order. [TARGET]    |


Dataset can be access through the link :
https://www.kaggle.com/code/gauravmalik26/food-delivery 

# 3.	🎯 OBJECTIVE
•	Build a predictive model to estimate food delivery time based on historical data.
•	Analyze the impact of different features on delivery times.

# 4.	🔎 METHODOLOGY

## 	Data Preprocessing
o	Data consistency (change data type to numeric, datetime or timedelta) 
o	Handle missing values (fill with mean for numerical features and mode for categorical features)
o	Check for outliers using IQR 

## 	Feature Engineering
o	Extract new features 'month', 'day_of_week' and 'is_weekend' 
o	Calculate 'Order_prepare_time'. This is the amount of time it took for the order to be prepared by the restaurant.  It is calculated as the difference between the order pickup time and the order received time, measured in minutes.
o	Compute distance (in km) using geodesic method between the latitude and longitude of the restaurant and the delivery location

## 	Exploratory Data Analysis (EDA)
o	Analyze distributions of features (univariate, bivariate and multivariate)

## 	Data Transformation
o	Transform categorical features  using Label Encoder and scale numerical features using Standard Scaler

## 	Feature Selection 
o	Train and compared Random Forest models using different feature sets.
o	All Features: Trained a Random Forest model using the full feature set and evaluated performance using R²
o	Random Forest Selected Features: Used feature selection based on Random Forest importance scores, trained a new model, and measured R²
o	Lasso Selected Features: Applied Lasso regression for feature selection, trained a model using only the selected features, and compared R²

## 	Model Building & Evaluation
o	Trained eight models, including Linear Regression, Ridge, Lasso, Random Forest, Gradient Boosting, SVR, XGBoost, and KNN.
o	Evaluate the performance of each model using R² Score, Mean Absolute Error (MAE), and Root Mean Squared Error (RMSE) 

## 	Hyperparameter Tuning 
o	Tuned Random Forest, Gradient Boosting, and XGBoost (top-performing models)
o	Compared performance using all features vs. selected features (Random Forest)
o	Used GridSearchCV with 5-fold cross-validation to find the best hyperparameters 
o	The best-tuned model for final predictions

# 5.	⚙️ RESULT 
•	Higher R² Score when training will all features compared to training with selected features. XGBoost (0.813150), Random Forest (0.808772), Gradient Boosting (0.774242)
•	Improved model performance after hyperparameter tuning when training will all features. XGBoost (0.821292), Random Forest (0.822633), Gradient Boosting (0.819862)

![image](https://github.com/user-attachments/assets/684a64e3-dd73-4703-a4c8-97bb80a58a20)
