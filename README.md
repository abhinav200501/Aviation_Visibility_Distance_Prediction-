# Aviation Visibility Distance Prediction

## Overview

This project develops a machine learning system to predict **visibility distance in aviation** using historical weather data.

Visibility is an important factor in aviation, particularly during takeoff, landing, and navigation. The objective of this project is to use weather-related parameters such as temperature, humidity, wind speed, wind direction, pressure, and precipitation to predict visibility distance.

This project follows an end-to-end machine learning workflow involving:

- Exploratory Data Analysis
- Feature Engineering
- Correlation Analysis
- Outlier Handling
- Feature Scaling
- Clustering Analysis
- Regression Modeling
- Hyperparameter Optimization
- Model Evaluation

---

## Problem Statement

Visibility distance is affected by several atmospheric and weather conditions. Poor visibility can create challenges for pilots and Air Traffic Control (ATC).

The objective of this project is:

> Given historical weather conditions, can we predict the visibility distance using machine learning?

The dataset contains weather-related variables including:

- Dry Bulb Temperature
- Wet Bulb Temperature
- Dew Point Temperature
- Relative Humidity
- Wind Speed
- Wind Direction
- Station Pressure
- Sea Level Pressure
- Precipitation

---

## Solution Approach

This is a **supervised machine learning regression problem** because visibility distance is available as the target variable.

The overall approach was:

```text
Historical Weather Data
        ↓
Data Analysis
        ↓
Correlation Analysis
        ↓
Feature Selection
        ↓
Outlier Handling
        ↓
Feature Scaling
        ↓
K-Means Clustering
        ↓
Regression Models
        ↓
Model Comparison
        ↓
GridSearchCV
        ↓
Final Random Forest Model
        ↓
Visibility Distance Prediction

---

Exploratory Data Analysis
Dataset Understanding

The first step was to understand the structure and characteristics of the aviation weather dataset.

The dataset contains weather observations along with visibility measurements.

The major features analyzed were:

Feature	Description
DryBulbTempF	Dry bulb air temperature
WetBulbTempF	Wet bulb temperature
DewPointTempF	Dew point temperature
RelativeHumidity	Relative humidity of the air
WindSpeed	Wind speed
WindDirection	Direction of wind
StationPressure	Atmospheric pressure at the station
SeaLevelPressure	Atmospheric pressure adjusted to sea level
Precipitation	Amount of precipitation
Visibility	Target variable representing visibility distance
