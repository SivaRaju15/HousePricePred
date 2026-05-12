# House Price Prediction Using Machine Learning

This project predicts residential house sale prices using machine learning regression models. It uses a housing dataset with property, location, quality, garage, basement, and sale-related features to estimate the target variable `SalePrice`.

## Project Overview

Accurate house price prediction is useful for buyers, sellers, real estate agencies, and investors. This project performs end-to-end data analysis and model building to understand the key factors that affect house prices and to build a reliable prediction model.

## Files

- `HousePricePred.ipynb` - complete Jupyter notebook
- `data.csv` - housing dataset
- `house_price_model.pkl` - saved model generated after running the notebook
- `README.md` - project documentation

## Dataset Summary

- Rows: `1460`
- Columns: `81`
- Target variable: `SalePrice`
- Duplicate rows: `0`
- Missing values are handled during preprocessing

## Workflow

1. Load and inspect the dataset
2. Handle missing values
3. Analyze target variable distribution
4. Detect and remove outliers
5. Encode categorical features
6. Perform correlation analysis
7. Select important features
8. Scale features
9. Train and compare regression models
10. Perform cross-validation
11. Tune Random Forest hyperparameters
12. Analyze actual vs predicted values
13. Compare models
14. Review feature importance and residuals
15. Save the trained model

## Models Used

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- AdaBoost Regressor
- Extra Trees Regressor
- Support Vector Regressor
- K-Nearest Neighbors Regressor
- XGBoost Regressor

## Model Performance

| Model | R2 Score | MAE | RMSE |
|---|---:|---:|---:|
| Extra Trees | 0.8494 | 15633.42 | 21885.54 |
| Gradient Boosting | 0.8455 | 16019.50 | 22167.70 |
| Random Forest | 0.8439 | 15837.15 | 22284.43 |
| K-Nearest Neighbors | 0.8326 | 16627.95 | 23074.66 |
| XGBoost | 0.8304 | 16504.07 | 23224.56 |
| Linear Regression | 0.8225 | 18114.53 | 23758.79 |
| AdaBoost | 0.7896 | 20347.66 | 25872.63 |
| Decision Tree | 0.7060 | 21851.02 | 30580.56 |
| Support Vector Regressor | -0.0031 | 42830.54 | 56486.02 |

## Best Model

The best model based on holdout R2 score is:

```text
Extra Trees Regressor
```

The notebook also tunes and saves a Random Forest model for reuse:

```text
house_price_model.pkl
```

## Key Insights

- `OverallQual` is the most important predictor of house price.
- `GrLivArea` strongly affects price because larger living area generally increases property value.
- Garage features such as `GarageCars` and `GarageArea` are important predictors.
- Basement area and first-floor area contribute strongly to price.
- Ensemble models performed better than simpler linear and single-tree models.

## Important Features

Selected important features include:

- `OverallQual`
- `GrLivArea`
- `GarageCars`
- `GarageArea`
- `FullBath`
- `YearBuilt`
- `TotalBsmtSF`
- `YearRemodAdd`
- `1stFlrSF`
- `GarageYrBlt`
- `TotRmsAbvGrd`
- `Fireplaces`
- `Foundation`
- `MasVnrArea`
- `OpenPorchSF`

## Challenges Faced

- Handling missing values across numerical and categorical columns
- Encoding categorical variables
- Managing many housing features
- Detecting and removing outliers
- Selecting the most relevant features
- Comparing multiple regression algorithms
- Reducing overfitting with cross-validation and hyperparameter tuning

## How to Run

1. Clone or download this repository.
2. Keep `data.csv` and `HousePricePred.ipynb` in the same folder.
3. Install the required libraries.
4. Open the notebook in Jupyter Notebook, JupyterLab, or VS Code.
5. Run all notebook cells from top to bottom.

## Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost joblib
```

## Project Structure

```text
HousePricePred/
├── data.csv
├── HousePricePred.ipynb
├── README.md
└── house_price_model.pkl
```

## Conclusion

This project successfully builds and compares multiple machine learning regression models for house price prediction. Extra Trees achieved the best holdout R2 score, while a tuned Random Forest model was saved for reuse. The analysis shows that property quality, living area, garage features, basement area, and construction-related features are major drivers of house prices.
