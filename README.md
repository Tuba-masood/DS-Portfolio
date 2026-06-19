# PIMA Diabetes Prediction

## Problem
Predict whether a patient has diabetes based on 8 health measurements.
Early prediction can support timely medical intervention.

## Data
- PIMA Indians Diabetes dataset (768 patients, 8 features + outcome)
- Source: Kaggle
- Classes are imbalanced: ~65% non-diabetic, ~35% diabetic

## Approach
- Exploratory Data Analysis (distributions, correlations, boxplots)
- Cleaned disguised missing values (impossible zeros in Glucose, BloodPressure, BMI → median imputation)
- Train/test split (80/20, stratified) before any modeling
- Baseline model (majority class) = ~65% accuracy — the bar to beat
- (More models to come)

## Results
*To be filled in as models are trained and evaluated.*

## Tools
Python, pandas, NumPy, scikit-learn, matplotlib, seaborn
