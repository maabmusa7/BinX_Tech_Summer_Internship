<div align="center">
  <img src="https://img.shields.io/badge/Sprint--2_Phase--3-CNNs_|_RNNs_|_Transformers-blue?style=for-the-badge&logo=deepnote&logoColor=white&color=0A192F" alt="Sprint 2 Badge" />
  <img src="https://img.shields.io/badge/Frameworks-TensorFlow_|_Hugging_Face-orange?style=for-the-badge&logo=tensorflow&logoColor=white" alt="Frameworks Badge" />
  <img src="https://img.shields.io/badge/MLOps-MLflow-blueviolet?style=for-the-badge&logo=mlflow&logoColor=white" alt="MLOps Badge" />
  <img src="https://img.shields.io/badge/Compute-Google_Colab_GPU-red?style=for-the-badge&logo=googlecolab&logoColor=white&color=f9ab00" alt="GPU Badge" />
  
  <br />
  
  # 🚀 BinX Tech AI & ML Internship Program
  ## 📊 Week 07 — Deep Learning Architectures (Sprint 2)
  
  ---
</div>

## 🌟 Sprint Executive Summary
Week 7 marked the completion of **Sprint 2 (Phase 3 Capstone)**, transitioning from dense neural network baselines to specialized deep learning architectures. This sprint was dedicated to evaluating, implementing, and fine-tuning models across **Computer Vision (CNNs)**, **Sequence Modeling (RNNs/LSTMs)**, and **Natural Language Processing (Transformers)**. 

Key milestones include:
* **Computer Vision:** Implementing Transfer Learning with a pre-trained **MobileNetV2** base to achieve **97.43% validation accuracy** while slashing trainable parameters down to just **3,843**.
* **Sequence Modeling:** Performing a systematic evaluation of Recurrent Networks on 187-length ECG heartbeats, leading to a crucial "Aha!" moment where a non-sequential MLP baseline bypassed temporal instabilities to outperform both RNNs and LSTMs.
* **Natural Language Processing:** Upgrading our capstone news classifier from an LSTM baseline to a state-of-the-art **DistilBERT Transformer**, utilizing **MLflow** hyperparameter sweeps to achieve a champion test accuracy of **94.80% and a 0.948 Macro F1**

## 📑 Table of Contents
| Day | Topic |
|---|---|
| Day 01 | Sprint 2 Planning & CNNs |
| Day 02 | Building CNNs & Transfer Learning |
| Day 03 | RNNs & LSTMs for Sequential Data |
| Day 04 | Attention & Transformers |
| Day 05 | Advancing the Core Model & Sprint Review |

</div>

----

## 📝 Overview
Week 6 introduced neural networks from first principles before moving into a production-style framework. Starting with **activation functions** (ReLU, Sigmoid, Tanh) and a **hand-computed forward pass**, the week built up to the full **four-step training loop** (forward pass → loss → backpropagation → weight update), grounded with a hands-on **learning rate experiment** and a plain-language explanation of the **chain rule** behind backpropagation. From there, the project moved into **Keras**, building a Sequential network with the correct output activation and loss for binary classification, diagnosing fit from training/validation curves, and comparing **Dropout/Batch Normalization** against an unregularized baseline. The week closed with systematic **one-hyperparameter-at-a-time tuning**, **EarlyStopping**, and a full **Sprint 1 wrap-up** — assembling baseline-vs-neural-network evidence, opening and merging pull requests for mentor review, and writing a Sprint Review and Retrospective with a concrete action item for Sprint 2.
 
## Repository Directory Structure
    Week06
        README.md
        Day01
            Notebook7.1.ipynb
            README.md
        Day02
            Notebook7.2.ipynb
            README.md
        Day03
            Notebook7.3.2.ipynb
            README.md
        Day04
             Notebook7.4_hands_on_lab.ipynb
             README.md
        Day05
             Notebook7.5.ipynb
             README.md

## 🛠️ Deep Learning Tech Stack & Purposing

| Technology / Tool | Logo / Badge | Primary Engineering Purpose |
| :--- | :---: | :--- |
| **TensorFlow & Keras** | <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" /> | Designing custom sequential CNNs, pooling blocks, recurrent LSTM layers, and standardizing data preprocessing. |
| **Hugging Face** | <img src="https://img.shields.io/badge/%F0%9F%A4%97_Hugging_Face-FFD21E?style=flat-square" /> | Ingesting and fine-tuning pre-trained sequence classification models (`DistilBERT-base-uncased`) via state-of-the-art attention pipelines. |
| **MLflow** | <img src="https://img.shields.io/badge/MLflow-012549?style=flat-square&logo=mlflow&logoColor=white" /> | Systematic hyperparameter logging, experiment metrics tracking, and artifact versioning during capstone fine-tuning runs. |
| **Scikit-Learn** | <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white" /> | Generating robust model performance benchmarks, computing stratified train/validation splits, class weights, and evaluating metrics. |
| **Google Colab** | <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white" /> | Leveraging high-performance T4 GPUs to accelerate parallelized gradient updates and transformer fine-tuning loops. |


