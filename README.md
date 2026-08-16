# Telco Customer Churn Prediction

A reproducible machine learning project for predicting customer churn from the IBM Telco Customer Churn dataset. The workflow covers data understanding, exploratory analysis, preprocessing, baseline model comparison, deep neural network training, and DNN optimization.

## Project Overview

Customer churn prediction helps identify customers who are likely to leave a telecommunications provider. This project builds and compares classical machine learning models and neural network models using customer demographics, account details, subscribed services, and billing information.

The final optimized DNN prioritizes improved churn recall while maintaining competitive ROC-AUC against the baseline models.

## Dataset

- Source file: `data/WA_Fn-UseC_-Telco-Customer-Churn.csv`
- Target column: `Churn`
- Records: customer-level observations
- Features: demographics, tenure, contract type, internet and phone services, billing preferences, monthly charges, and total charges

## Repository Structure

```text
.
|-- data/                    # Raw Telco customer churn dataset
|-- models/                  # Saved preprocessors and trained DNN models
|-- notebooks/               # End-to-end analysis and modelling notebooks
|-- reports/                 # Model comparisons, experiment results, and metadata
|-- requirements.txt         # Python dependencies
`-- README.md
```

## Notebooks

Run the notebooks in order:

1. `notebooks/01_Data_Understanding.ipynb` - load the dataset and perform initial checks.
2. `notebooks/02_EDA.ipynb` - explore churn patterns and feature relationships.
3. `notebooks/03_Preprocessing.ipynb` - clean data, encode features, and prepare modelling inputs.
4. `notebooks/04_Baseline_Models.ipynb` - train and compare baseline classifiers.
5. `notebooks/05_DNN_Model_Proper.ipynb` - train the main DNN model and compare it with baselines.
6. `notebooks/06_DNN_Optimization.ipynb` - tune DNN variants and threshold settings.

## Model Results

Latest optimized comparison from `reports/dnn_optimized_comparison.csv`:

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | ---: | ---: | ---: | ---: | ---: |
| Logistic Regression | 0.8055 | 0.6582 | 0.5561 | 0.6029 | 0.8420 |
| Decision Tree | 0.7942 | 0.6296 | 0.5455 | 0.5845 | 0.8284 |
| Random Forest | 0.7892 | 0.6305 | 0.4973 | 0.5561 | 0.8226 |
| XGBoost | 0.8020 | 0.6568 | 0.5321 | 0.5879 | 0.8445 |
| Optimized DNN (O10-BatchNorm) | 0.7821 | 0.5781 | 0.6631 | 0.6177 | 0.8397 |

The optimized DNN uses a validation threshold of `0.45` and is saved as `models/churn_dnn_optimized.keras` with its preprocessing pipeline at `models/preprocessor_optimized.joblib`.

## Getting Started

Prerequisites:

- Python 3.8+
- Jupyter Lab or Jupyter Notebook

Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Launch Jupyter:

```powershell
jupyter lab
```

Then run the notebooks from `01_Data_Understanding.ipynb` through `06_DNN_Optimization.ipynb`.

## Saved Artifacts

The `models/` directory contains:

- `churn_dnn_best.keras` - selected DNN from the main DNN experiments.
- `churn_dnn_optimized.keras` - optimized DNN model.
- `preprocessor.joblib` - preprocessing pipeline for the main DNN model.
- `preprocessor_optimized.joblib` - preprocessing pipeline for the optimized DNN model.

The `reports/` directory contains experiment logs, comparison CSVs, final metrics, threshold results, and model metadata.

## Reproducibility Notes

- Keep the raw dataset in `data/` with the existing file name.
- Run notebooks sequentially because later notebooks depend on preprocessing and evaluation choices established earlier.
- Regenerated models and report files may differ slightly depending on package versions, random seeds, and hardware.
