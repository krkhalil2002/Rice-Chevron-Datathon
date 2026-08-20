# Rice Datathon 2025 - Chevron Vehicle Population Prediction

## Project Overview

This project was developed for the Rice Datathon 2025 Chevron Track, a 36-hour data science competition hosted at Rice University in Houston, Texas.

The objective of the project was to use vehicle registration data and machine learning techniques to predict Vehicle Population.

The project focused on data cleaning, exploratory data analysis, feature preprocessing, categorical encoding, machine learning, model evaluation, and generating predictions.

The primary machine learning model used was a Random Forest Regressor.

## Competition

Rice Datathon 2025 was a 36-hour data science competition focused on applying data science and machine learning to real-world challenges.

Project information:

https://rice-datathon-2025.devpost.com/

This project was completed as part of the Chevron Track.

## Objective

The main objective was to determine whether vehicle registration characteristics could be used to predict Vehicle Population.

The project followed the following workflow:

```text
Data Collection
      |
Data Cleaning
      |
Exploratory Data Analysis
      |
Feature Preparation
      |
Categorical Encoding
      |
Random Forest Regression
      |
Model Evaluation
      |
Vehicle Population Predictions
```

## Dataset

The project used two datasets:

### training.csv

The training dataset was used to develop and train the machine learning model.

The target variable was:

`Vehicle Population`

### scoring.csv

The scoring dataset was processed using the same general preprocessing workflow and was used to generate vehicle population predictions.

## Data Cleaning

Several preprocessing steps were performed to prepare the data for analysis and modeling.

### Number of Vehicles Registered at the Same Address

The `Number of Vehicles Registered at the Same Address` column contained inequality symbols such as `<`, `>`, and `=`.

These symbols were removed and the column was converted to numeric values.

Missing values in this column were replaced with a value of 4.

### Model Year

Missing values in the `Model Year` column were replaced using the median model year.

This was done for both the training and scoring datasets.

### Region

The `Region` column was removed from both datasets during preprocessing.

### Unknown Values

The following columns contained `Unknown` values:

* GVWR Class
* Electric Mile Range
* Fuel Type

The `Unknown` values were replaced with the most common non-unknown value for each respective column.

These preprocessing steps were performed to make the data more consistent and usable for machine learning.

## Exploratory Data Analysis

Exploratory data analysis was performed to better understand the dataset and examine relationships between the available features and Vehicle Population.

Scatter plots were created to examine the relationship between individual features and the target variable.

The project also examined the number of unique values within each column and reviewed the unique values for several important variables.

Variables examined included:

* Date
* Model Year
* Fuel Technology
* Fuel Type
* GVWR Class
* Vehicle Category
* Electric Mile Range

This analysis helped identify the structure and characteristics of the dataset before applying the machine learning model.

## Feature Preparation

The dataset was separated into numerical and categorical variables.

The target variable, `Vehicle Population`, was removed from the numerical feature set before model training.

Categorical variables were then prepared for machine learning using One-Hot Encoding.

The encoded categorical features were combined with the numerical features to create the final feature matrix used by the model.

## Machine Learning Model

### Random Forest Regression

A Random Forest Regressor was used to predict Vehicle Population.

The model was trained using the cleaned numerical features and one-hot encoded categorical features.

Random Forest was selected as the regression model for the project because it can identify complex relationships between multiple input features and a continuous target variable.

The model was trained using:

```python
rf_model = RandomForestRegressor()
rf_model.fit(X, y)
```

The target variable was:

`Vehicle Population`

## Model Evaluation

The model was evaluated using two regression metrics:

### Root Mean Squared Error

Root Mean Squared Error (RMSE) was used to measure the magnitude of prediction errors.

A lower RMSE represents smaller prediction errors.

### R-squared

R-squared (R2) was used to measure how much of the variation in Vehicle Population was explained by the model.

The project calculated both metrics using the model's predictions.

