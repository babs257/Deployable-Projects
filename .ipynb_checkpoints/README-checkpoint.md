ENERGY DEAFULT RISK PREDICTION
README

Project Overview
This project predicts default risk (likelihood of customers defaulting on payments) using energy consumption, socioeconomic indicators, payment behavior, and area-level features. The dataset is aggregated at the MSOA (Middle Layer Super Output Area) and region level, with observations spanning yearly and quarterly time periods.

Dataset Description
The main dataset includes:

Geographic identifiers:

local_authority_code, msoa_code, region_code

Energy data:

total_consumption, annual_bill_estimate, consumption_yoy

Payment behavior:

credit_(%), direct_debit_(%), prepayment_%, dominant_payment_mode, prepay_volatility

Socioeconomic metrics:

total_annual_income, income_bill_ratio, cost_burden, relative_cost_burden

Time variables:

year, quarter, month_num, season, year_quarter

Statistical bounds:

upper_confidence_limit_(£), lower_confidence_limit_(£), confidence_interval_(£)

Engineered features:

median_total_ratio, prepay_volatility

Target label:

default_risk_label (binary or categorical risk measure)

Unnecessary descriptive columns (e.g., names of areas) have been removed to focus on predictive modeling.

Project Workflow
Data Ingestion:

Load the source data into a pandas DataFrame.

Preprocessing:

Clean missing or inconsistent values.

Standardize column types/formats.

Feature Engineering:

Create new features from temporal, demographic, consumption, and payment data.

Aggregate and transform where necessary.

Column Selection:

Split columns into numerical and categorical sets.

Remove unneeded identifiers and descriptive fields.

Encoding & Scaling:

Encode categorical variables appropriately (e.g., one-hot encoding).

Scale numerical features if required.

Modeling:

Train machine learning models (e.g., Random Forest, XGBoost) to predict default risk.

Assess feature importance and model accuracy.

Evaluation & Iteration:

Validate models using appropriate metrics.

Refine feature set as needed based on results.

How to Run
Ensure all dependencies are installed (Python, pandas, Oracle Accelerated Data Science (ADS), scikit-learn, etc.).

Prepare your dataset (df_ready).

Execute preprocessing and feature engineering steps described in notebook/scripts.

Run model training and evaluation.

Review outputs: predicted risks and feature importance.

Key Files
notebook.ipynb — Jupyter notebook with all data processing and modeling code.

data/ — Data folder (not included, must be sourced separately).

requirements.txt — List of required Python packages.

src/ — Helper scripts/functions for data cleaning and feature engineering.

Contact & Support
For help or questions on the project structure, feature engineering, or modeling steps, please contact the project maintainer or raise an issue on the repository.

Notes
All features engineered adhere to best practices to avoid data leakage.

Further external data (e.g., fuel poverty, unemployment rates, weather anomalies) can be merged for model enhancement.

The workflow is easily extendable for other area-level risk modeling tasks.
