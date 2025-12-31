# ML_Project

A collection of Jupyter notebooks demonstrating machine learning projects (classification, recommendation systems, and data science case studies).

## Project structure

- notebooks/       - Jupyter notebooks (cleaned and documented)
- src/             - Reusable Python modules extracted from notebooks
- data/            - Datasets (not committed)
- models/          - Saved model artifacts (not committed)
- results/         - Output plots and reports
- tests/           - Unit tests for extracted modules
- .github/         - CI and issue templates

## Quickstart

1. Create environment (Python 3.12 recommended):
   - python -m venv .venv && source .venv/bin/activate
   - OR (conda) conda create -n mlproj python=3.12 && conda activate mlproj
2. Install dependencies:
   - pip install -r requirements.txt
3. Start Jupyter Lab:
   - jupyter lab
4. Open notebooks in `notebooks/`. Notebooks in the repository root are the original copies and have been preserved for reference.

## Notebooks (cleaned copies)
- 01-iris-classification.ipynb — Basic Iris dataset classification walkthrough
- 02-cuisines-classification.ipynb — Cuisine prediction / text classification case study
- 03-green-destination-datascience.ipynb — Data science case study for green destination dataset
- 04-predict-restaurant-rating.ipynb — Regression/classification to predict ratings
- 05-restaurant-recommendation.ipynb — Recommendation system example
- 06-fetal-health.ipynb — Fetal health classification case study
- 07-maternal-predicting-pregnancy-risk-levels.ipynb — Maternal health risk classification (large notebook — review in place)

Note: The notebooks in `notebooks/` are cleaned placeholder copies (outputs removed). Please review and replace with the cleaned content where necessary.

## Contributing

Please read CONTRIBUTING.md for guidelines on notebooks (clear outputs, narrative cells) and code style.

## License

This project is licensed under the MIT License — see LICENSE for details.

## Contact

Author: TheMishraAshwani      
