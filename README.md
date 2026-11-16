# Hospital Demand Forecasting — Pune

**Synthetic demonstration only.** No official dataset was supplied. All records and results are fictional and must not be described as real patient data.

## Contents
- `Hospital_Demand_Forecasting.ipynb`: reproducible notebook.
- `Hospital_Demand_Forecasting_Report.docx`: report for portal upload.
- `data/synthetic_hospital_encounters_500k.csv`: 500,250 encounter rows (duplicates and missing values intentionally included).
- `outputs/weekly_hospital_demand.csv`: cleaned weekly panel.
- `outputs/model_backtest_results.csv`: segment-level 13-week holdout metrics.
- `outputs/13_week_forecast.csv`: 13-week forecast and approximate 80%/95% ranges.
- `outputs/weekly_planning_table.csv`: illustrative resource plan.
- `outputs/charts/`: visualisations.

## Run
Install: `pip install pandas numpy matplotlib scikit-learn statsmodels jupyter`
Open the notebook from this project folder and run all cells. Python 3.10+ recommended.

## Method
Weekly visits are forecast by hospital and service line using Seasonal Naive, ETS and Random Forest lag features. The last 13 weeks form a single chronological holdout; MAPE excludes zero actuals; bias = forecast - actual. Intervals are approximate residual-based ranges.

## Planning assumptions
25 OPD visits per staff slot/week; 35 emergency visits per staff slot/week; 2.2 inpatient bed-days per inpatient encounter; follow-up rates 35% OPD and 68% inpatient, with 90% call completion. These are illustrative only, not clinical standards.

## Submission
Upload the DOCX report. The portal says a GitHub URL is compulsory for technical/software projects: create a repository, upload this project, then paste its actual URL. Do not enter a made-up URL.