# Real Estate Price Prediction

**Exploratory analysis of 506 suburban housing records and a model to predict median home value.**

## Objectives

1. Identify which variables move house prices, and how
2. Find the best-performing model for price prediction

## What I did

- **Exploration:** distributions, a correlation heatmap, scatter matrices and kernel density plots. Room count is the strongest positive driver of price and the share of lower-status population the strongest negative one. Homes bordering the river carry a visible premium.
- **Feature engineering:** added a tax-per-room variable, which correlates more strongly with price than either input alone
- **Preparation:** stratified train-test split (80:20) on the river variable so both sets keep the same mix, median imputation for missing values, standardisation in a scikit-learn pipeline
- **Modelling:** compared three models with 10-fold cross-validation

## Results

| Model | Mean RMSE | Std dev |
|---|---|---|
| Linear regression | 4.22 | 0.75 |
| Decision tree | 4.19 | 0.85 |
| **Random forest** | **3.37** | **0.76** |

Random forest was selected and saved as `Blue Sky.joblib`. RMSE is in thousands of US dollars.

## Repository

| File | Contents |
|---|---|
| `Blue Sky Real Estates.ipynb` | Full analysis and modelling |
| `data.csv` | Dataset (Boston Housing, StatLib) |
| `data.html` | Automated profiling report |
| `Blue Sky.joblib` | Trained model |

## Stack

Python, pandas, scikit-learn, matplotlib, seaborn
