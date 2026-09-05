# Fraud Detection on Imbalanced Financial Transaction Data

An end-to-end machine learning pipeline for detecting fraudulent credit card transactions, built around the central challenge of **extreme class imbalance** (fraud is typically <0.2% of transactions).

## Overview

This project walks through the full workflow of building a fraud detection model:

- Loading and profiling a heavily imbalanced dataset
- Exploratory data analysis (transaction amount, time-of-day patterns)
- Explaining why accuracy is a misleading metric for this problem
- Handling class imbalance with **SMOTE** oversampling and `class_weight='balanced'`
- Training and comparing **Logistic Regression** and **Random Forest** classifiers
- Evaluating with precision, recall, F1-score, and AUC-ROC (not accuracy)
- Analysing which metric matters most for fraud detection (recall vs. precision trade-off)
- Feature importance / coefficient analysis
- Discussing how the pipeline would need to scale to 1M+ transactions/hour in production

## Dataset

This project is built against the [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud):

- 284,807 transactions, 492 fraudulent (~0.17% fraud rate)
- Features `V1`–`V28` are PCA-anonymized components of the original transaction data
- `Time` and `Amount` are the only non-anonymized features
- `Class` is the target: `1` = fraud, `0` = legitimate

**The dataset is not included in this repo** (Kaggle's terms require downloading it directly). See [Setup](#setup) below.

If `creditcard.csv` is not found, the notebook automatically falls back to a synthetic dataset with the same schema and a comparable imbalance ratio, so it will still run end-to-end for demo purposes — but results should only be treated as final once run against the real data.

## Tech Stack

- Python 3
- pandas, numpy
- scikit-learn
- imbalanced-learn (SMOTE)
- matplotlib, seaborn
- Jupyter Notebook

## Setup

1. Clone this repo:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-name>
   ```

2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. Download `creditcard.csv` from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) and place it in the project root (same folder as the notebook).

4. Launch Jupyter and run the notebook top to bottom:
   ```bash
   jupyter notebook fraud_detection_pipeline.ipynb
   ```

## Project Structure

```
.
├── fraud_detection_pipeline.ipynb   # Main notebook: full pipeline
├── requirements.txt                 # Python dependencies
├── creditcard.csv                   # Dataset (not tracked in git — download separately)
└── README.md
```

## Approach

| Step | Technique |
|---|---|
| Class imbalance handling | SMOTE (oversampling) on training data only; `class_weight='balanced'` as a comparison |
| Train/test split | Stratified split to preserve fraud ratio in both sets |
| Models | Logistic Regression, Random Forest |
| Evaluation | Precision, Recall, F1-score, AUC-ROC, confusion matrix, ROC & PR curves |
| Feature analysis | Logistic Regression coefficients, Random Forest feature importances |

## Key Takeaways

- **Accuracy is not a useful metric here** — a model predicting "legitimate" for every transaction scores >99.8% accuracy while catching zero fraud.
- **Recall is generally prioritized over precision** in fraud detection, since missed fraud (false negatives) is typically far more costly than a false alarm (false positive).
- **SMOTE must be applied only to training data**, after the train/test split, to avoid data leakage and inflated evaluation metrics.
- Scaling to production volumes (~1M transactions/hour) is primarily a systems/engineering problem — streaming ingestion, low-latency model serving, and real-time feature stores — layered on top of a model chosen partly for inference cost.

## License

This project is for educational/internship purposes. The dataset is provided by [ULB Machine Learning Group](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) under its own Kaggle license terms.

