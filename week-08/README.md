<div align="center">
  <img src="https://img.shields.io/badge/Sprint--3_Phase--4-NLP_|_Computer_Vision_|_Integration-blue?style=for-the-badge&logo=deepnote&logoColor=white&color=0A192F" alt="Sprint 3 Badge" />
  <img src="https://img.shields.io/badge/Frameworks-PyTorch_|_Hugging_Face_|_OpenCV-orange?style=for-the-badge&logo=pytorch&logoColor=white" alt="Frameworks Badge" />
  <img src="https://img.shields.io/badge/Explainability-SHAP-blueviolet?style=for-the-badge&logo=mlflow&logoColor=white" alt="Explainability Badge" />
  <img src="https://img.shields.io/badge/Compute-Google_Colab_GPU-red?style=for-the-badge&logo=googlecolab&logoColor=white&color=f9ab00" alt="GPU Badge" />
  <br />
  
  # 🚀 BinX Tech AI & ML Internship Program
  ## 📊 Week 08 — NLP & COMPUTER VISION — SPRINT 3
 
  ---
  
</div>

## 🌟 Sprint Executive Summary
Sprint 3 moved the capstone news classifier from a trained model into a fully integrated, explainable, and evaluated pipeline, while building parallel NLP and Computer Vision preprocessing skills. The sprint opened with **text preprocessing and representation** (tokenization, cleaning, TF-IDF, and word embeddings), pivoted into **image preprocessing** for a second dataset (bag classification), and closed by wrapping the DistilBERT capstone model into a single **end-to-end `predict()` pipeline**, complete with a **confusion matrix**, **misclassified-example error analysis**, and **SHAP explainability**.
 
Key milestones include:
* **NLP Preprocessing & Representation:** Building a leakage-aware text-cleaning pipeline and benchmarking a **TF-IDF + Logistic Regression** baseline at **91.10% accuracy / 0.9109 Macro F1** against the Sprint 2 LSTM (91.82%) and DistilBERT (94.55%) results.
* **Computer Vision Preprocessing:** Building an OpenCV-based image pipeline (resize, RGB conversion, normalization) and augmentation pipeline for a new 3-class, 15,000-image **Bag Classification dataset** (Plastic / Paper / Garbage), with MobileNetV2-specific `preprocess_input` applied for future transfer learning.
* **Model Integration:** Wrapping the DistilBERT capstone model and tokenizer into a single `predict()` function, verifying training/serving consistency, and migrating the pipeline from TensorFlow to PyTorch mid-sprint to resolve library version conflicts.
* **Full Evaluation & Explainability:** Producing task-appropriate metrics (Precision/Recall/F1/AUC-ROC) against baseline, confirming no class-imbalance handling was needed (balanced dataset), and generating **SHAP** global and per-prediction explanations for the transformer classifier.

## 📑 Table of Contents
| Day | Topic |
|---|---|
| Day 01 | Sprint 3 Planning & NLP Preprocessing |
| Day 02 | Text Representation: TF-IDF & Embeddings |
| Day 03 | Computer Vision Preprocessing with OpenCV |
| Day 04 | Model Integration & Error Analysis |
| Day 05 | Full Evaluation, Explainability & Sprint Review |
 
---
 
## 📝 Overview
Sprint 3 focused on integration and evaluation rather than new model architectures. Day 1 revisited **why raw text needs cleaning** before it can be vectorized, building a lowercase → punctuation-removal → stopword-removal → lemmatization pipeline and explicitly verifying it preserved task-critical signal for a topic-classification task. Day 2 converted that cleaned text into numeric form via two families of representation — frequency-based **TF-IDF** and meaning-based **word embeddings** — establishing a fast, interpretable baseline against the project's existing deep learning models. Day 3 shifted to a second, image-based dataset, applying the same "preprocessing before modeling" discipline via OpenCV and Keras augmentation tools. Day 4 tied everything together: the trained DistilBERT model and its tokenizer were wrapped into a single, deployable `predict()` function, with explicit checks to guarantee no training/serving skew. Day 5 closed the sprint with a full, metrics-driven evaluation against baseline and SHAP-based explainability, preparing the model for Sprint 4 deployment.
 
