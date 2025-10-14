# Multivariate Linear Regression — Practical Lab 2

This repository contains a Jupyter Notebook, `Multivariate_linear_regression.ipynb`, implementing a practical lab on multivariate linear regression, non-parametric models, and cross-validation using the Diabetes dataset from scikit-learn.

Contents
- `Multivariate_linear_regression.ipynb` — A step-by-step notebook covering data loading, exploratory data analysis, univariate polynomial regression (BMI), multivariate polynomial regression, decision trees, k-nearest neighbors, and a binary framing with logistic regression.
- `requirements.txt` — Python package dependencies used to run the notebook.

Summary of the notebook
- Part 1: Data loading, EDA, train/validation/test splits (75% train, ~10% val, 15% test). Uses the scikit-learn Diabetes dataset.
- Part 2: Univariate polynomial regression using BMI as the single predictor. Fits degrees 0–5, selects the best model by validation R², refits on train+validation and evaluates on test. Includes plotting and equation display.
- Part 3: Multivariate models including:
  - Multivariate polynomial regression (degree 2 and 3), with Ridge regularization for degree 3.
  - Decision Tree regression (varying max_depth).
  - k-Nearest Neighbors regression (k=3 and k=7) with scaling in a pipeline.
  - Logistic regression after binarizing the target at the 60th percentile (train+val threshold).

Key utilities and metrics
- Custom helpers: MAPE (mean absolute percentage error), a small summarizer for R²/MAE/MAPE, and a console-friendly table printer.
- Metrics used: R², MAE, MAPE for regression; accuracy, F1, ROC-AUC and confusion matrix for classification.

Quickstart (Windows / PowerShell)
1. Create and activate a virtual environment (recommended):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2. Install dependencies:

```powershell
pip install -r requirements.txt
```

3. Launch Jupyter and open the notebook:

```powershell
jupyter notebook Multivariate_linear_regression.ipynb
```

Notes and findings
- The notebook shows that BMI is a strong univariate predictor but is insufficient to capture all variance. Multivariate polynomial models can improve validation performance but risk overfitting (especially high-degree polynomials).
- Decision Trees and kNN provide alternative non-linear approaches; kNN requires careful scaling and suffers with high-dimensional data.
- Logistic regression (after binarizing the continuous target) demonstrates reasonable classification performance (accuracy/F1/ROC-AUC reported in the notebook).

Recommendations / next steps
- Add cross-validation (k-fold) for more reliable hyperparameter selection.
- Compare regularization strengths (e.g., Ridge/ElasticNet) more thoroughly for polynomial models.
- Add model serialization (joblib) and a small script to load a trained model and make predictions.

License
- This repository is provided for educational purposes.

Author
- Notebook author: Albright Maduka
# Multivariate_linear_regression