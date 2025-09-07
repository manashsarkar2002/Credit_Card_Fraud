Credit Card Fraud Detection

Credit Card Fraud Detection is a machine learning project for detecting fraudulent transactions using classical ML and basic ML operations for imbalanced data. This repo contains data preprocessing, exploratory data analysis (EDA), model training, evaluation, and inference scripts — ready to reproduce and extend.

🚀 Project Overview

Goal: Build and evaluate models that identify fraudulent credit card transactions.

Approach: Clean & preprocess transaction data → perform EDA → handle class imbalance → train baseline & advanced models → evaluate with appropriate metrics (precision, recall, F1, ROC-AUC) → produce inference pipeline.

Intended audience: Students, ML practitioners, and recruiters who want a clear end-to-end pipeline for fraud detection.
📥 Dataset

Typical dataset used: Kaggle - Credit Card Fraud Detection (transactions made by European cardholders).

Dataset characteristics:

Highly imbalanced (fraudulent transactions ≪ non-fraudulent).

Features are often PCA components (V1..V28) + Time, Amount, and label Class (0 = normal, 1 = fraud).

Place the downloaded CSV in data/raw/ (e.g., data/raw/creditcard.csv) before running preprocessing.

⚠️ Do not upload raw data with sensitive information to public repositories. Keep data/ excluded via .gitignore if necessary.
🧹 Preprocessing & Feature Engineering

Typical steps included in src/data_processing.py:

Load CSV and examine missing values.

Scale Amount and Time (e.g., StandardScaler or RobustScaler).

Optionally create features (hour of day from Time, transaction amount buckets).

Train/test split (stratified by label).

Save processed data to data/processed/.

⚖️ Handling Class Imbalance

Common techniques applied:

Resampling: SMOTE (oversampling minority), RandomUnderSampler, or combination (SMOTEENN).

Class-weighted models: many sklearn models accept class_weight='balanced'.

Anomaly detection: isolation forests, one-class SVM for unsupervised detection.

🧪 Models & Training

Baseline and advanced models typically included:

Logistic Regression (baseline)

Random Forest

XGBoost / LightGBM