## Repository Directory Structure

    Week08
        README.md
        Day01
            Notebook8_1.ipynb
            README.md
        Day02
            Notebook8_2.ipynb
            README.md
        Day03
            Notebook8_3.ipynb
            README.md
        Day04
            Notebook8_4.ipynb
            README.md
        Day05
            Notebook8_5.ipynb
            README.md
 
## 🛠️ Deep Learning Tech Stack & Purposing
 
| Technology / Tool | Logo / Badge | Primary Engineering Purpose |
| :--- | :---: | :--- |
| **NLTK** | <img src="https://img.shields.io/badge/NLTK-3776AB?style=flat-square&logo=python&logoColor=white" /> | Tokenization, stopword removal, and lemmatization for the AG News text-cleaning pipeline. |
| **Scikit-Learn** | <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white" /> | TF-IDF vectorization, Logistic Regression baseline, train/validation splitting, and full classification-report evaluation. |
| **Gensim** | <img src="https://img.shields.io/badge/Gensim-FF6F00?style=flat-square" /> | Loading pre-trained GloVe word embeddings and exploring semantic nearest-neighbor geometry. |
| **OpenCV** | <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white" /> | Reading, resizing, color-converting, and normalizing raw images for the Bag Classification dataset. |
| **TensorFlow/Keras (ImageDataGenerator)** | <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" /> | Building and visualizing an image augmentation pipeline (rotation, shift, flip, zoom, brightness). |
| **Hugging Face (PyTorch)** | <img src="https://img.shields.io/badge/%F0%9F%A4%97_Hugging_Face-FFD21E?style=flat-square" /> | Loading the saved DistilBERT capstone model/tokenizer and wrapping them into a single integrated `predict()` pipeline. |
| **SHAP** | <img src="https://img.shields.io/badge/SHAP-8A2BE2?style=flat-square" /> | Generating global feature importance and per-prediction explanations for the DistilBERT text classifier. |
| **Seaborn / Matplotlib** | <img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=plotly&logoColor=white" /> | Confusion matrix heatmaps, class-distribution charts, and pixel-intensity/before-after visualizations. |
| **Google Colab** | <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white" /> | GPU-accelerated inference and evaluation for the DistilBERT pipeline. |
 
## 🔑 Key Topics
 
- Day 1 - Why text needs preprocessing, word/sub-word tokenization, lowercasing, punctuation and stopword removal, lemmatization vs. stemming, task-dependent cleaning decisions.
- Day 2 - Bag-of-words and TF-IDF weighting, word embeddings and semantic geometry, contextual embeddings, TF-IDF vs. embeddings trade-offs.
- Day 3 - OpenCV image reading/resizing/color-conversion/normalization, augmentation pipelines, model-specific `preprocess_input` requirements.
- Day 4 - End-to-end `predict()` pipeline design, training/serving skew, confusion matrices, qualitative misclassified-example analysis.
- Day 5 - Task-appropriate evaluation metrics, class-imbalance assessment, SHAP global/per-prediction explainability, Sprint Review & Retrospective.


## 📅 Daily Breakdown
 
