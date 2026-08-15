# Cardiac Patient Monitoring System - Heart Disease Prediction
### Predicting Heart Disease Risk with Machine Learning

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Data Preparation](#data-preparation)
- [Exploratory Data Analysis](#eda)
- [Models & Results](#models-results)
- [Feature Engineering & Pipeline](#feature-engineering)
- [Key Findings](#key-findings)
- [Limitations](#limitations)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)

---

<a name="overview"></a>
## Overview

This project aims to build a machine learning analysis project on a synthetic **cardiac patient dataset**, covering the full data science lifecycle:

- Data cleaning.
- Exploratory data analysis with statistical and visual insight.
- Two supervised classification models.
- Evaluation using cross-validation and classification metrics.
- Feature engineering wrapped in a reusable Scikit-learn `Pipeline`.

The goal: identifying which factors; demographic, clinical or lifestyle, are most associated with heart disease and building a reliable model that helps predicting those factors.

---


<a name="dataset"</a>
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
| Clinical Measurements | Systolic_BP, Diastolic_BP, Heart_Rate, Blood_Sugar_Fasting, Cholestrol_Total, Pulse_Pressure (engineering) |

---


<a name="project-workflow"</a>
## Project Workfolw

```
Data Loading → Cleaning → EDA, Baseline Model → Model Comparison → Cross-Validation & Evaluation → Feature Engineering → Pipeline
```

 Each stage was completed and reviewed as a discrete milestone before moving to the next, ensuring a disciplined, reproducible process from raw Dara to final model.

 ---


<a name="data-preparation"</a>
 ## Data Preparation 
 - Checked for missing values, duplicates and invalid ranges 
 - `Alchohol_Intake` had **40% missing values** - rather than dropping the column or guessing values, missing entries were labeled `"unknkown"` as their own category, preserving the full dataset without introducing bias.
 - Binary columns (e.g. `Hypertension`) were explicitly treated as **categorical**, not continuous, despite their numeric data type.

---


<a name="eda"</a>

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


<a name="models-results"</a>
## Models & Results

Two classifiers were trained and evaluated using an 80/20 **stratifies** train/test split and **5-fold cross-validation**:

### Baseline (pre-feature engineering)

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | :---: | :---: | :---: | :---: | :---: |
| Logistic Regression | 0.9237 | 0.9178 | 0.9176 | 0.1977 | 0.9822 |
| Random Forest | 1.0 | 1.0 | 1.0 | 1.0 | 1.0 |

### Final (post-feature engineering, via Pipeline)

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | :---: | :---: | :---: | :---: | :---: |
| Logistic Regression | 0.923 | 0.9178 | 0.9176 | 0.1977 | 0.9822 |
| Random Forest | 1.0 | 1.0 | 1.0 | 1.0 | 1.0 |


**Best model**: `Logistic Regression` - 92% accuracy is not attributable to reverse-engineering the data's generation rule, making it the more trustworthy and generalisable result. See [Key Findings](#-key-findings) for the full reasoning.

**Confusion matric interpretation:**
- **False Positives** → healthy patients flagged as at-risk (unnecessary follow-up
- **False Negatives** → at-risk patients missed by the model (higher clinical concern)

*Full confusion matrices and classification reports are in the notebook.*

---


<a name="feature-engineering"</a>
## Feature Engineering & Pipeline

| Decision | Rationale |
| --- | --- |
| Dropped `Weight`, `Height` | Redundant with `BMI` confirmed via EDA |
| Feature extraction of `Pulse_Pressure` | `Systolic_BP - Diastolic_BP` -A clinical meaningful arterial stiffness indicator |
| Built `ColumnTransformer` + `Pipeline` | Combines scaling, encoding and modelling into a single reusable object |

*This ensures the entire preprocessing + training workflow can be rerun consistently on new data with a single `.fit()` call no manual  steps required.*

---


<a name="key-findings"</a>
## Key Findings
- Age, Colestrol_Total, Diabetes, Hypertensionand Previous_Heart_Attaks emerged as the strongest perdictors of `Heart_Disease`, consistent with established cardiac risk factors.
- The dataset's class balance meant no resampling or class-weighting was necessary
- Feature engineering *improved* model performance while simplifying the feature set
- Random Forest's perfect test score is an artifact of the synthetic dataset's likely rule-based generation, not genuine superiority

---

<a name="final-summary"</a>
## Final Results Summary
- **Recommended model:** Logistic Regression, despite Random Forest's higher raw scores (reasoning above).
- **Top predictive features:** `Age`, `Cholesterol_Total`, `Hypertension`, `Diabetes`,`Previous_Heart_Attack`.
- **Key limitations flag in any real-world application:** this dataset is synthetic, and a perfect classifier is not a realistic outcome to expect on genuine patient data - any deployment on real clinical data would need revalidation, likely with nosier, less separable results.
- **Process discipline:** every stage was completed and reviewed as a distinct milestone before proceeding to the next, with findings documented at each step.


---

<a name="limitations"</a>
## Limitations
- Dataset is **synthetic** - real-world clinical data is typically noisier, so performance may not directly generalise.
- `Alcohol_Intake` had substantial missing data, imputed as "unknown" rather than a statistically derived value.
- No hyperparameter tuning was performed beyond default model settings.
- Deep learning, clinical diagnoses and unsupervised analysis were beyond the project's scope.
- **Random Forest achieved a perfect 100% test score**, which is very unlikely on genuine clinical data. This points to the synthetic  dataset encoding a near-deterministic rule around a small set of features.

---

<a name="how-to-run"</a>
## How to Run

```bash
# 1. Clone this repository
git clone [your-repo-url]
cd [repo-name]

# 2. Install dependencies
pip instal -r requirements.txt

# 3. Add the dataset
# Place synthetic_heart_disease_dataset.csv into the data/ folder

# 4. Launch and run the notebook top to bottom
Jupyter notebook notebooks/Cardiac_Patient_Monitoring_System.ipynb
```

The notebook runs end to end with no manual/hidden steps required.

---

<a name="project-structure"</a>
## Project Structure

 
    data
        synthetic_heart_disease_dataset.csv
    notebooks
        Cardiac_Patient_Monitoring_System_Project.ipynb
    outputs
        plots, confusion matrices, result summaries
    requirements.txt
    README.md

---

<a name="tech-stack"</a>
## Tech Stack

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Jupyter Notebook

---

<p align="center">
  <I>Built as part of an individual AI & Machine Learning capstone project.</i>
</p>



