
# Waze Project Regression Analysis: Simplify Complex Data Relationships

## Project Objective

The objective of this project is to build a binomial logistic regression model to predict user churn based on various variables. This involves performing exploratory data analysis (EDA), building the model, evaluating its performance, and interpreting the results.

### Dataset

This project uses a dataset called `waze_dataset.csv`. It contains synthetic data created for this project in partnership with Waze. The dataset consists of 14,999 rows, with each row representing one unique user and 13 columns.

#### Data Dictionary

| Column Name                  | Type   | Description                                                                                   |
|------------------------------|--------|-----------------------------------------------------------------------------------------------|
| `ID`                         | int    | A sequential numbered index                                                                   |
| `label`                      | obj    | Binary target variable (“retained” vs “churned”) indicating if a user has churned during the month |
| `sessions`                   | int    | The number of occurrences of a user opening the app during the month                          |
| `drives`                     | int    | The number of occurrences of driving at least 1 km during the month                           |
| `device`                     | obj    | The type of device a user starts a session with                                               |
| `total_sessions`             | float  | A model estimate of the total number of sessions since a user has onboarded                   |
| `n_days_after_onboarding`    | int    | The number of days since a user signed up for the app                                         |
| `total_navigations_fav1`     | int    | Total navigations since onboarding to the user’s favorite place 1                             |
| `total_navigations_fav2`     | int    | Total navigations since onboarding to the user’s favorite place 2                             |
| `driven_km_drives`           | float  | Total kilometers driven during the month                                                      |
| `duration_minutes_drives`    | float  | Total duration driven in minutes during the month                                             |
| `activity_days`              | int    | Number of days the user opens the app during the month                                        |
| `driving_days`               | int    | Number of days the user drives (at least 1 km) during the month                               |

### Project Tasks

#### PACE: Plan

1. **Imports and Data Loading**
   - Import necessary libraries and datasets.

#### PACE: Analyze

2. **Explore Data with EDA**
   - Analyze data, check for missing values, outliers, and correlations.
   - Create new features that might be relevant for the model.

3. **Create Features**
   - Create new variables such as `km_per_driving_day` and `professional_driver` based on domain knowledge.

#### PACE: Construct

4. **Preparing Variables**
   - Handle missing values and outliers.
   - Encode categorical variables and drop variables with high multicollinearity.

5. **Model Building**
   - Split the data into training and testing sets.
   - Instantiate and train a logistic regression model.

6. **Determine Whether Assumptions Have Been Met**
   - Check for multicollinearity and linear relationships between predictors and log-odds.

#### PACE: Execute

7. **Results and Evaluation**
   - Make predictions on the test data and evaluate the model's accuracy.
   - Use a confusion matrix to calculate precision and recall.
   - Generate a classification report and interpret the results.

8. **Show Results with a Confusion Matrix**
   - Visualize the model's performance using a confusion matrix.

9. **Conclusion**
   - Summarize key findings and provide business recommendations.
   - Discuss the model's strengths and limitations, and suggest potential improvements.

### Conclusion

**Key Insights:**
- The variable `activity_days` was found to be the most influential predictor in the model, showing a negative correlation with user churn. This aligns with initial expectations as users who are more active tend to stay with the service.
- Some variables, such as `km_per_driving_day`, did not perform as strongly as anticipated despite having shown strong correlations during exploratory data analysis.

**Model Performance:**
- The logistic regression model had an accuracy of approximately 82%.
- Precision for the model was moderate, but recall was low, indicating a tendency to miss many actual churn cases.

**Recommendations:**
- The current model may not be suitable for making critical business decisions due to its low recall rate. It could be used for guiding further exploratory analysis.
- To improve the model, consider engineering additional features and possibly scaling the predictor variables.
- Further data, such as more granular user interactions and drive-level details, could enhance the model's predictive power.

**Future Improvements:**
- Explore creating new features that capture additional user behaviors and interactions with the app.
- Conduct further iterations of model building with different combinations of predictor variables to optimize performance.
- Evaluate and potentially implement different modeling techniques or algorithms to improve recall and overall predictive accuracy.

