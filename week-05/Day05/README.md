<div align="center">

# Day 05 -  Phase 3 Project Selection & Sprint 1 Planning

  *Thursday, August 20, 2026*

[← Previous Day](../Day04/README.md) 
</div>

---

## **Tasks**
- [x] Update the Cardiac Patient Monitoring System Project with Unsupervised Learning parts.
- [ ] Review the six project options with your mentor and select one based on your strengths and
interests.
- [ ] Create the Sprint 1 backlog (dataset selection, EDA, baseline model) with written acceptance
criteria per task.
- [ ] Define the Sprint 1 goal and get mentor sign-off before any Phase 3 work begins.
- [ ] Set up the project GitHub repository with a README skeleton and a feature-branch workflow.

## **What i did:**
- Reviewed week 5 materials & resources. 
- Finalised the unsupervised learning part of the project and README.
- Selected a project of interest.


## **Materials Used:**
- Week 5 day 5 material.
- GitHub.
- Claude.
- YouTube: XGBoost for Multi-Class Classification with Python | Step-by-Step with Hyperparameter Tuning
  

## **What i learned:**
- XGBoost for Multiclassifiction.

## **Challenges:**
- Completeing the unsupervised part of the project on the synthetic dataset I previously used. 

## **Related Files:**
[`Cardiac_Patient_Monitoring_Syatem_Project.ipynb`]


---

# Unsupervised Learning - Project Documentation Report

## 1. Project Context & Selection Rationale

This unsupervised learning analysis was completed as an extension to the Cardiac Patient Monitoring System capstone project, following the completion of supervised learning phase.

**Why this direction was chosen:** The goal was to explore whether natural patient groupings exist in the dataset independent of the `Heart_Disease` label, using clustering, dimensionality reduction, and anomaly detection techniques relevant to understanding the dataset's underlying structure.

---

## 2. Problem Statement & Definition of Done

**Problem Statement:** Do the clinical, demographic and lifestyle features in the dataset naturally group patients into distinct subpopulations, and can these groupings reveal structure not captured by the binary `Heart_Disease` label?

**Definition of Done:**
- [x] At leat 3 three clustering methods(K-Means, DBSCNAN, Hierarchical) run and compared on the same scaled feature.
- [x] Optimal K-Means `k` selected via elbow method + silhouette screen, with visualised and interpreted results.
- [x] Dimensionality reduction (PCA and t-SNE) applied and compared
- [x] Anomaly detection performed (Isolation Foresr) with flagged points individually inspected and hypothesised.
- [x] All findings documented in plain language, including negative and weak results.

---

## 3. Completed Backlog

| Task |  Method/Parameters | Acceptance Criteria | Status |
|---|---|---|---|
| Data Preperation | Scaled numeric features `StandardScaler` excluding target | Scaled features, no target leakage | Done |
| K-Means clustering | Elbow method `k=1-10`, Silhouette score for comparison | Optimal k selected, clusters visualised  | Done |
| DBSCAN clustering | eps=0.9, min_smaples=5 | Cluster count and noise points reported | Done |
| Hierarchical clustering | Ward linkage, sampled, dendrogram + cut height| Built dendrogram and cut height chosen and justified | Done |
| Clustering method comparison | Silhouette score | comparison table, best fit model conclusion | Done |
| PCA | variance analysis | Components needed for ≥ 95% variance reported | Done |
| t-SNE | 2D Projection, compered to PCA | visual comparison and interpretation | Done |
| Isolation Forest | Anomaly detection on full feature set | 2 points individually inspected, anomaly count reported | Done |

---

## 4. Goal Outcome Summary

**Sprint Goal:** Determine wether the dataset contains meaningful natural patient clusters.
**Outcome:** No method produced strongly separated clusters. Silhouette score stayed lo across K-Mean, DBSCAN, and Hierarchical clustering. The mild clusters that emerged were driven by blood pressure patterns.

---

## 5. Repository and Reproducability

- All unsupervised analysis code is contained in the existing project notebook, after the feature engineering section.
- README updated with a dedicated **Unsupervised Learning** section reflecting this work.
- No new branches/repo structure were required as this work extends the existing single notebook, except for the updated notebook being added to the notebook file of the project directory and under week5, day 5
