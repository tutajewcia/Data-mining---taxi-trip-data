# Taxi Data Analysis

## Project Overview

This project analyzes taxi trip data to uncover insights and trends related to travel patterns, payments, and driver performance. The dataset includes detailed information about taxi rides, such as travel time, distance, costs, and geographical details. The goal of this project is to clean, explore, and model the data to draw conclusions based on the data provided.

## Dataset Description

The dataset contains 10,000 rows and 25 columns, which include:

- **Identifiers**: Unique trip ID, taxi ID.
- **Trip Details**: Start and end time, duration, distance, fare, tips, tolls, and extras.
- **Location Data**: Pickup and drop-off areas, latitude, longitude.
- **Other Information**: Payment type, taxi company, and trip year/month.

## Objectives

1. **Data Quality Assessment**: Evaluate the quality and completeness of the dataset.
2. **Exploratory Data Analysis (EDA)**:
   - Identify popular pickup and drop-off areas.
   - Analyze payment types, most frequently used taxi companies, and top-performing drivers.
   - Examine yearly trends in taxi usage.
3. **Feature Engineering**:
   - Add a new feature `speed` to evaluate its influence on tips.
4. **Modeling**: Predict the amount of tips using machine learning models (e.g., Random Forest, Linear Regression).

## Methodology

### Data Cleaning

- Replaced non-numeric values (e.g., `"out of town"`) with numeric equivalents.
- Removed unnecessary columns such as precise location data (`pickup_latitude`, `dropoff_longitude`) and timestamps (`trip_start_timestamp`, `trip_end_timestamp`).
- Filtered outliers based on boxplots for key numerical variables (`trip_seconds`, `trip_miles`, `trip_total`).

### Exploratory Analysis

1. **Geographical Trends**:
   - Most trips originated from areas `8`, `32`, and `"out of town"`.
   - Popular destinations included areas `"out of town"`, `8`, and `33`.
2. **Temporal Patterns**:
   - The highest number of trips occurred in 2013.
3. **Payment Analysis**:
   - Cash payments dominated (75%), followed by credit cards.
4. **Taxi Company Performance**:
   - Most trips were from unnamed taxis, followed by `303 Taxi` and `Metro Group`.

### Machine Learning Models

- **Random Forest** and **Linear Regression** were used to predict tips.
- Features such as `fare`, `trip_seconds`, `trip_miles`, and `speed` were included in the model.

#### Model Comparison:

| Metric       | Random Forest (Test) | Linear Regression (Test) |
|--------------|-----------------------|--------------------------|
| MAPE         | 25.52%               | 22.43%                  |
| MAE          | 0.67                 | 0.59                    |

While Random Forest performed better on training data, Linear Regression generalized better on test data.

## Results and Insights

- The median trip duration is 11 minutes, covering a distance of 1.83 miles on average.
- The average trip cost is approximately $11, with a median tip of $2.
- Random Forest achieved higher accuracy in predicting tips, but Linear Regression was more robust.

## Future Work

- Use cross-validation to improve model performance and reduce overfitting.
- Explore additional features such as time of day or weather conditions.
- Integrate geospatial analysis for a more detailed study of trip patterns.
