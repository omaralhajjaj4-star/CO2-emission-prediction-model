# CO2-emission-prediction-model
Using a public dataset, this model predicts the amount of co2 emissions based on the most relevant variables

CO₂ Emission Prediction Model

This project develops a machine learning model to predict the CO₂ emissions of vehicles based on their specifications. Using a Multiple Linear Regression algorithm, the model analyzes data on vehicle fuel consumption to provide highly accurate predictions.

Dataset

The model is trained on the CO2 Emission Dataset.csv file, which contains fuel consumption ratings and CO₂ emission data for various vehicles.

Description

The dataset consists of 7,385 records and 12 distinct features. An initial exploratory data analysis confirmed that the dataset is complete, with no missing or null values, streamlining the preprocessing phase.1

Features

The dataset includes the following columns:
Column Name
Description
Make
The brand of the vehicle manufacturer (e.g., ACURA, BMW).
Model
The specific model of the vehicle (e.g., ILX, 320i).
Vehicle Class
The classification of the vehicle (e.g., COMPACT, SUV).
Engine Size(L)
The engine's displacement in litres.
Cylinders
The number of cylinders in the engine.
Transmission
The type of transmission (e.g., AS5, M6).
Fuel Type
The type of fuel used (e.g., Z, D, X, E).
Fuel Consumption City (L/100 km)
Fuel consumption in the city, in litres per 100 km.
Fuel Consumption Hwy (L/100 km)
Fuel consumption on the highway, in litres per 100 km.
Fuel Consumption Comb (L/100 km)
Combined (55% city, 45% hwy) fuel consumption in L/100 km.
Fuel Consumption Comb (mpg)
Combined fuel consumption in miles per gallon.
CO2 Emissions(g/km)
(Target Variable) The tailpipe emissions of CO₂ in grams per kilometre.


Methodology

The project follows a structured approach from data exploration to model deployment, as detailed in the CO2 prediction model.ipynb notebook.1

1. Exploratory Data Analysis (EDA)

The dataset was initially inspected to understand its structure, data types, and statistical properties. This phase included analyzing the distribution of vehicle makes and their average emissions. A key finding was that while Bugatti vehicles had the highest average emissions, this was identified as an unrepresentative outlier due to the very small sample size (only three entries).1

2. Correlation Analysis and Feature Selection

A correlation heatmap was generated to visualize the linear relationships between the numerical features and the target variable, CO2 Emissions(g/km). This analysis was crucial for feature selection.
The final model was developed through an iterative process. An initial model was built using only the two features with the highest correlation. To improve performance and avoid multicollinearity, a more refined model was then constructed. This final model uses a carefully selected set of features by dropping redundant columns like city/highway-specific fuel consumption and the mpg rating, as the combined consumption in L/100 km was found to be a more comprehensive predictor.1

3. Model Training

The final predictive model is a Multiple Linear Regression algorithm from the scikit-learn library. The dataset was split into training (80%) and testing (20%) sets to ensure an unbiased evaluation of the model's performance.
The model was trained using the following numerical features:
Engine Size(L)
Cylinders
Fuel Consumption Comb (L/100 km)

Results and Performance

The final model's performance was evaluated on the unseen test set. The results demonstrate a very high level of accuracy and predictive power.
The model achieved an R² Score of approximately 0.97, indicating that it can explain about 97% of the variability in vehicle CO₂ emissions based on the selected features. This high score signifies a strong and reliable predictive model.1 A custom function, eval_metric, was used to calculate the complete performance metrics, including Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE), confirming the model's minimal error.
