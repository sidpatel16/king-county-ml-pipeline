# Predicting House Prices in King County

## Project Overview
This project applies an end-to-end machine learning workflow to predict real estate prices in King County, Washington. Using a dataset of houses sold between May 2014 and May 2015, the goal is to accurately forecast the `price` target variable using a variety of housing features.

## Dataset
* **Source File:** `kc_house_data-2.csv`
* **Description:** The dataset contains 19,606 observations and 19 variables representing house sales. 
* **Target Variable:** `price` (Continuous)

## Methodology
The analytical pipeline was built using Python and `scikit-learn`. The workflow includes:
1. **Data Split:** 70% training and 30% testing split.
2. **Preprocessing Pipeline:** Built using `ColumnTransformer` and `Pipeline`.
    * *Numeric Features:* Imputed missing values with the median and standardized using `StandardScaler`.
    * *Categorical Features:* Imputed missing values with a constant ('unknown') and applied `OneHotEncoder`.
    * *Binary Features:* Imputed missing values using the most frequent value.
3. **Modeling:** Trained and evaluated three regression algorithms against a baseline model.

## Models Evaluated
* **Baseline:** Predicts the mean of the target variable for every observation.
* **Linear Regression:** Fits a linear relationship between the input features and the house price.
* **Decision Tree Regressor:** A non-linear model capturing complex decision rules.
* **Random Forest Regressor:** An ensemble learning method utilizing 100 decision trees.

## Results & Evaluation
Model performance was evaluated using Root Mean Squared Error (RMSE). 

| Model | Train RMSE | Test RMSE |
| :--- | :--- | :--- |
| **Baseline (Mean)** | N/A | 181,941.87 |
| **Linear Regression** | 76,626.57 | 77,158.35 |
| **Decision Tree** | 9,047.80 | 98,069.50 |
| **Random Forest** | 27,312.15 | **70,055.38** |

**Key Findings:**
* The **Random Forest Regressor** performed the best, achieving the lowest Test RMSE of roughly 70,055.
* The **Decision Tree** severely overfit the training data (Train RMSE of ~9,047 vs. Test RMSE of ~98,069).
* Both the Linear Regression and Random Forest models significantly outperformed the baseline.

## How to Run This Project
1. Clone this repository to your local machine.
2. Ensure `kc_house_data-2.csv` and `Assignment - KC House Prices-1 - Github.ipynb` are in the same directory.
3. Run the Jupyter Notebook sequentially to reproduce the preprocessing steps and model evaluations.
