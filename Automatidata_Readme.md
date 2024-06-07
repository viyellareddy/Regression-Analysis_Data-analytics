
# Automatidata Project: Multiple Linear Regression Analysis

## Project Overview

"Regression Analysis: Simplify Complex Data Relationships." The data consulting firm Automatidata has recently hired you as the newest member of their data analytics team. Their newest client, the NYC Taxi and Limousine Commission (New York City TLC), wants the Automatidata team to build a multiple linear regression model to predict taxi fares using existing data that was collected over the course of a year. The aim is to build and evaluate a multiple linear regression model and update the client on the progress.

## Dataset

This project uses a dataset called `2017_Yellow_Taxi_Trip_Data.csv`. It contains data gathered by the New York City Taxi & Limousine Commission and published by the city of New York as part of their NYC Open Data program. In order to improve the learning experience and shorten runtimes, a sample was drawn from the 113 million rows in the 2017 Yellow Taxi Trip Data table.

### Data Dictionary

The dataset contains 408,294 rows and 18 columns:

| Column Name            | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ID`                   | Trip identification number.                                                                                                                             |
| `VendorID`             | A code indicating the TPEP provider that provided the record. 1 = Creative Mobile Technologies, LLC; 2 = VeriFone Inc.                                   |
| `tpep_pickup_datetime` | The date and time when the meter was engaged.                                                                                                            |
| `tpep_dropoff_datetime`| The date and time when the meter was disengaged.                                                                                                         |
| `Passenger_count`      | The number of passengers in the vehicle. This is a driver-entered value.                                                                                 |
| `Trip_distance`        | The elapsed trip distance in miles reported by the taximeter.                                                                                           |
| `PULocationID`         | TLC Taxi Zone in which the taximeter was engaged.                                                                                                        |
| `DOLocationID`         | TLC Taxi Zone in which the taximeter was disengaged.                                                                                                     |
| `RateCodeID`           | The final rate code in effect at the end of the trip. 1 = Standard rate; 2 = JFK; 3 = Newark; 4 = Nassau or Westchester; 5 = Negotiated fare; 6 = Group ride |
| `Store_and_fwd_flag`   | This flag indicates whether the trip record was held in vehicle memory before being sent to the vendor, aka “store and forward,” because the vehicle did not have a connection to the server. Y = store and forward trip; N = not a store and forward trip |
| `Payment_type`         | A numeric code signifying how the passenger paid for the trip. 1 = Credit card; 2 = Cash; 3 = No charge; 4 = Dispute; 5 = Unknown; 6 = Voided trip       |
| `Fare_amount`          | The time-and-distance fare calculated by the meter.                                                                                                      |
| `Extra`                | Miscellaneous extras and surcharges. Currently, this only includes the $0.50 and $1 rush hour and overnight charges.                                      |
| `MTA_tax`              | $0.50 MTA tax that is automatically triggered based on the metered rate in use.                                                                          |
| `Improvement_surcharge`| $0.30 improvement surcharge assessed trips at the flag drop. The improvement surcharge began being levied in 2015.                                       |
| `Tip_amount`           | Tip amount. This field is automatically populated for credit card tips. Cash tips are not included.                                                      |
| `Tolls_amount`         | Total amount of all tolls paid in trip.                                                                                                                  |
| `Total_amount`         | The total amount charged to passengers. Does not include cash tips.                                                                                      |

## Project Structure

The project follows the PACE problem-solving framework:

1. **Plan**
2. **Analyze**
3. **Construct**
4. **Execute**

### 1. Plan

#### Tasks:

- **Imports and Loading**: Import necessary libraries and load the dataset.
- **Exploratory Data Analysis (EDA)**: Inspect and clean the dataset, check for missing values and outliers, and understand data distributions.

### 2. Analyze

#### Tasks:

- **EDA and Checking Model Assumptions**: Identify outliers, handle missing data, check for multicollinearity, and create new features.
- **Feature Engineering**: Create new columns such as `duration`, `mean_distance`, `mean_duration`, `day`, `month`, and `rush_hour`.

### 3. Construct

#### Tasks:

- **Build the Multiple Linear Regression Model**:
  - Split the data into training and testing sets.
  - Standardize the data.
  - Fit the model using training data.
  - Evaluate model performance on training and testing data.

### 4. Execute

#### Tasks:

- **Evaluate and Interpret the Model**:
  - Visualize actual vs. predicted values.
  - Analyze residuals.
  - Interpret model coefficients.

## Key Insights and Visualizations

### Exploratory Data Analysis

- **Outliers**: Identified outliers in `trip_distance`, `fare_amount`, and `duration` columns.
- **Missing Values**: No missing values were found in the dataset.
- **New Features**: Created new columns `duration`, `mean_distance`, `mean_duration`, `day`, `month`, and `rush_hour`.

### Model Building and Evaluation

- **Model Performance on Training Data**:
  - R²: 0.84
  - Mean Absolute Error (MAE): 2.19
  - Mean Squared Error (MSE): 17.89
  - Root Mean Squared Error (RMSE): 4.23

- **Model Performance on Testing Data**:
  - R²: 0.87
  - Mean Absolute Error (MAE): 2.13
  - Mean Squared Error (MSE): 14.33
  - Root Mean Squared Error (RMSE): 3.79

- **Coefficients**:
  - `mean_distance` has the highest weight, indicating that for every 1 mile traveled, the fare increases by an average of $2.00.

### Visualizations

- **Scatter Plot**: Visualized actual vs. predicted fare amounts.
- **Histogram**: Distribution of residuals.
- **Correlation Heatmap**: Showed high correlation between `mean_distance` and `fare_amount`.

## Conclusion

The multiple linear regression model developed in this project demonstrates a strong predictive capability for taxi fares based on features such as trip distance, trip duration, passenger count, and rush hour status. The model performance metrics and visualizations indicate that the model is well-fitted and provides accurate predictions.

