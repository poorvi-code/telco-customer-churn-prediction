# Customer Churn Prediction

A reproducible project for exploratory data analysis, preprocessing, and baseline modelling to predict customer churn for a telecommunications dataset.

## Project Overview

This repository contains a data science workflow that explores the Telco Customer Churn dataset, performs EDA and preprocessing, and builds baseline classification models to predict whether a customer will churn.

## Dataset

- Source file: `data/WA_Fn-UseC_-Telco-Customer-Churn.csv`
- Summary: customer demographic, account, and service usage features with a `Churn` target column.

## Repository Structure

- `data/` — raw dataset CSV.
- `notebooks/` — Jupyter notebooks that implement the analysis and modelling pipeline:
	- [notebooks/01_Data_Understanding.ipynb](notebooks/01_Data_Understanding.ipynb)
	- [notebooks/02_EDA.ipynb](notebooks/02_EDA.ipynb)
	- [notebooks/03_Preprocessing.ipynb](notebooks/03_Preprocessing.ipynb)
	- [notebooks/04_Baseline_Models.ipynb](notebooks/04_Baseline_Models.ipynb)
- `models/` — trained model artifacts (empty in this snapshot).
- `reports/` — generated reports and figures.
- `requirements.txt` — Python dependencies.

## Getting Started

Prerequisites: Python 3.8+ recommended.

1. Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2. Install dependencies:

```powershell
pip install -r requirements.txt
```

3. Launch Jupyter Lab / Notebook and run the notebooks in order (01 → 04):

```powershell
jupyter lab
```

## Reproducible Workflow

Follow the notebooks in sequence:

- `01_Data_Understanding.ipynb`: data loading and sanity checks.
- `02_EDA.ipynb`: exploratory analysis and visualizations.
- `03_Preprocessing.ipynb`: data cleaning, feature engineering, and pipelines.
- `04_Baseline_Models.ipynb`: train/evaluate baseline classifiers and compare metrics such as accuracy, precision, recall, and ROC AUC.

To persist trained models, export them from the final notebook into the `models/` directory.