| Day | Topic | Summary | Deliverables & Experiments |
|---|---|---|---|
| 01 | Sprint 3 Planning & NLP Preprocessing | Built and debugged a full text-cleaning pipeline for AG News, verifying it preserved task-critical topic signal | Tokenized and cleaned AG News text (lowercase, punctuation removal, stopword removal, lemmatization); identified and fixed a bug where lemmatization was silently running on unfiltered tokens; documented the stopword-vs-topic-signal trade-off in Markdown |
| 02 | Text Representation: TF-IDF & Embeddings | Converted cleaned text into numeric vectors via two representation families and benchmarked against existing deep learning baselines | Trained a **TF-IDF + Logistic Regression** baseline (91.10% accuracy, 0.9109 Macro F1); loaded pre-trained GloVe embeddings and inspected nearest-neighbor semantic geometry; documented representation choice vs. LSTM/DistilBERT |
| 03 | Computer Vision Preprocessing with OpenCV | Built an OpenCV preprocessing and augmentation pipeline for a new 3-class Bag Classification dataset | Loaded and labeled 15,000 images (Plastic/Paper/Garbage, balanced 5,000 each); built `preprocess_image()` (resize, BGR→RGB, normalize); visualized 5 augmented variants of a sample image; applied MobileNetV2's `preprocess_input` for future transfer learning |
| 04 | Model Integration & Error Analysis | Wrapped the DistilBERT capstone model into a single deployable prediction pipeline and diagnosed its errors | Built and debugged an end-to-end `predict()` function (migrated from TensorFlow to PyTorch mid-sprint after unresolved dependency conflicts); verified training/serving consistency; generated a confusion matrix; inspected misclassified examples for data-quality vs. model-weakness patterns |
| 05 | Full Evaluation, Explainability & Sprint Review | Closed Sprint 3 with metrics-driven evaluation and model explainability | Produced a full classification report (Precision/Recall/F1) and macro AUC-ROC against the Sprint 2 baseline; confirmed class-imbalance handling was not applicable (balanced dataset); generated SHAP global and per-prediction text explanations; completed Sprint Review and Retrospective |
 
### 🧠 Core Presentation Highlights & Technical Defense
 
* **Topic Taught:** Automated Hyperparameter Tuning (GridSearchCV & RandomizedSearchCV) & Building Leakage-Free ML Pipelines with Scikit-Learn
* **Key Engineering Arguments Delivered:**
   * Grounded how exhaustive vs. sampled search strategies trade off differently as the hyperparameter space grows — GridSearchCV's cost scales multiplicatively with every added parameter/value, while RandomizedSearchCV samples a fixed budget of combinations regardless of grid size, making it the practical choice once a search space grows beyond a small number of dimensions.
   * Justified why `Pipeline` is the required pattern over manual preprocessing, based on the fact that fitting a scaler, encoder, or imputer *before* cross-validation splitting lets fold-specific test data leak into training statistics — inflating CV metrics with information the model shouldn't have had access to. Wrapping every preprocessing step inside the pipeline object ensures each fold's transformer statistics are fit exclusively on that fold's own training partition.
   * Tied the two subtopics together: hyperparameters are the primary lever for controlling overfitting, but that lever only works if the evaluation itself is honest — leakage corrupts the evaluation, so even a "well-tuned" model's hyperparameters can't be trusted without a leakage-free pipeline underneath them.
* **Active Feedback & Peer Review:** Actively participated in peer reviews and providing/receiving constructive criticism on/from colleagues.
---
 
# 🏆 Sprint 3 Review
 
## Sprint Goal
Integrate the capstone model into a complete, end-to-end pipeline and perform rigorous evaluation, while building parallel NLP text-representation and Computer Vision preprocessing skills.
 
## What Was Delivered
 
- **NLP Preprocessing & Representation Notebooks.** A debugged text-cleaning pipeline for AG News, plus a TF-IDF + Logistic Regression baseline and a GloVe embedding exploration, benchmarked against the Sprint 2 LSTM and DistilBERT results.
- **Computer Vision Preprocessing Notebook.** An OpenCV read/resize/RGB/normalize pipeline and Keras augmentation pipeline for a new 3-class, 15,000-image Bag Classification dataset, with MobileNetV2-specific preprocessing applied.
- **Integrated Prediction Pipeline Notebook.** A single `predict()` function wrapping the DistilBERT capstone model and tokenizer, migrated from TensorFlow to PyTorch mid-sprint, with training/serving consistency explicitly verified.
- **Full Evaluation & Explainability Notebook.** A complete metrics report (Precision/Recall/F1/AUC-ROC) against baseline, a documented class-imbalance assessment, and SHAP global and per-prediction explanations for the transformer classifier.