## 🔑 Key Topics

- Day 1 - Parameter sharing, translation invariance, stride, padding, and convolutional feature hierarchies.
- Day 2 - Max pooling downsampling, data augmentation transforms (horizontal flips, rotations, zooms), and ImageNet transfer learning.
- Day 3 - Gated memory cells (LSTMs/GRUs), backpropagation through time (BPTT), and handling high class imbalance in time-series data.
- Day 4 - Self-attention formulas, positional encoding, long-range dependency modeling, and the Hugging Face Transformers library.
- Day 5 - Hyperparameter tuning (batch size vs. learning rate), MLflow tracking integration, and Sprint 2 Retro.

## 📅 Daily Breakdown

| Day | Date | Topic | Summary | Deliverables & Experiments | Log |
|---|---|---|---|---|---|
| 01 | Aug 30 | Sprint 2 Planning & CNNs | Establish the Sprint 2 backlog and internalize why dense neural networks fail computationally on spatial data | Built a custom hand-defined edge-detection filter (Sobel kernel X & Y) using NumPy, convolving it across a sample image to visualize resulting directional feature maps
 | [Day01 →](./Day01/README.md) |
| 02 | Aug 31 | Building CNNs & Transfer Learning |  Design, regularize, and compare convolutional pipelines utilizing custom pooling architectures, data augmentations, and frozen pre-trained feature extractors | Built a 3-class bag classifier (15,000 images)
. Evaluated a custom CNN from scratch, an augmented CNN, and a pre-trained MobileNetV2 model | [Day02 →](./Day02/README.md) |
| 03 | Sep 1 | RNNs & LSTMs for Sequential Data | Investigate how recurrent hidden states propagate context through sequences, analyze the vanishing gradient problem, and implement class-weighted sequence architectures | Modeled 109,446 ECG heartbeat waveforms from the MIT-BIH dataset
. Conducted a diagnostic showdown comparing custom Simple RNNs and Stacked LSTMs against a non-sequential MLP baseline | [Day03 →](./Day03/README.md) |
| 04 | Sep 2 | Attention & Transformers | Break through the sequential execution limits of recurrent networks using parallelized attention mechanisms
 | Fine-tuned a pre-trained `distilbert-base-uncased` classifier on 127,600 AG News headlines, achieving a 3-point accuracy improvement over an LSTM baseline in just one epoch | [Day04 →](./Day04/README.md) |
| 05 | Sep 3 | Advancing the Core Model & Sprint Review |  Establish and run a hyperparameter tuning grid on our Capstone's selected core model architecture, logging all runs systematically to finalize Sprint 2 | Conducted MLflow-logged tuning runs on the DistilBERT news classifier
. Drafted the final metrics comparison charts and presented our champion model | [Day05 →](./Day05/README.md) |


### 🧠 Core Presentation Highlights & Technical Defense

* **Topic Taught:** Automated Hyperparameter Tuning (GridSearchCV & RandomizedSearchCV) & Building Leakage-Free ML Pipelines with Scikit-Learn

* **Key Engineering Arguments Delivered:**
   * Grounded how exhaustive vs. sampled search strategies trade off differently as the hyperparameter space grows — GridSearchCV's cost scales multiplicatively with every added parameter/value, while RandomizedSearchCV samples a fixed budget of combinations regardless of grid size, making it the practical choice once a search space grows beyond a small number of dimensions.
   * Justified why we selected `Pipeline` + `ColumnTransformer` as our required pattern over manual preprocessing, based on the fact that fitting a scaler, encoder, or imputer *before* cross-validation splitting lets fold-specific test data leak into training statistics — inflating CV metrics with information the model shouldn't have had access to. Wrapping every preprocessing step inside the pipeline object ensures each fold's transformer statistics are fit exclusively on that fold's own training partition [__, __].

* **Active Feedback & Peer Review:** Actively participated in peer reviews and providing/recieving constructive criticism on/from colleagues.


---

# 🏆 Sprint 2 Review

## Sprint Goal
Learn CNNs for images, RNN/s/LSTMs for sequences and attention mechanism behind Transformers and advance the project's core model.

## What Was Delivered

- **Sprint 2 Planning and CNN Notebook**. implementations on the 3-class `bag-classes` dataset - 15,000 images of garbage, paper and plastic bags- comparing a CNN baseline, Data Augmented CNN and a transfer learning pipeline.
- **Sequence modeling ECG Notebook**. Modeling 109k ECG heartbeat waveforms from MIT-BIH dataset. Conducted comparative training of a plain RNN & LSTM against a flat non-sequential MLP baseline under balanced class weight.
- **Transformer core model Notebook**. Fine-tuned a pre-trained Hugging Face **DistilBERT** model on the AG News text dataset and benchmarked it against a custom LSTM baseline.
- **Systematic MLOPs Tuning Pipeline**. Implemented MLflow logging to track hyperparameter grids (varying learning rate and batch sizes), saved model weights, compiled a final metric progression chart, and officially selected your Capstone's core architecture.
  
