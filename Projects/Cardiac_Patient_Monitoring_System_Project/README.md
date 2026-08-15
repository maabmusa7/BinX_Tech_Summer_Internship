# Cardiac Patient Monitoring System - Heart Disease Prediction
### Predicting Heart Disease Risk with Machine Learning

## Table of Contents
- [Overview](#-overview)
- [Dataset](#-dataset)
- [Project Workflow](#-project-workflow)
- [Data Preparation](#-data-preparation)
- [Exploratory Data Analysis](#-exploratory-data-analysis)
- [Models & Results](#-models--results)
- [Feature Engineering & Pipeline](#-feature-engineering--pipeline)
- [Key Findings](#-key-findings)
- [Limitations](#-limitations)
- [How to Run](#-how-to-run)
- [Project Structure](#-project-structure)
- [Tech Stack](#-tech-stack)

---

## Overview
This project aims to build a machine learning analysis project on a synthetic **cardiac patient dataset**, covering the full data science lifecycle:

- Data cleaning.
- Exploratory data analysis with statistical and visual insight.
- Two supervised classification models.
- Evaluation using cross-validation and classification metrics.
- Feature engineering wrapped in a reusable Scikit-learn `Pipeline`.

 The goal: identifying which factors; demographic, clinical or lifestyle, are most associated with heart disease and building a reliable model that helps predicting those factors.

---

## Dataset
| Topic | Description |
| --- | --- |
| **Source** | [Kaggle - Heart Disease Dataset](https://www.kaggle.com/code/moridata/heart-disease-dataset/input) |
| **Type** | Synthetic patient health records |
| **Rows** | 50,000 patients |
| **Predictors** | 20 engineered features |
| **Target** | `Heart Disease` - binary (0 = No Disease, 1 = Disease) |
| **Class Balance** | 53.7% No Disease / 46.3% Disease (well balanced) |

**Feature categories:**
| Category | Columns |
| --- | --- |
| Demographic | Age, Gender |
| Anthropometric | BMI *(weight, Height dropped)* |
| Lifestyle | Smoking, Alcohol_Intake, Physical_Activity, Diet, Stress_Level |
| Diagnosed Conditions | Diabetes, Hyperlipidemia, Family_History, Previous_Heart_Attack |
| Clinical Measurements | Systolic_BP, Diastolic_BP, Heart_Rate, Blood_Sugar_Fasting, Cholestrol_Total, Pulse_Pressure |

---

## Project Workfolw

```
Data Loading → Cleaning → EDA, Baseline Model → Model Comparison → Cross-Validation & Evaluation → Feature Engineering → Pipeline
```
 Each stage was completed and reviewed as a discrete milestone before moving to the next, ensuring a disciplined, reproducible process from raw Dara to final model.

 ---

 ## Data Preparation 
 - Checked fro missing values, duplicates and invalid ranges 
 - `Alchohol_Intake` had **40% missing values** - rather than dropping the column or guessing values, missing entries were labeled `"unknkown"` as their own category, preserving the full dataset without introducing bias.
 - Binary columns (e.g. `Hypertension`) were explicitly treated as **categorical**, not continuous, despite their numeric data type.

---


## Exploratory Data Analysis
- Structural checks (shape, types, missing values, duplicates)
- Descriptive statistics, skewness, and IQR Method for outlier detection.
- Univariate visualisations - histograms, KDE plots, box plots, count plots
- Bivariate vizualiztions - box plots and stacked bar charts split by target, correlation heat map, scatter plots coloured by `heart_Disease`.
- No resampling or balancing was needed for the target column(balanced proportions 53.7% / 46.3%).

**Highlights:**
- `[Age, Diabetes, Hypertension, Previous_Heart_Attack, Cholesterol_Total]` showed the clearest separation between disease and non-disease groups.
- `Weight/Height` were found redundant with `BMI`.

*Full EDA visualizations and written interpretation are available in the notebook.*

---

## Models & Results

Two classifiers were trained and evaluated using an 80/20 **stratifies** train/test split and **5-fold cross-validation**:

### Baseline (pre-feature engineering)

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | :---: | :---: | :---: | :---: | :---: |
| Logistic Regression | 0.923 |  |  |  |  |
| Random Forest | 1.0 |  |  |  |  |

### Final (post-feature engineering, via Pipeline)

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | :---: | :---: | :---: | :---: | :---: |
| Logistic Regression | 0.923 |  |  |  |  |
| Random Forest | 1.0 |  |  |  |  |

**Best model**: `Pipeline` - N/A

**Confusion matric interpretation:**
- **False Positives** → healthy patients flagged as at-risk (unnecessary follow-up
- **False Negatives** → at-risk patients missed by the model (higher clinical concern)

*Full confusion matrices and classification reports are in the notebook.*

## Feature Engineering & Pipeline

| Decision | Rationale |
| --- | --- |
| Dropped `Weight`, `Height` | Redundant with `BMI` confirmed via EDA |
| Feature extraction of `Pulse_Pressure` | `Systolic_BP - Diastolic_BP` -A clinical meaningful arterial stiffness indicator |
| Built `ColumnTransformer` + `Pipeline` | Combines scaling, encoding and modelling into a single reusable object |

*This ensures the entire preprocessing + training workflow can be rerun consistently on new data with a single `.fit()` call no manual  steps required.*

---

## Key Findings
- Age, Colestrol_Total, Diabetes, Hypertensionand Previous_Heart_Attaks emerged as the strongest perdictors of `Heart_Disease`, consistent with established cardiac risk factors.
- The dataset's class balance meant no resampling or class-weighting was necessary
- Feature engineering *improved* model performance while simplifying the feature set
- Random Forest outperformed the baseline, making it preferred  choice for this use case.

---

## Limitations
- Dataset is **synthetic** - real-world clinical data is typically noisier, so performance may not directly generalise.
- `Alcohol_Intake` had substantial missing data, imputed as "unknown" rather than a statistically derived value.
- No hyperparameter tuning was performed beyond default model settings.
- Deep learning, clinical diagnoses and unsupervised analysis were beyond the project's scope.

---

## How to Run

```
```

---

## Project Structure


---

## Tech Stack

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Jupyter Notebook

---

<p align="center">
  <I>Built as part of an individual AI & Machine Learning capstone project.</i>
</p>



