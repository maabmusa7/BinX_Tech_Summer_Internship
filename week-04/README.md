<div align="center">

# 📊 Week 04 — EVALUATION, TUNING & PIPELINES

*Week 4 moved from a model that can simply work to a one that can be trusted, validated, refined and reliably reproduced.*

</div>

<div align="left">
   
## 📑 Table of Contents

| Day | Topic |
|---|---|
| Day 01 | Train / Validation / Test Splits |
| Day 02 | Cross-Validation |
| Day 03 | Bias-Variance & Diagnosing Model Fit |
| Day 04 | Feature Engineering & Hyperparameter Tuning |
| Day 05 | Scikit-learn Pipelines & Tuned Mini-Project |


</div>

----

## 📝Overview

   Week 4 transitioned from a simple running model to a reliable trustworthy one. Starting with **Train/Validation/Test split**  snd **Cross Validation** to establish sound evaluation basis, then diagnosing model behaviour through **Bias-Variance** to distinguish **overfitting and unerfitting**. The week expanded into strengthening model performance; to include **Feature Engineering** and **Hyperparameter Tuning** using **GridSearchCV**, refining inputs to get the most out of it. The week concluded with **Scikit-learn Pipelines**, consolidating preprocessing, tuning and modelling a **leakage-free** workflow in a Tuned Mini-project.


## Structure


    Week04
        README.md
        Day01
            Notebook4.1.ipynb
            README.md
        Day02
            Notebook4.2.ipynb
            README.md
        Day03
            Notebook4.3.ipynb
            README.md
        Day04
             Notebook4.4.ipynb
             README.md
        Day05
             Notebook4.5.ipynb
             README.md
        
        


## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Evaluation  | train_test_split, cross_val_score, StratifiedKFold |
| Tuning | GridSearchCV, RandomizedSearchCV |
| Regularization | Ridge(L2), Lasso(L1) |
| Pipelines | Pipeline, ColumnTransformer, StandardScaler, OneHotEncoder |
| Environment | Python 3.10+, Jupyter Notebook, Pandas, Scikit-learn, Git & GitHub |

## 📅  Daily Breakdown

| Day | Date | Topic | Summary |Log |
|---|---|---|---|---|
| 01 | Aug 9 | Train / Validation / Test Splits | Three-Way Split, Tuning one setting | [Day01 →](./Day01/README.md) |
| 02 | Aug 10 | Cross-Validation | Definition, k-Fold, cross_val_score, Stratified k-Fold | [Day02 →](./Day02/README.md) |
| 03 | Aug 11 | Bias-Variance & Diagnosing Model Fit | Bias-Variance Tradeoof, Overfitting VS Underfitting, Diagnosing with Train/Validation Gap, Regularization | [Day03 →](./Day03/README.md) |
| 04 | Aug 12 | Feature Engineering & Hyperparameter Tuning | Feature Engineering VS Model Choice, Feature Engineering Techniques, Hyperparameters VS Parameters, GridSearchCV | [Day04 →](./Day04/README.md) |
| 05 | Aug 13 | Scikit-learn Pipelines & Tuned Mini-Project | Building Pipelines, ColumnTransformer, Tuning Pipelines, Week 4 Mini-Project | [Day05 →](./Day05/README.md) |

## 🎯Key Takeaways
- Explaining the purpose the validation set and why it is needed.
- Producing reliable models with k-fold cross validation.
- Identifying overfitting and underfitting and resolving them.
- Engineering and scaling features to improve model performance.
- Hyperparameter tuning with GridSearchCV, Package processing and modelling into a leakage-free Scikit-learn Pipeline.
