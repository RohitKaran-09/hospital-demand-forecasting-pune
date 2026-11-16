# Hospital Demand Forecasting — Report

> Text extracted from the generated Word report. The formatted DOCX is included in the downloadable project ZIP.

<PARSED TEXT FOR PAGE: 1 / 3>              Hospital Demand Forecasting
                 Virtual R Data Analyst Internship | Pune Community Clinic Network

                SYNTHETIC DEMONSTRATION PROJECT — NOT REAL PATIENT DATA



Executive summary
This project demonstrates a complete hospital-demand forecasting workflow using a generated
dataset of 500,250 fictional encounter rows across four fictional Pune hospitals and three service
lines. After cleaning, encounters were aggregated to weekly demand. Seasonal Naive, ETS and
Random Forest lag-feature models were compared on a 13-week chronological holdout. Segment-
level forecasts, approximate uncertainty ranges and an illustrative operational planning table were
produced.



1. Data and preparation
The synthetic dataset spans 2024-01-01 to 2026-11-08. Fields include visit date, hospital, service line,
free-text diagnosis, age, admission flag, lab tests, billing amount and follow-up requirement. It
includes deliberate duplicate IDs and missing values. After deduplication and removal of records
missing date/hospital/service line, 499,500 rows remain. Missing age values were median-imputed.



2. Forecasting methodology
The target is weekly encounter count by hospital and service line. Three methods were evaluated:
Seasonal Naive (same week one year earlier), additive ETS (trend and annual seasonality), and
Random Forest with lag features. The final 13 weeks were held out. MAPE excludes zero-actual
weeks; bias is forecast minus actual. The lowest holdout MAPE method was selected for each
segment.<PARSED TEXT FOR PAGE: 2 / 3>3. Forecast and operational planning
The 13-week output contains 156 rows: 13 weeks × 4 hospitals × 3 service lines. Forecast outputs
include point estimates and approximate 80%/95% residual-based ranges. Planning outputs estimate
OPD staff slots, emergency staff slots, inpatient bed proxies and follow-up call capacity.




4. Model results
    Random Forest: mean segment holdout MAPE 6.55%.
    ETS: mean segment holdout MAPE 8.10%.
    Seasonal Naive: mean segment holdout MAPE 9.08%.

Use segment-level metrics when reviewing results; a network-wide average can hide poor
performance in individual services.



5. Limitations and recommendations
1.   All data are synthetic and cannot be represented as actual patient or hospital evidence.<PARSED TEXT FOR PAGE: 3 / 3>2.   The current comparison uses one 13-week holdout origin; add 4–6 expanding-window origins
     and report average/median metrics.
3.   No verified Diwali, Holi or other local holiday calendar is included. Add validated event flags
     before analysing holiday effects.
4.   Diagnosis text is simulated. Real free-text diagnoses require standardisation, clinical review and
     privacy safeguards.
5.   Prediction ranges use holdout residual standard deviation and normal multipliers; assess
     calibration and consider bootstrap/conformal intervals.
6.   Staffing and bed conversion factors are illustrative placeholders, not clinical standards. Obtain
     approval from hospital operations teams.



6. Deliverables
    Hospital_Demand_Forecasting.ipynb — reproducible analysis notebook
    data/synthetic_hospital_encounters_500k.csv — synthetic encounter data
    outputs/weekly_hospital_demand.csv — cleaned weekly panel
    outputs/model_backtest_results.csv — model metrics
    outputs/13_week_forecast.csv — 13-week forecast and ranges
    outputs/weekly_planning_table.csv — illustrative planning table
    outputs/charts/ — charts



Conclusion
This project demonstrates data cleaning, time-series aggregation, model comparison, forecasting and
operational translation. It must be rerun on authorised anonymised hospital data and validated
through fuller rolling backtests and approved planning assumptions before real-world use.