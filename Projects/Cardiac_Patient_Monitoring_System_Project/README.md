# Cardiac Patient Monitoring System - Heart Disease Prediction
### Predicting Heart Disease Risk with Machine Learning

## Project Objective
  This project analyses a synthetic heart disease dataset to explore factors associated with cardiac risk and build supervised classification models to. predict heart disease presence. The workflow includes data cleaning, exploratory data analysis, baseline and comparison classifiers, model evaluation and reusable feature engineering pipeline.

## Dataset
- Source: https://www.kaggle.com/code/moridata/heart-disease-dataset/input / Heart Disease Dataset
- Rows: 50,000 patients
- Columns: 20 features + 1 target (`Heart_Disease`)
- Features include: demographic information (Age, Gender), body measurements(Height, Weight, BMI), lifestyle and behavioural factors(Smoking, Physical_Activity,Alchohol_Intake, Diet, Stress_Level), diagnosed medical conditions (Diabetes, Hyperlipidemia, Family_History, Previous_Heart_Attack) and clinical measurements (Systolic_BP, Diastolic_BP, Heart_Rate, Blood_Sugar_Fasting, Cholesterol_Total).

## Data Preperation
- Alcohol_Intake column had 40% of its values missing and were filled with "unknown"
- Binary columns (0/1) (e.g Smoking) were treated as categorical.
 
## Exploratory Data Analysis
- No resampling or balancing was needed for the target column as it had balanced proportions 53.7% / 46.3%
- Age, Diabetes, Hypertension, Previous_Heart_Attack and Cholesterol_Total showed the clearest relationship with heart disease.
- Weight and Height were found redundant with BMI.

## Models

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | --- | --- | --- | --- | --- |
| Logistic Regression | 0.923 |  |  |  |  |
| Random Forest | 1.0 |  |  |  |  |