```python
mse_rf = mean_squared_error(y, y_pred_rf)
r2_rf = r2_score(y, y_pred_rf)

print(f"Random Forest - Root Mean Squared Error: {np.sqrt(mse_rf)}")
print(f"Random Forest - R2 Score: {r2_rf}")
```

The exact RMSE and R2 values are not included in the uploaded source file because the file contains the code used to calculate the metrics but not the resulting console output.

## Key Findings

### 1. Vehicle Population can be predicted using multiple vehicle characteristics

The project used a combination of numerical and categorical vehicle information to predict Vehicle Population.

This required combining different types of variables into a single feature set before training the model.

### 2. Data quality had a significant impact on the modeling process

The dataset contained missing values, unknown categorical values, and non-numeric symbols.

These inconsistencies had to be addressed before the data could be effectively used by the machine learning model.

### 3. Categorical variables required preprocessing

Vehicle-related categorical variables could not be directly used by the Random Forest model in their original format.

One-Hot Encoding was used to transform categorical variables into numerical features.

### 4. Random Forest was used to capture relationships within the data

The Random Forest Regression model provided a way to model relationships between vehicle characteristics and Vehicle Population without relying on a strictly linear relationship.

### 5. The model generated predictions for the scoring dataset

After training, the Random Forest model was used to generate Vehicle Population predictions for the scoring dataset.

The predictions were stored in a DataFrame and exported as `y_pred_rf.csv`.

## Skills Demonstrated

This project demonstrates experience with:

* Python
* Pandas
* NumPy
* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Data Visualization
* One-Hot Encoding
* Machine Learning
* Random Forest Regression
* Regression Model Evaluation
* RMSE
* R-squared
* CSV Data Processing
* Google Colab

## Technologies Used

| Technology   | Purpose                                   |
| ------------ | ----------------------------------------- |
| Python       | Data analysis and machine learning        |
| Pandas       | Data manipulation and preprocessing       |
| NumPy        | Numerical operations                      |
| Matplotlib   | Data visualization                        |
| Seaborn      | Exploratory data visualization            |
| Scikit-learn | Machine learning and model evaluation     |
| Google Colab | Development environment                   |
| GitHub       | Project documentation and version control |

## Project Workflow

The complete project workflow was:

1. Load the training and scoring datasets.
2. Clean the vehicle registration data.
3. Handle missing values.
4. Replace unknown categorical values.
5. Remove the Region feature.
6. Explore relationships between features and Vehicle Population.
7. Separate numerical and categorical features.
8. Apply One-Hot Encoding to categorical variables.
9. Combine numerical and encoded categorical features.
10. Train the Random Forest Regression model.
11. Generate predictions.
12. Evaluate model performance using RMSE and R2.
13. Generate predictions for the scoring dataset.
14. Export the predictions to a CSV file.

## Output

The final model predictions were exported to:

```text
y_pred_rf.csv
```

The output contains a column named:

```text
predicted_vehicle_population
```

This file contains the predicted Vehicle Population values generated by the Random Forest model.

## Future Improvements

Potential improvements to the project could include:

* Using a dedicated train/test split before evaluating the model.
* Applying cross-validation to obtain a more reliable estimate of model performance.
* Tuning Random Forest hyperparameters.
* Comparing Random Forest with other regression algorithms.
* Examining feature importance to determine which variables contribute most to Vehicle Population predictions.
* Creating additional visualizations to communicate the results.
* Developing an interactive dashboard to present vehicle population trends.

## Project Structure

```text
Rice-Datathon-Chevron/
|
|-- README.md
|-- Rice Datathon Cheveron.ipynb
|-- training.csv
|-- scoring.csv
|-- y_pred_rf.csv
```

## Conclusion

This project demonstrates an end-to-end machine learning workflow for predicting Vehicle Population from vehicle registration data.

The analysis required cleaning real-world data, handling missing and unknown values, preparing numerical and categorical features, performing exploratory analysis, applying One-Hot Encoding, training a Random Forest Regression model, evaluating the model, and generating predictions.

The project provided practical experience applying Python and machine learning techniques to a real-world data science problem during the Rice Datathon 2025 Chevron Track.
