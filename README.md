# Dragon Project: Predicting Dragon Flame Heat Output (FHO)

Regression analysis project for **COMS4048A/COMS7063A – Data Analysis and Exploration / Statistical Foundations of Data Science**

## Overview

This project investigates which physical and biological characteristics of dragons best predict **Flame Heat Output (FHO)**, using a dataset of 500 dragons with attributes including age, mass, wingspan, sustained flight speed, hide thickness, and species. The goal was to build interpretable linear regression models with strong generalisation, informed by rigorous exploratory analysis, diagnostic testing, and feature engineering.

## Objectives

- Explore and clean a real-world-style dataset (data quality issues, invalid values, categorical inconsistencies).
- Fit and compare single-variable regression models for each predictor.
- Build and evaluate multiple multi-variable regression models of varying complexity.
- Interpret model coefficients (raw and standardised) to understand feature importance.
- Run residual diagnostics to validate linear regression assumptions.
- Apply feature engineering (log transforms, polynomials, interactions, ratios, domain-specific features) to improve performance.

## Dataset

500 observations, 7 variables: `SPC` (species), `AGE`, `MASS`, `WSP` (wingspan), `HID` (hide thickness), `SPD` (sustained flight speed), and target `FHO`. Data quality issues identified during exploration included an invalid species label (`Wyvernn`) and biologically impossible negative ages, both addressed during preprocessing.

## Methodology

1. **Exploratory Data Analysis** – distribution checks, missing value/duplicate checks, categorical error detection.
2. **Single-Variable Regression** – simple linear models fitted per predictor and ranked by test R².
3. **Multiple-Variable Regression** – five model configurations (all numeric, top-3, physical-only, all + species, selected + species) compared on R², adjusted R², RMSE, MAE, and overfitting gap.
4. **Interpretability** – raw and standardised coefficients to identify the most influential predictors.
5. **Model Evaluation** – residual plots, Q-Q plots, Breusch-Pagan (homoscedasticity), Shapiro-Wilk (normality), and Durbin-Watson (autocorrelation) tests.
6. **Feature Engineering** – log transforms, polynomial terms, interaction terms, ratio features, and a domain-specific "flame power index."

## Key Results

| Metric | Value |
|---|---|
| Best baseline model | Model 1 (All Numeric) |
| Baseline Test R² | 0.5444 |
| Best engineered model | Domain-specific features |
| Final Test R² | 0.5639 |
| Final RMSE | 234.24°C |

- **Wingspan (WSP)** was the strongest single and multi-variable predictor of FHO.
- **Age** and **sustained flight speed** contributed moderate additional explanatory power.
- **Species** provided little incremental predictive value once physical traits were accounted for.
- Diagnostic tests confirmed the regression assumptions of normality, homoscedasticity, and independence of residuals were satisfied, with no meaningful overfitting.
- Domain-specific engineered features (e.g. a flame power index combining age, mass, and wingspan) produced the largest performance gains.

## Tools & Libraries

Python (Google Colab) · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn · SciPy · Statsmodels

## Plots

Save each figure as an image (e.g. PNG) in an `images/` folder in the repo, then update the paths below to match your filenames.

| Figure | Description | Suggested filename |
|---|---|---|
| Fig. 1 | Scatter plots of each single predictor (WSP, MASS, AGE, SPD, HID) vs. FHO, with fitted regression line and R²/RMSE. | <img width="5364" height="3562" alt="single_variable_regression" src="https://github.com/user-attachments/assets/71528050-d642-4fbb-a020-3569a1689479" /> |
| Fig. 2 | Bar chart of mean FHO by species (Dragon, Hydra, Wyvern) with error bars. |<img width="2964" height="1764" alt="species_comparison" src="https://github.com/user-attachments/assets/24bab80e-4b87-4b75-999a-a73877a2f8df" /> |
| Fig. 3 | Comparison of the five multiple regression models: Test R² (left) and overfitting gap (right). |<img width="4464" height="1464" alt="multiple_regression_comparison" src="https://github.com/user-attachments/assets/3f45017e-906b-4da3-a7ee-ab1ff51c281c" />|
| Fig. 4 | Standardised regression coefficients for Model 1 (All Numeric), showing relative predictor importance. | <img width="4470" height="1764" alt="coefficient_interpretation" src="https://github.com/user-attachments/assets/be60ce75-5d52-469e-800c-5f36c947edfd" />|
| Fig. 5 | Residual diagnostic plots for the recommended model: residuals vs. fitted, Q-Q plot, scale-location, actual vs. predicted, and residuals vs. individual predictors. | <img width="3985" height="3083" alt="comprehensive_diagnostics" src="https://github.com/user-attachments/assets/068411ea-7c19-411d-9a02-0d023063279e" />|
| Fig. 6 (feature engineering) | Performance comparison of feature-engineered models vs. baseline, plus MASS×WSP interaction and log-transform effect plots. | <img width="4469" height="3550" alt="feature_engineering_analysis" src="https://github.com/user-attachments/assets/8c461f99-8942-4c22-a6e6-e50ed6b32912" /> |
| Project Summary | Model Performance and Key results| <img width="4405" height="2572" alt="project_summary" src="https://github.com/user-attachments/assets/b197fb18-7bad-4941-94bc-8008a145f52a" />|

## Repository Contents

- `Dragon_Report.pdf` – Full written report with methodology, figures, and results.
- `images/` – Plot images referenced above.
- `dragon_report.ipynb`

## Authors

Patel Mohamed Suhail · Ntimbane Permission · Nemangwela Unarine · Shabane Wamashudu · Namogane Mechem Matsepe

Supervised coursework — University of the Witwatersrand, School of Computer Science and Applied Mathematics.
