README - Data Cleaning & Imputation (Canada startups dataset)

Files included:
 - Canada_cleaned.csv (final working dataset with 31 columns and imputed values)
 - Column_Imputation_Notes.pdf (this document: column-wise notes & explanations)

Dataset source:
 - Provided by hackathon organizers (country-wise startup CSVs).

Key challenges:
 - Very high missingness in multiple columns (up to ~99%).
 - Mixed data types (numbers stored as strings with commas or % signs).
 - Some features are IPO-specific requiring filtered models (e.g., Valuation at IPO).

Approach (short):
 1) Profile missing values and unique categories for all columns.
 2) Standardize formats: remove commas, convert percentages, parse dates.
 3) Use simple statistics (mode/median/grouped median) for low-missing columns.
 4) Use ML-based imputations (RandomForest/LightGBM) for high-missing columns where relationships exist.
 5) Use IPO-only models for IPO-specific fields.
 6) Iteratively impute from low-missing to high-missing columns so that earlier imputations can serve as predictors.

Tools & libraries:
 - Python, pandas, NumPy, scikit-learn, LightGBM (optional), ReportLab (PDF generation).

How to reproduce:
 - Run the provided preprocessing notebook/script in order. Main steps:
    1) Load original Canada.csv
    2) Profile missingness and inspect unique categories
    3) Clean numeric and date formats
    4) Impute columns using the documented sequence (low->high missing)
    5) Save Canada_cleaned.csv

Contact:
 - If you need the runnable notebook or model artifacts for reproducibility, request them and they will be included.