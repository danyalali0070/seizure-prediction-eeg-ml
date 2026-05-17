# seizure-prediction-eeg-ml

# 🧠 Seizure Prediction: A Data-Driven Early Warning System

**Author:** Muhammad Danyal Ali (BCS-B) | IMSciences  
**Domain:** Machine Learning & Biomedical Signal Processing  

## 📌 Project Overview
This repository contains the code and academic report for my Semester Major Assignment. The project investigates how different machine learning preprocessing choices, model complexities, and regularization strategies affect the generalization performance of classifiers in predicting epileptic seizures from EEG data.

Rather than just chasing high accuracy, this project takes the "Honest Route"—evaluating the true clinical viability of linear baseline models (Logistic Regression) on highly non-linear, imbalanced physiological data.

## 📊 Datasets Evaluated
The pipeline was stress-tested across three distinct datasets to evaluate generalization:
1. **UCI Epileptic Seizure Recognition** (Structured Baseline)
2. **Bonn University EEG** (Raw Statistical Features)
3. **Kaggle-Style EEG** (Severe 10% Imbalance)

## 🛠️ Methodology Highlights
* **Preprocessing Comparison:** Demonstrated why Pipeline B (Extract → Scale → PCA) mathematically outperforms Pipeline A (Scale → Filter → Extract) by preventing outlier distortion from raw seizure spikes.
* **Regularization Study:** Compared L1 (Lasso), L2 (Ridge), and Elastic Net. Discovered that **Elastic Net** provided the most stable cross-dataset generalization by balancing sparsity and stability.
* **Class Imbalance:** Addressed severe imbalance using **SMOTE** and **Class Weighting**, transitioning the evaluation metric from misleading Accuracy to **PR-AUC (Precision-Recall)**.

## 💡 Key Clinical Insight: "Alarm Fatigue"
The empirical results revealed a crucial limitation of linear models. While the optimized pipeline achieved a PR-AUC of 0.450 (vastly outperforming random guessing), the low precision (28%) generated a high false-alarm rate. In a real-world clinical setting, this would induce "Alarm Fatigue" among nursing staff, proving that while linear models serve as excellent interpretable baselines, safe EEG prediction requires advanced non-linear Deep Learning architectures (CNNs/LSTMs).

## 📁 Repository Contents
* `Seizure_Prediction_ErrorFree.ipynb`: The complete Google Colab notebook containing all data cleaning, model training, evaluation metrics, and visualization code.
* `Seizure_Prediction_Report_Danyal.pdf`: The final, IEEE-formatted academic report detailing the experimental design, mathematical proofs, and clinical conclusions.

## 🚀 How to Run
1. Open the `.ipynb` file in Google Colab or a local Jupyter environment.
2. Ensure you have the Kaggle Epileptic Seizure `.csv` downloaded.
3. Run all cells sequentially. The pipeline handles data leakage prevention autonomously via `imblearn.pipeline`.
