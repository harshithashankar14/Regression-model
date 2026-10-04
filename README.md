Concrete Compressive Strength Prediction using Regression Models and XAI

Predicting concrete compressive strength (CCS) from its mix composition and age with seven regression models, then explaining the predictions with SHAP and LIME.

## Overview
Concrete strength is normally confirmed by lab compression tests, which are slow and resource-intensive. This project builds machine learning models that estimate strength from the mix ingredients, and uses explainable AI (XAI) to show which ingredients matter most. It was done as a team research project at Global Academy of Technology, Bangalore, and presented as a poster.

## Dataset
Kaggle "Concrete Compressive Strength" dataset: 1,030 samples, 9 attributes (8 inputs plus the target).

| Type | Attributes |
|---|---|
| Inputs | Cement, blast furnace slag, fly ash, water, superplasticizer, coarse aggregate, fine aggregate (kg/m³), age |
| Target | Concrete compressive strength |

All attributes are numeric. The data is in `concrete1.csv`.

## Approach
1. Exploratory data analysis and box plots (no outliers found)
2. Mean imputation for missing values in slag and coarse aggregate
3. Min-Max scaling of the features
4. Train/test split: [state your split, e.g. 80/20]
5. Trained seven regression models: Linear, Ridge, Lasso, Elastic Net, Polynomial, Decision Tree and Random Forest
6. Evaluated with MSE, RMSE and MAE
7. Explained the models with SHAP and LIME

## Results
| Model | MSE | RMSE | MAE |
|---|---|---|---|
| Linear Regression | 120.18 | 10.96 | 8.71 |
| Ridge Regression | 120.04 | 10.95 | 8.72 |
| Lasso Regression | 118.56 | 10.88 | 8.67 |
| Elastic Net | 247.59 | 15.73 | 12.34 |
| **Polynomial Regression** | **78.31** | **8.84** | **7.05** |
| Decision Tree | 287.66 | 16.96 | 13.46 |
| Random Forest | 274.38 | 16.56 | 13.34 |

**Polynomial Regression performed best** on all three error metrics, because it captures the non-linear relationship between mix ingredients and strength.

## Explainability (SHAP and LIME)
- Cement and fine aggregate have a significant influence on compressive strength
- Age has the highest impact on the model's predictions

## Why it matters
Knowing which ingredients drive strength lets engineers adjust concrete mixes while keeping cost and sustainability in mind, for example when replacing cement with fly ash or recycled materials.

## Files
| File | Description |
|---|---|
| `VAP.ipynb` | Data preparation, models and XAI |
| `concrete1.csv` | Dataset |
| `ML.xlsx` | [what this contains, or remove this row] |
| `final_poster_ML.pdf` | Research poster |

## Tools
Python, pandas, scikit-learn, SHAP, LIME, matplotlib

## Team
Pratham Ramachandra Bharati, Harshitha Shankar, Trupthi Rao and Ashwini Kodipalli, Global Academy of Technology, Bangalore.

## Author
Harshitha Shankar | MSc Business Analytics, UCD Smurfit School of Business
[LinkedIn](https://linkedin.com/in/harshithashankar14)
