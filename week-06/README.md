<div align="center">

# 📊 Week 06 — DEEP LEARNING INTRO - SPRINT 1

*Week 6 moved from classical ML baselines into neural networks — understanding how a network computes, trains, and improves, then closing the sprint with a fully evaluated, tuned, and documented model.*

</div>
<div align="left">

## 📑 Table of Contents
| Day | Topic |
|---|---|
| Day 01 | Sprint 1 Planning & Neural Network Architecture |
| Day 02 | Activations, Forward Propagation & Loss |
| Day 03 | Backpropagation, Gradient Descent & Optimizers |
| Day 04 | Building & Training a Network in Keras |
| Day 05 | Tuning, Evaluation & Sprint Review |

</div>

----

## 📝 Overview
Week 6 introduced neural networks from first principles before moving into a production-style framework. Starting with **activation functions** (ReLU, Sigmoid, Tanh) and a **hand-computed forward pass**, the week built up to the full **four-step training loop** (forward pass → loss → backpropagation → weight update), grounded with a hands-on **learning rate experiment** and a plain-language explanation of the **chain rule** behind backpropagation. From there, the project moved into **Keras**, building a Sequential network with the correct output activation and loss for binary classification, diagnosing fit from training/validation curves, and comparing **Dropout/Batch Normalization** against an unregularized baseline. The week closed with systematic **one-hyperparameter-at-a-time tuning**, **EarlyStopping**, and a full **Sprint 1 wrap-up** — assembling baseline-vs-neural-network evidence, opening and merging pull requests for mentor review, and writing a Sprint Review and Retrospective with a concrete action item for Sprint 2.

## Structure
    Week06
        README.md
        Day01
            Notebook6.1_project_update.ipynb
            Notebook6.1_hands_on_lab.ipynb    <- feature/baseline-sprint1 branch
            README.md
        Day02
            Notebook6.2.ipynb
            README.md
        Day03
            Notebook6.3.ipynb    <- feature/phase3-training-loop
            README.md
        Day04
             Notebook6.4_hands_on_lab.ipynb
             README.md
        Day05
             Notebook6.5.ipynb    <- feature/phase3-training-loop
             README.md

## 🛠️ Tech Stack
| Tool | Purpose |
|---|---|
| Deep Learning Framework  | TensorFlow / Keras (Sequential, Dense, Dropout, BatchNormalization) |
| Training | Adam / SGD optimizers, callbacks (EarlyStopping, ModelCheckpoint) |
| Baseline & Data  | Scikit-learn, Pandas, NumPy |
| Compute | Google Colab (free GPU/TPU) |
| Environment | Jupyter/Colab, Matplotlib, Git & GitHub (feature branches + pull requests) |


## 📅 Daily Breakdown
| Day | Date | Topic | Summary | Log |
|---|---|---|---|---|
| 01 | Aug 24 | Sprint 1 Planning & Neural Network Architecture | Sprint Planning, Backlog selection, Dataset Dinalization, Baseline Model, Feature Branch & Draft PR | [Day01 →](./Day01/README.md) |
| 02 | Aug 25 | Activations, Forward Propagation & Loss | ReLU, Sigmoid, Tanh, Output Activation, Loss Function, Forward Pass | [Day02 →](./Day02/README.md) |
| 03 | Aug 26 | Backpropagation, Gradient Descent & Optimizers | Training Loop, Learning Rate, Backpropagation, Chain Rule | [Day03 →](./Day03/README.md) |
| 04 | Aug 27 | Building & Training a Network in Keras | Sequential Model, Adam, Validation Split, Dropout, Batch Normalization | [Day04 →](./Day04/README.md) |
| 05 | Aug 28 | Tuning, Evaluation & Sprint Review | Tuning, Evaluation & Sprint Review | Hyperparameter Tuning, EarlyStopping, Sprint Evidence, PR merge, Retrospective | [Day05 →](./Day05/README.md) |