## Key Takeaways
- **Preprocessing Is Task-Dependent, Not One-Size-Fits-All:** The same cleaning step (e.g., stopword removal) can be safe for one task and harmful for another — verifying that cleaning preserves task-critical signal is a required step, not an afterthought.
- **Frequency-Based Representations Are a Strong, Cheap Baseline:** TF-IDF + Logistic Regression reached 91.10% accuracy — within striking distance of the LSTM (91.82%) and only ~3.5 points behind DistilBERT (94.55%) — at a fraction of the training cost, reinforcing that model complexity should be justified by the accuracy gain it actually delivers.
- **Training/Serving Skew Is a Silent, Real-World Risk:** Preprocessing mismatches between training and prediction time (e.g., applying manual NLTK cleaning before a transformer that expects raw text) can silently corrupt predictions without raising any error — integration testing has to explicitly check for this.
- **Library Version Drift Is a Genuine Engineering Cost:** A `transformers` library upgrade removed TensorFlow-specific classes mid-sprint, cascading into `tokenizers` build failures and `huggingface-hub` conflicts with other pre-installed packages — resolved by migrating the integration pipeline from TensorFlow to PyTorch rather than continuing to fight version pins.
- **Explainability Closes the Trust Gap:** A high-accuracy model that cannot explain individual predictions is hard to deploy responsibly — SHAP's per-prediction word-level attributions turn an opaque transformer decision into something a non-technical stakeholder can inspect.

## Key Results
A. **NLP Text Representation** (AG News Classification)
  - *TF-IDF + Logistic Regression:* Reached **91.10% accuracy** and a **0.9109 Macro F1**, with Sports the easiest class to separate (0.96 F1) and Business the hardest (0.88 F1) due to vocabulary overlap with World news.
  - *LSTM Baseline (Sprint 2):* **91.82% test accuracy**.
  - *DistilBERT (Sprint 2, fine-tuned):* **94.55% test accuracy**, **0.945 Macro F1** — selected as the project's production model.
B. **Computer Vision Preprocessing** (Bag Classification)
  - Loaded and verified **15,000 images** across 3 balanced classes (Plastic/Paper/Garbage, 5,000 each).
  - Built and validated an OpenCV pipeline producing a consistent **(224, 224, 3)** output shape, normalized to **[0.0, ~1.0]**.
  - Confirmed MobileNetV2's `preprocess_input` produces the expected **[-1, 1]** range, distinct from the manual [0, 1] normalization — flagged as the correct stage-appropriate step for future model training.
C. **Integrated Pipeline & Evaluation** (AG News, DistilBERT)
  - Successfully wrapped the model into a single `predict()` function with verified training/serving consistency.
  - Generated a confusion matrix identifying the model's most common confusion pattern (World ↔ Business, consistent with the vocabulary-overlap pattern also seen in the TF-IDF baseline).
  - Produced SHAP global and per-prediction explanations, surfacing which words most influenced individual classification decisions.

## Sprint 3 Retrospective
 
**What went well:**
- Reusing already-fine-tuned model weights (loaded from a saved checkpoint) avoided costly retraining during the integration and evaluation stages.
- Benchmarking TF-IDF against the existing LSTM/DistilBERT results provided a clear, quantified view of the accuracy-vs-complexity trade-off across three representation strategies.

**What was challenging:**
- A `transformers` library upgrade silently broke TensorFlow-specific model classes mid-sprint; attempts to pin an older, compatible version triggered further `tokenizers` build failures and `huggingface-hub` dependency conflicts with other pre-installed Colab packages.

**One concrete procedure for Sprint 4:**
Pin exact library versions in a requirements file at the start of the sprint, and consolidate the model/data "reload" steps into a single setup cell early in the notebook, to avoid repeated environment-debugging time during deployment.
 
