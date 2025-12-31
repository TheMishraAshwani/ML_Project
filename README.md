### ML_Project

A portfolio of independent machine learning projects spanning healthcare diagnostics, food industry analytics, and business intelligence applications. Each project is implemented as a self-contained Jupyter notebook following standardized data science workflows.

## Overview

This repository demonstrates breadth of ML techniques across multiple domains rather than depth in a single system. It contains seven independent Jupyter notebook projects, each addressing distinct machine learning problems with consistent methodology but diverse algorithms and applications.

## Repository Organization

```
ML_Project Repository
├── Healthcare Analytics
│   ├── Fetal_health.ipynb
│   └── maternal_predicting_pregnancy_risk_levels.ipynb
├── Food Industry ML
│   ├── Cuisines_Classification.ipynb
│   ├── Restaurant_Recommendation.ipynb
│   └── Predict_Restaurant_Rating.ipynb
├── Business Intelligence
│   └── GreenDestination_DataScience.ipynb
└── Educational Demos
    └── Iris_Classification_.ipynb
```

## Project Inventory by Domain

### Healthcare Domain

| Notebook | Problem Type | Target Classes | Key Algorithms |
|----------|-------------|----------------|----------------|
| Fetal_health.ipynb | Multi-class classification | 3 fetal health states | Logistic Regression, SVM, Random Forest, Gradient Boosting, XGBoost, ANN |
| maternal_predicting_pregnancy_risk_levels.ipynb | Multi-class classification | 3 risk levels (low/mid/high) | 6 models + GridSearchCV hyperparameter tuning |

### Food & Restaurant Industry

| Notebook | Problem Type | Data Sources | Approach |
|----------|-------------|--------------|----------|
| Cuisines_Classification.ipynb | Multi-class classification | Cuisine dataset | 200+ cuisine categories |
| Restaurant_Recommendation.ipynb | Collaborative filtering | restaurants.csv, ratings.csv | SVD matrix factorization |
| Predict_Restaurant_Rating.ipynb | Regression | Restaurant dataset CSV | Linear regression with one-hot encoding |

### Business Analytics & Education

| Notebook | Domain | Focus |
|----------|--------|-------|
| GreenDestination_DataScience.ipynb | HR Analytics | Binary classification (attrition prediction) |
| Iris_Classification_.ipynb | Educational | Classic benchmark dataset (SVC vs Neural Network) |

## Standard ML Pipeline Implementation

All projects follow a consistent seven-stage pipeline architecture:

1. **CSV Data Loading** (`pandas.read_csv`)
2. **EDA** (`sns.pairplot`, `.info()`)
3. **Preprocessing** (`StandardScaler`, `LabelEncoder`)
4. **Feature Engineering** (`PCA`, `OneHot`)
5. **train_test_split`
6. **Model Training** (`sklearn` estimators)
7. **Evaluation** (`classification_report`, `metrics`)

### Key Code Patterns

```python
# Data Loading
data = pd.read_csv(csv_file)

# EDA
sns.pairplot(data, hue="fetal_health")

# Preprocessing
StandardScaler, LabelEncoder

# Model Training
sklearn.ensemble.RandomForestClassifier, sklearn.linear_model.LogisticRegression

