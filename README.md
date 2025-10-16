# Multivariate Linear Regression — Practical Lab 2

What this project is
- A reproducible notebook that demonstrates:
  - Exploratory data analysis on the Diabetes dataset
  - Univariate polynomial regression using BMI (degrees 0–5)
  - Multivariate polynomial regression (degree 2 and 3, with Ridge regularization)
  - Non‑parametric models: Decision Trees and k‑Nearest Neighbors
  - A binary framing of the regression target with Logistic Regression (threshold at 60th percentile)
  - Simple helper utilities (stabilized MAPE, table display, concise metric printing)

Files
- `Multivariate_linear_regression.ipynb` — The main notebook with code, plots and reflections.
- `requirements.txt` — Project dependencies (use to install the Python environment).

Dataset
- Uses the built-in `sklearn.datasets.load_diabetes` (standardized features). The notebook splits data into Train (75%), Validation (10%), and Test (15%).

Key results (from notebook experiments)
- Best univariate BMI model (selected by validation R²) produced moderate test performance (example values from the notebook):
  - Univariate TEST: R² ≈ 0.20, MAE ≈ 54.45, MAPE ≈ 47.6%
- Multivariate polynomial (degree=2) generalized better than degree=3 in validation and was the chosen multivariate model. On the test set it reported (notebook values): R² ≈ 0.37 (example reported: R² = 0.3743).
- Decision tree and kNN were evaluated; choice of tree depth and k mattered for bias/variance tradeoffs. kNN used scaling inside a pipeline (k=3 and k=7 were tried).
- Logistic regression (binarized target at 60th percentile) achieved good discriminative performance in the notebook example:
  - TEST: Accuracy ≈ 76.12%, F1 ≈ 65.22%, ROC-AUC ≈ 84.69% (see notebook for confusion matrix counts)

Quickstart (Windows PowerShell)
1) Create and activate a virtual environment:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2) Install dependencies:

```powershell
pip install -r requirements.txt
```

3) Start Jupyter and open the notebook:

```powershell
jupyter notebook Multivariate_linear_regression.ipynb
```

Running tips
- Run the notebook from top to bottom. Cells rely on previously defined variables (train/val/test splits, helper functions, fitted models).
- If you only want to re-run model evaluation sections, make sure the datasets and train/val/test splits are defined first (cells near Step 5).

Reproducibility
- A fixed random seed is used in the notebook (RNG_SEED = 42) for reproducible splits and model behaviour where applicable.

Suggested next steps
- Add k-fold cross-validation for hyperparameter tuning and more stable model selection.
- Add a small script that serializes the final chosen model (joblib) and provides a predict API.
- Trim `requirements.txt` to a minimal set used in the notebook if you want a lighter environment for deployment.

Acknowledgements & Author
- Notebook author: Albright Maduka
- Course: CSCN8010 — Foundations of ML Frameworks

