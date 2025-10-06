# Online_payment_fraud_detection
Machine learning project to detect fraudulent online transactions using real-world data.

## Project Overview
This repository demonstrates a machine learning approach for detecting fraudulent online payment transactions. The project uses a large dataset of real transaction records to build and evaluate classifiers for the automatic flagging of suspicious activity.

## Problem Statement
Online payment systems are vulnerable to increasingly sophisticated fraud attempts. Detecting fraudulent transactions early is critical to reducing financial losses. This notebook explores preprocessing, feature engineering, and modeling to distinguish legitimate transactions from fraudulent ones.

## Dataset
- **Source:** Contains 6,362,620 rows and 11 transaction features.  
- **Main Columns:**  
  - `step`: Time-step for the transaction  
  - `type`: Transaction type (PAYMENT, TRANSFER, CASHOUT, DEBIT)  
  - `amount`: Transaction amount  
  - `nameOrig`/`nameDest`: Origin and destination account IDs  
  - `oldbalanceOrg`/`newbalanceOrg`: Balances before/after for origin  
  - `oldbalanceDest`/`newbalanceDest`: Balances before/after for destination  
  - `isFraud`: Binary label (fraud/not fraud)  
  - `isFlaggedFraud`: Flagged by threshold
- **Imbalance:** Less than 0.13% of samples are fraud, requiring careful workflow for fair detection.

## Methodology
- **Data Exploration:** Statistical summaries, distribution and correlation plots for both features and fraud labels.
- **Preprocessing:** One-hot encoding for categorical features; separation of features and target column.
- **Model Selection:**  
  - Logistic Regression  
  - XGBoost Classifier  
  - Random Forest Classifier (best performance)
- **Evaluation:** Metrics include ROC AUC, training/validation accuracy, and interpretive plots. Random Forest achieved validation accuracy above 96%, Logistic Regression scored ~91%, and XGBoost scored ~71%.

## Results
- Fraud is disproportionately present in `TRANSFER` and `CASHOUT` transactions.
- Random Forest (7 estimators, entropy) gave the highest validation accuracy (96.4%) and near-perfect training fit.
- Logistic Regression performed well, but had convergence warnings (solver stopped early).
- Data imbalance was visually and numerically confirmed, suggesting further improvements with specialized sampling or custom metrics.


## Visualizations
The notebook provides:
- Distribution plots of transaction types and fraud distribution.
- Correlation heatmaps and feature importance visualizations.
- Bar plots for value counts and fraud occurrences by transaction type.
- <img width="567" height="406" alt="Screenshot 2025-10-06 154837" src="https://github.com/user-attachments/assets/8a93cb92-3229-4a4a-a4e4-9e011fc4056b" />


