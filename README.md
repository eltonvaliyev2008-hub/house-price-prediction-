# House Price Prediction

## Overview

In this project, I used the Kaggle House Prices dataset to predict residential property sale prices.

The project is organized into six Jupyter notebooks, covering data cleaning, data preprocessing, feature engineering, exploratory data analysis (EDA), linear regression, and advanced machine learning models.

## What I Did

**1. Data Cleaning**

- Checked for duplicate records.
- Identified and handled missing values.
- Analyzed and investigated outliers.
- Reviewed data types and data consistency.

**2. Data Preprocessing**

- Encoded categorical features using ordinal encoding and one-hot encoding.
- Analyzed feature skewness.
- Applied feature scaling where necessary.

**3. Feature Engineering**

- Created 15 new features to capture additional relationships between variables.
- Examples include `TotalSF`, `TotalBath`, `HouseAge`, and `Quality_x_Area`.
- The complete list of engineered features is available in `new_features_list.txt`.

**4. Exploratory Data Analysis (EDA)**

- Analyzed the target variable distribution.
- Investigated relationships between features.
- Explored feature correlations and their relationships with sale prices.

**5. Linear Regression**

- Built a baseline Linear Regression model.
- Analyzed residuals and regression assumptions.
- Experimented with polynomial features.
- Investigated multicollinearity using VIF (Variance Inflation Factor).
- Examined the impact of outliers on model performance.

**6. Advanced Modelling**

- Trained and compared Ridge, Lasso, ElasticNet, Random Forest, XGBoost, and LightGBM models using cross-validation.
- Optimized selected model hyperparameters using GridSearchCV.
- Compared tuned models against their default configurations.
- Experimented with ensemble learning techniques, including blending and stacking.

## Model Evaluation Results

Models were evaluated using 5-fold cross-validation on the 80% training split.

RMSE was calculated on the logarithmic target scale. Lower RMSE values indicate better performance.

| Model | CV RMSE |
|---|---:|
| XGBoost (Tuned) | 0.1117 |
| Lasso | 0.1127 |
| ElasticNet | 0.1128 |
| LightGBM (Tuned) | 0.1130 |
| Ridge | 0.1159 |
| XGBoost (Default) | 0.1183 |
| LightGBM (Default) | 0.1212 |
| Linear Regression | 0.1216 |
| Random Forest | 0.1242 |
| **Blending (ElasticNet + Lasso + XGBoost + LightGBM)** | **0.1088** |

<p align="center">
  <img src="images/model_comparison.png" alt="Model Comparison" width="800">
</p>

### Hyperparameter Optimization

Hyperparameters were optimized using GridSearchCV. The tuned models were then compared against their default configurations to evaluate the impact of hyperparameter optimization on model performance.

### Ensemble Learning

A blending approach combining ElasticNet, Lasso, XGBoost, and LightGBM achieved the best cross-validation result, with an RMSE of **0.1088**.

Stacking was also explored as an additional ensemble learning technique.

## Kaggle Competition Result

**Kaggle Score: 0.12902**

## Installation and Usage

### 1. Download the Dataset

Download `train.csv` and `test.csv` from the [Kaggle House Prices Competition](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data).

The dataset is not included in this repository. Place both CSV files in the directory expected by the notebooks.

### 2. Install Dependencies

```bash
pip install pandas numpy scipy matplotlib seaborn scikit-learn xgboost lightgbm jupyter
```

### 3. Run the Notebooks

```bash
jupyter notebook
```

Run the notebooks in the following order.

## Project Structure

| Notebook | Description |
|---|---|
| `1-Data-Cleaning` | Duplicate detection, missing values, data types, and outlier analysis |
| `2-Data-Preprocessing` | Categorical encoding, skewness analysis, and feature scaling |
| `3-Feature-Engineering` | New feature creation and feature selection |
| `4-Exploratory-Data-Analysis` | Target distributions, feature relationships, and correlation analysis |
| `5-Linear-Regression` | Baseline model, residual analysis, VIF, polynomial features, and outlier impact |
| `6-Advanced-Modelling` | Ridge, Lasso, ElasticNet, tree-based models, hyperparameter tuning, blending, and stacking |

## Additional Files

- `new_features_list.txt` - Complete list of the 15 engineered features.

## Author

**Elton Vəliyev**

[LinkedIn](https://www.linkedin.com/in/eltonvaliyev/)
