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

# Exploratory Data Analysis

## Dataset Understanding

The first step was to understand the structure and characteristics of the aviation weather dataset.

The dataset contains weather observations along with visibility measurements.

The major features analyzed were:

| Feature | Description |
|---------|-------------|
| `DryBulbTempF` | Dry bulb air temperature |
| `WetBulbTempF` | Wet bulb temperature |
| `DewPointTempF` | Dew point temperature |
| `RelativeHumidity` | Relative humidity of the air |
| `WindSpeed` | Wind speed |
| `WindDirection` | Direction of wind |
| `StationPressure` | Atmospheric pressure at the station |
| `SeaLevelPressure` | Atmospheric pressure adjusted to sea level |
| `Precipitation` | Amount of precipitation |
| `Visibility` | Target variable representing visibility distance |

---

## Data Types and Missing Values

The dataset was initially inspected to understand:

- Number of observations
- Number of features
- Data types
- Missing values
- Duplicate records
- Numerical distributions

The analysis showed that:

- The dataset contained **no missing values**.
- Most variables were numerical weather measurements.
- The target variable was continuous and therefore suitable for regression.

Since there were no missing values, no imputation step was required for the original dataset.

---

## Univariate Analysis

Distribution analysis was performed on the numerical variables to understand their:

- Central tendency
- Spread
- Skewness
- Extreme values
- Distribution patterns

Histograms and distribution plots were used to examine features such as:

- Temperature
- Humidity
- Wind Speed
- Pressure
- Precipitation
- Visibility

### Observations

The analysis showed that several weather variables were not normally distributed.

In particular:

- `Precipitation` contained a large number of values close to zero.
- `WindSpeed` contained some extreme observations.
- `SeaLevelPressure` also contained potential outliers.
- Several temperature and pressure features showed similar distribution patterns.

---

## Precipitation Analysis

The `Precipitation` feature was analyzed separately because a large proportion of its observations were close to zero.

This indicated that precipitation was relatively sparse in the dataset.

The distribution was highly concentrated around zero, with fewer observations having significant precipitation.

This characteristic was considered during the feature analysis and modeling process.

---

## Correlation Analysis

A correlation matrix was generated to understand relationships between weather variables and visibility.

Correlation analysis revealed strong relationships between several weather features.

In particular:

- `WetBulbTempF`
- `DewPointTempF`
- `StationPressure`

showed high correlation with other features.

Highly correlated variables can provide redundant information and may introduce multicollinearity into models.

---

## Feature Selection

Based on the correlation analysis, the following features were removed:

```text
WetBulbTempF
DewPointTempF
StationPressure
