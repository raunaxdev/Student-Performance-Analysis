# Student Performance Analysis and Prediction System

A reproducible data-analysis and machine-learning project that explores student assessment results and predicts average scores from demographic, education, and test-preparation attributes.

## Features

- A seeded, synthetic dataset with 1,000 student records.
- Exploratory visualizations of score distributions, average scores by gender, and score correlations.
- A scikit-learn preprocessing and regression pipeline with one-hot encoding and a random forest.
- A reproducible 80/20 train-test evaluation using R² and root mean squared error (RMSE).
- PNG plots saved in `images/` when the notebook is run.

## Project structure

```text
dataset/
  StudentsPerformance.csv
images/
notebooks/
  eda_and_model_training.ipynb
requirements.txt
README.md
```

## Dataset

`dataset/StudentsPerformance.csv` contains 1,000 synthetic records with these columns:

| Column | Values |
|---|---|
| gender | male, female |
| race/ethnicity | group A, group B, group C, group D, group E |
| parental level of education | bachelor's degree, some college, master's degree, associate's degree, high school, some high school |
| lunch | standard, free/reduced |
| test preparation course | none, completed |
| math score, reading score, writing score | Integer scores from 0 to 100 |

The records are generated for this project and are not real student records. Scores have plausible relationships to preparation, lunch, and parental education; use them for demonstration, not high-stakes decisions.

## Installation and execution

Python 3.10 or later is recommended.

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook notebooks/eda_and_model_training.ipynb
```

Run all cells from top to bottom. The notebook reads the CSV, derives `total_score` and `average_score`, saves visualizations in `images/`, fits the model, and prints its held-out evaluation metrics.

## Evaluation

The notebook predicts `average_score` from the five categorical attributes using a `RandomForestRegressor`. With the included seeded dataset and fixed 20% test split (`random_state=42`), the executed notebook reports:

- **R²:** 0.2691
- **RMSE:** 8.6492 points

These are demonstration results on synthetic data; run the notebook to reproduce them.
