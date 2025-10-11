# Stat_Capstone — E‑Commerce Sales Analytics (Capstone Project)

One-line summary
This repository contains a Jupyter Notebook and synthetic retail dataset used for a statistics-for-data-analytics capstone project. The notebook walks through data cleaning, exploratory analysis, statistical tests, regression modeling, and time-series forecasting on e-commerce transaction data.

Contents
- `questionFile.ipynb` — Main Jupyter Notebook that implements the full analysis and visualizations described in the project brief.
- `synthetic_retail_data.csv` — Synthetic e-commerce transactions dataset used by the notebook.
- `LICENSE` — Project license.

Project overview
The goal is to reproduce an end-to-end analytics workflow a data analyst would perform on e-commerce transaction data: cleaning and preprocessing, descriptive statistics and visualizations, probability estimates and hypothesis tests, regression modeling to explain order value, and time-series analysis for revenue forecasting. The notebook is written in Python and uses common data-science libraries.

Dataset
The dataset contains approximately 9,500 transactions (2023) with fields such as:
- `InvoiceNo`, `CustomerID`, `Date`, `ProductCategory`, `Quantity`, `UnitPrice`, `DiscountApplied`, `ReviewRating`, `IsFirstPurchase`, `MarketingChannel`, `Country`, `TimeOnSite`, `ShippingCost`, `ItemsInCart`, `PreviousSpending`, `BrowsingSessions`, `TotalAmount`.

Key analyses implemented in `questionFile.ipynb`
- Data import and missing-value handling (ReviewRating, TimeOnSite, MarketingChannel, etc.)
- Outlier detection and capping using IQR for numeric features
- Descriptive statistics (mean, median, mode, variance, IQR) and distributions (histograms, boxplots)
- Pivot summaries: revenue by product category, country, and average order value by marketing channel
- Probability estimates (e.g., probability of 5-star reviews, probability of large order values)
- Hypothesis tests: two-sample t-test (first-time vs returning customers), ANOVA (spending across countries), chi-square (marketing channel vs review rating)
- 95% confidence intervals for average daily revenue and average review rating
- Correlation matrix and multiple linear regression to predict `TotalAmount` (including standardized coefficient interpretation)
- Time-series construction (daily/monthly revenue), moving averages, and Holt-Winters exponential smoothing forecasting

Dependencies
The notebook uses the following Python packages (tested with Python 3.10+). Install them with pip if needed:

- pandas
- numpy
- matplotlib
- seaborn
- scipy
- statsmodels
- scikit-learn

Quick setup
1. Create and activate a virtual environment (optional but recommended). On Windows PowerShell:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2. Install dependencies:

```powershell
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn
```

Running the notebook
1. Start Jupyter Notebook or JupyterLab from this repository root:

```powershell
jupyter notebook
```

2. Open `questionFile.ipynb` and run cells in order. The notebook reads `synthetic_retail_data.csv` from the same directory. If the CSV is not present, move it into the repository root.

Notes and suggestions
- The notebook contains data-cleaning choices (mode or mean imputation, IQR capping). If you need stricter or alternative treatments (drop rows, winsorization, or model-based imputation), modify the corresponding cells.
- For reproducibility, consider exporting a requirements.txt with exact package versions via `pip freeze > requirements.txt` and pinning versions.
- Long-running forecasting or large-plot cells may be skipped during quick checks.

Contact and license
If you need help running the notebook or want changes, open an issue or contact the project owner. This repository includes a `LICENSE` file — please review it for reuse and redistribution terms.

Status
Notebook and dataset present. See `questionFile.ipynb` for the full analysis and code comments.
