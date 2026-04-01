# mobile-game-user-analytics

This repository contains an exploratory analytics project built on an anonymized mobile game dataset. The analysis is notebook-based and follows a simple flow: data quality audit, user base and engagement, retention, and monetization.

## Dataset

Source: Kaggle  
Link: https://www.kaggle.com/datasets/mobilegameguru/anonymzed-mobile-game-user-data

The raw CSV files are not tracked in this repository. Download the dataset from Kaggle and place the files below inside `csv_files/`:

- `users.csv`
- `user_sessions.csv`
- `user_purchases.csv`

## Project Scope

The notebooks focus on:

- data quality checks before analysis
- user base composition and engagement behavior
- cohort-based retention analysis
- monetization KPIs and cohort-based D30 ARPU

Important context:

- the session and purchase event windows are limited to the dataset extract
- monetization metrics use purchase rows matched to registered users in `users`
- some comments in the notebooks explicitly call out sample bias and observation-window limits

## Repository Structure

```text
.
|-- 01_data_quality_audit.ipynb
|-- 02_user_base_and_engagement.ipynb
|-- 03_retention_cohort_analysis.ipynb
|-- 04_monetization_analysis.ipynb
|-- csv_files/
|-- requirements.txt
`-- .gitignore
```

Notebook order:

1. `01_data_quality_audit.ipynb`
2. `02_user_base_and_engagement.ipynb`
3. `03_retention_cohort_analysis.ipynb`
4. `04_monetization_analysis.ipynb`

## Environment

Tested with:

- Python `3.10.0`
- `numpy 2.2.6`
- `pandas 2.3.3`
- `matplotlib 3.10.8`
- `IPython 8.39.0`

Install the required packages:

```bash
pip install -r requirements.txt
```

## How to Run

1. Create and activate a virtual environment.
2. Install dependencies with `pip install -r requirements.txt`.
3. Download the Kaggle dataset and place the CSV files in `csv_files/`.
4. Open Jupyter Lab or Jupyter Notebook in this folder.
5. Run the notebooks in numeric order.

Example:

```bash
jupyter lab
```

## Notebook Summary

### 1. Data Quality Audit

Checks schema, missing values, duplicates, key logic, date consistency, and some extreme session and purchase anomalies.

### 2. User Base and Engagement

Looks at user mix, new-user trend, session behavior, daily activity, country and OS splits, and a user-level engagement table.

### 3. Retention and Cohort Analysis

Builds user-day activity, calculates exact-day retention, compares weekly cohorts, and studies retention by OS, country, and first-week engagement.

### 4. Monetization Analysis

Covers revenue KPIs, payer conversion, ARPU, ARPPU, ARPDAU, purchase frequency, first purchase timing, and cohort-based D30 ARPU.

## Notes and Limitations

- This is an exploratory analysis project, not a production data pipeline.
- Some metrics are intentionally presented with caveats because the dataset is a selected extract, not a full product warehouse.
- Raw ARPU and payer conversion in the monetization notebook should be read within the notebook scope, not as universal game benchmarks.
- D30 ARPU is included to provide a cleaner cohort-based monetization view.