## Key Takeaways
- **Convolutional Efficiency & Parameter Sharing:** Fully connected networks fail computationally on images because flattening a spatial image (such as an RGB image) discards local pixel relationships and creates a massive weight overhead. Convolutional Neural Networks (CNNs) solve this by exploiting **local connectivity** and **parameter sharing**—sliding a small, identical filter repeatedly across the image to dramatically reduce trainable parameter counts.
- **The Practicality of Transfer Learning:** When working with limited custom datasets, reusing learned features from a frozen, pre-trained backbone yields exceptionally high validation accuracy while keeping trainable weight counts minimal and preventing overfitting.
- **The Recurrent Sequence Trap:** Recurrent architectures (RNNs and LSTMs) are designed for sequence-dependent context. However, training them on long sequences (e.g., 187-time-step ECG heartbeats) makes them highly prone to vanishing gradients, loss instabilities, and class collapses. For static, pre-aligned waveforms, a non-sequential MLP baseline can actually bypass these instabilities to perform faster and more accurately, showing that **the most complex model is not always the best engineering solution**.
- **Attention over Step-by-Step Memory:** Unlike RNNs, which compress historical tokens sequentially into a single, fixed-size hidden state (often overwriting distant context), **self-attention** allows every token to link directly to every other token regardless of distance. This makes Transformer architectures highly parallelizable and robust at extracting long-range context in text classification.
- **The Accuracy Trap in Imbalanced Data:** On highly imbalanced datasets, raw accuracy is a misleading metric because models can score high "fake" results by simply defaulting to the majority class. valuating **Macro F1 scores** and inspecting **confusion matrices** are mandatory for diagnosing class-wise performance and identifying minority-class collapses

## Key Results
A. **Computer Vision** (3-class bag classification)
  - *Baseline CNN:* Reached **90.53% validation accuracy** by epoch 15, but suffered from severe overfitting as validation loss climbed steadily to **0.6196** while training accuracy hit 99.3%.
  - *Augmented CNN:* Random transformations narrowed the training-validation gap slightly, raising validation accuracy to **90.97%** and lowering validation loss to **0.4693**.
  - *MobileNetV2 (Transfer Learning):*  Decisively won the vision track, achieving **97.43% validation accuracy** and a **low 0.0754 validation loss** with only 3,843 trainable parameters.
B. **Sequence Modeling (MIT-BIH ECG Heartbeats)**
  - *Simple RNN:* Suffered from extreme vanishing gradients and class collapse, yielding a misleading **66.97% test accuracy** but a critically poor **0.198 macro F1 score**.
  - *LSTM:* Suffered from loss instability, triggering early-stopping at epoch 9 with a **42.24% test accuracy** and **0.287 macro F1 score**.
  - *Multilayer Perceptron (MLP) Baseline:* Dominated this time-series task, achieving **83.91% test accuracy** and a **0.629 macro F1 score** in just *33.75 seconds*.
C. **Capstone Core Model** (AG News Classification)
  - *LSTM Baseline:* Reached **91.57% test accuracy** after 3 epochs, showing early validation degradation by epoch 3.
  - *DistilBERT - default:* Fine-tuned in a single epoch to reach **94.55% test accuracy** and a **0.945 macro F1 score**.
  - *DistilBERT - tuned / Run 0:*  Our peak performance deliverable. Configured with a learning rate of `3e-`5 and a batch size of `16` over `2` epochs, it achieved **94.80% validation accuracy** and a **0.948 Macro F1 score**.
    

## Sprint 1 Retrospective

**What went well:**
- Empirical Diagnostics: Running baseline-versus-complexity comparisons saved massive computational time by demonstrating that simple dense structures easily outperformed recurrent networks on static, pre-aligned waveform features.
- Efficiency via Transfer Learning: Reusing pre-trained weights (MobileNetV2 and DistilBERT) instantly boosted accuracy while keeping training times highly accessible.
- 
**What was challenging:**
- Recurrent Training Instability: Vanilla RNNs and LSTMs were highly sensitive to gradient vanishing and exploding over long sequence lengths, leading to early termination or collapse on minority classes.
- Imbalance Blindspots: The 12.5 : 1 class imbalance of the MIT-BIH dataset exposed how easily high raw accuracy figures can mask a model that is completely failing to identify rare cardiac conditions.
- Completing tasks with limited resources especially GPU capacity.

**One concrete procedure for Sprint 2:**
To prepare our selected DistilBERT champion model for production deployment

</div>