# Evaluation
sklearn.metrics.classification_report, confusion_matrix
```

## Technology Stack Breakdown

### Core Data Science Libraries (Universal)

Every notebook imports and utilizes:

| Library | Purpose | Import Pattern |
|---------|---------|----------------|
| pandas | DataFrames | `import pandas as pd` |
| numpy | Arrays | `import numpy as np` |
| matplotlib.pyplot | Visualization | `import matplotlib.pyplot as plt` |
| seaborn | Statistical Plots | `import seaborn as sns` |

### Scikit-learn Ecosystem (6 of 7 Projects)

| Module | Primary Classes/Functions | Projects Using |
|--------|---------------------------|----------------|
| sklearn.model_selection | train_test_split, GridSearchCV, cross_val_score | 6 projects |
| sklearn.preprocessing | StandardScaler, LabelEncoder | 6 projects |
| sklearn.metrics | classification_report, confusion_matrix, mean_squared_error | 6 projects |
| sklearn.linear_model | LogisticRegression | Multiple |
| sklearn.svm | SVC | Multiple |
| sklearn.ensemble | RandomForestClassifier, GradientBoostingClassifier | Multiple |
| sklearn.decomposition | PCA | 1 project |

### Specialized Libraries

- **XGBoost**: `xgboost.XGBClassifier` used in Fetal_health.ipynb
- **TensorFlow/Keras**: Sequential neural networks in Fetal_health.ipynb and Iris_Classification_.ipynb
- **Surprise Library**: `surprise.SVD` for collaborative filtering in Restaurant_Recommendation.ipynb

## Data Input Patterns

Projects load data from CSV files or built-in datasets using consistent patterns:

| Data Sources | Examples |
|--------------|----------|
| Kaggle Datasets (kagglehub.dataset_download) | Fetal_health.ipynb, maternal_predicting_pregnancy_risk_levels.ipynb |
| Local CSV Files (pd.read_csv) | Restaurant projects, GreenDestination_DataScience.ipynb |
| sklearn.datasets (Iris) | Iris_Classification_.ipynb |

### Example Loading Code

```python
# Kaggle dataset download
path = kagglehub.dataset_download("andrewmvd/fetal-health-classification")
data = pd.read_csv(f"{path}/fetal_health.csv")
```

## Preprocessing Strategy Variations

| Strategy | Applicable To | Techniques | File Examples |
|----------|---------------|------------|---------------|
| Numerical-only | Fetal health, Iris | StandardScaler, PCA | Fetal_health.ipynb |
| Mixed data | Maternal risk, Employee attrition | LabelEncoder + scaling | maternal_predicting_pregnancy_risk_levels.ipynb, GreenDestination_DataScience.ipynb |
| Categorical-heavy | Restaurant ratings, Cuisines | Extensive one-hot encoding | Predict_Restaurant_Rating.ipynb, Cuisines_Classification.ipynb |

## Model Training Strategies

| Approach | Projects | Description |
|----------|----------|-------------|
| Single Model | 2 projects | Linear Regression |
| Multi-Model Comparison | 4 projects | 2-6 Model Evaluation |
| Hyperparameter Tuning | 1 project | GridSearchCV (maternal) |
| Specialized Algorithm | 1 project | SVD Matrix Factorization |

### Multi-Model Comparison Examples

- **Fetal_health.ipynb**: Compares 6 algorithms (Logistic Regression, SVM, Random Forest, Gradient Boosting, XGBoost, ANN)
- **maternal_predicting_pregnancy_risk_levels.ipynb**: 6 models + GridSearchCV for optimization

## Performance Characteristics

| Project | Problem Complexity | Best Model | Performance Notes |
|---------|-------------------|------------|-------------------|
| Iris_Classification_.ipynb | Simple (3 balanced classes) | SVC | 100% accuracy |
| Fetal_health.ipynb | Moderate (3 classes, 2126 samples) | ANN | High accuracy |
| maternal_predicting_pregnancy_risk_levels.ipynb | Moderate (3 risk levels) | Random Forest (tuned) | GridSearchCV optimized |
| Cuisines_Classification.ipynb | Complex (200+ classes) | N/A | 9% accuracy - severe class imbalance |
| Predict_Restaurant_Rating.ipynb | Failed experiment | Linear Regression | R² = -2026 (catastrophic) |
| Restaurant_Recommendation.ipynb | Specialized | SVD | RMSE/MAE evaluation |

## Repository Structure Summary

This portfolio demonstrates:

- **Breadth over depth**: 7 independent projects across 4 domains
- **Consistent methodology**: Standardized ML pipeline in all notebooks
- **Algorithm diversity**: 10+ different ML algorithms/techniques
- **Real-world scenarios**: Healthcare diagnostics, recommendation systems, business analytics
- **Educational value**: Includes both successful implementations and instructive failures (Cuisines, Restaurant Rating)

## Project Structure

```
- notebooks/       - Jupyter notebooks (cleaned and documented)
- src/             - Reusable Python modules extracted from notebooks
- data/            - Datasets (not committed)
- models/          - Saved model artifacts (not committed)
- results/         - Output plots and reports
- tests/           - Unit tests for extracted modules
- .github/         - CI and issue templates
```

## Quickstart

1. Create environment (Python 3.12 recommended):
   - `python -m venv .venv && source .venv/bin/activate`
   - OR (conda) `conda create -n mlproj python=3.12 && conda activate mlproj`
2. Install dependencies:
   - `pip install -r requirements.txt`
3. Start Jupyter Lab:
   - `jupyter lab`
4. Open notebooks in `notebooks/`. Notebooks in the repository root are the original copies and have been preserved for reference.

## Notebooks (cleaned copies)

- 01-iris-classification.ipynb — Basic Iris dataset classification walkthrough
- 02-cuisines-classification.ipynb — Cuisine prediction / text classification case study
- 03-green-destination-datascience.ipynb — Data science case study for green destination dataset
- 04-predict-restaurant-rating.ipynb — Regression/classification to predict ratings
- 05-restaurant-recommendation.ipynb — Recommendation system example
- 06-fetal-health.ipynb — Fetal health classification case study
- 07-maternal-predicting-pregnancy-risk-levels.ipynb — Maternal health risk classification (large notebook — review in place)

Note: The notebooks in `notebooks/` are cleaned placeholder copies (outputs removed).

## Contributing

Please read CONTRIBUTING.md for guidelines on notebooks (clear outputs, narrative cells) and code style.

## License

This project is licensed under the MIT License — see LICENSE for details.

## Contact

Author: TheMishraAshwani