## 🎯 Key Takeaways
- Understanding how ReLU, Sigmoid, and Tanh transform values, and choosing the correct output activation and loss function for a given task.
- Computing a forward pass by hand to internalize how weights, biases, and activations combine layer by layer.
- Explaining the four-step training loop and why the chain rule makes backpropagation possible.
- Diagnosing model fit directly from training vs. validation curves, distinguishing instability from classic overfitting.
- Using Dropout and Batch Normalization deliberately, and confirming their effect empirically rather than assuming it.
- Tuning hyperparameters one at a time to isolate which change actually drives improvement, and using EarlyStopping to avoid picking an arbitrary final epoch.
- Closing a sprint properly: assembling evidence, documenting architecture and results, and running the full PR review → merge → retrospective cycle.


# Sprint 1 Review — Cardiac Risk Prediction Project

## Sprint Goal
Establish a working baseline for predicting heart disease risk from the CDC BRFSS survey dataset, then determine whether increasingly complex models (Random Forest, Neural Network) could meaningfully improve on that baseline.

## What Was Delivered
- **EDA & cleaning**: identified and removed 18,078 duplicate rows (~5.7%), confirmed no missing values, flagged data-quality issues (BMI outlier of 94.85, implausible SleepTime values).
- **Baseline model**: Logistic Regression with `class_weight="balanced"` — **ROC-AUC 0.832**.
- **Comparison model**: Random Forest, both untuned and lightly tuned — **ROC-AUC 0.791**, underperforming the linear baseline.
- **Neural network**: Keras Sequential network (37 → 32 → 16 → 1), tuned via systematic one-hyperparameter-at-a-time comparison (dropout, learning rate, network size), trained with EarlyStopping — **ROC-AUC 0.832–0.836** across variants.
- **Unsupervised exploration**: K-Means, DBSCAN, hierarchical clustering, PCA, t-SNE, and Isolation Forest, used to understand structure in the data independent of the target label.

## Key Result

| Model | ROC-AUC |
|---|---|
| Logistic Regression (baseline) | 0.832 |
| Random Forest | 0.791 |
| Neural Network (best variant) | 0.836 |
| Neural Network (tuned + EarlyStopping) | 0.832 |

Every model — regardless of complexity — converged to essentially the same ~0.83 ROC-AUC ceiling. This is the headline finding of the sprint: **the predictive signal in this dataset is largely linear**, and increasing model complexity did not unlock meaningfully better performance.

## What This Means Going Forward
Future performance gains are more likely to come from **better features** (interaction terms, external data sources, more granular risk scoring) than from more sophisticated model architectures — a concrete, evidence-backed direction for Sprint 2 rather than defaulting to "try a bigger model."

## Sprint 1 Retrospective

**What went well:**
- Systematic, one-variable-at-a-time hyperparameter testing isolated dropout as the single most impactful lever, rather than guessing at combined changes.
- Refactoring manual preprocessing into a Scikit-learn `Pipeline` + `ColumnTransformer` eliminated an entire category of bugs (variable name collisions, out-of-order execution) that had repeatedly caused issues earlier in the sprint.

**What was challenging:**
- Small naming/typo bugs ( e.g## Sprint 1 Retrospective

**What went well:**
- Systematic, one-variable-at-a-time hyperparameter testing isolated dropout as the single most impactful lever, rather than guessing at combined changes.
- Refactoring manual preprocessing into a Scikit-learn `Pipeline` + `ColumnTransformer` eliminated an entire category of bugs (variable name collisions, out-of-order execution) that had repeatedly caused issues earlier in the sprint.

**What was challenging:**
- Small naming/typo bugs (e.g. `keras,optimizers`, `Sex` mapped with the wrong dictionary) caused repeated debugging cycles throughout the sprint — several hours were spent tracing errors back to single-character typos.

**One concrete change for Sprint 2:**
Before running any multi-cell pipeline or multi-model comparison loop, do a fast "smoke test" first — run the exact same code with `epochs=2` (or an equivalent minimal setting) to catch typos and shape errors in seconds rather than after a full, slow training run. This would have caught most of this sprint's bugs immediately instead of after multi-minute training cycles.


</div>
