# TikTok Project Regression Analysis: Simplify Complex Data Relationships

### Project Overview

You are a data professional at TikTok. The data team is working towards building a machine learning model that can be used to determine whether a video contains a claim or offers an opinion. With a successful prediction model, TikTok can reduce the backlog of user reports and prioritize them more efficiently.

### Project Objective

The objective of this project is to conduct a logistic regression using verified status as the outcome variable. The results will help understand how video characteristics relate to verified users, which may inform the final model related to predicting whether a video is a claim or an opinion.

### Dataset

This project uses a dataset called `tiktok_dataset.csv`. The dataset contains 19,382 rows, with each row representing one unique video and 12 columns.

#### Data Dictionary

| Column Name                | Type   | Description                                                                 |
|----------------------------|--------|-----------------------------------------------------------------------------|
| `claim_status`             | obj    | Indicates whether the video is a "claim" or "opinion"                       |
| `video_id`                 | int    | Unique identifier for each video                                            |
| `video_duration_sec`       | int    | Duration of the video in seconds                                            |
| `video_transcription_text` | obj    | Transcription text of the video                                             |
| `verified_status`          | obj    | Indicates whether the user is "verified" or "not verified"                  |
| `author_ban_status`        | obj    | Indicates the ban status of the author ("active", "under review", "banned") |
| `video_view_count`         | float  | Number of views the video received                                          |
| `video_like_count`         | float  | Number of likes the video received                                          |
| `video_share_count`        | float  | Number of shares the video received                                         |
| `video_download_count`     | float  | Number of times the video was downloaded                                    |
| `video_comment_count`      | float  | Number of comments the video received                                       |

### Project Tasks

#### PACE: Plan

1. **Imports and Data Loading**
   - Import necessary libraries and load the dataset.

#### PACE: Analyze

2. **Explore Data with EDA**
   - Analyze the data, check for missing values, duplicates, and outliers.
   - Handle class imbalance through resampling if needed.
   - Visualize distributions and relationships among variables.

3. **Examine Correlations**
   - Create a correlation matrix and heatmap to determine the most correlated variables.

#### PACE: Construct

4. **Select Variables**
   - Define the outcome variable `y` and feature set `X`.
   - Split the data into training and testing sets.
   - Encode categorical variables using one-hot encoding.

5. **Model Building**
   - Construct and fit a logistic regression model to the training data.

#### PACE: Execute

6. **Results and Evaluation**
   - Encode categorical features in the testing set.
   - Make predictions using the logistic regression model.
   - Evaluate model performance using confusion matrix and classification report.
   - Interpret model coefficients.

7. **Conclusion**
   - Summarize key findings and provide business recommendations based on the model.

### Key Insights and Recommendations

**Key Insights:**
- The dataset has some strongly correlated variables, which might lead to multicollinearity issues. To address this, we dropped `video_like_count` from the model.
- The logistic regression model indicated that longer videos tend to be associated with higher odds of the user being verified.
- The model had acceptable predictive power with a precision of 61% and a recall of 84%. The overall accuracy was 65%.

### Conclusion

The logistic regression model for predicting verified status based on video features has shown that certain characteristics, such as video length, are associated with verified users. The model has acceptable predictive power, with precision and recall values indicating its usefulness for further analysis. Future work could include exploring additional features and more granular data to improve the model's performance.
