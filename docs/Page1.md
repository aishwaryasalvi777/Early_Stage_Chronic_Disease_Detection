# Page 1 : CSV Explainations

# What each file contains and how to use it

## patients.csv
Contains one row per patient (100,000 patients), with demographics, vitals, lifestyle, comorbidity flags, and Charlson score.

Use it for:
- Baseline/static features
- Cohort definition (age, condition flags)
- Risk stratification at patient level

## diagnoses.csv
Contains longitudinal diagnosis encounters (274,592 data rows), including visit date/type, primary and secondary diagnoses, ICD-10, specialty.

Use it for:
- Disease history and progression features
- Visit frequency and utilization patterns
- Label creation for onset prediction (for example, first CKD diagnosis date)

## lab_results.csv
Contains high-volume longitudinal labs (2,827,722 data rows), test values, normal ranges, abnormal flags.

Use it for:
- Biomarker trend features (rolling mean, slope, last abnormal date)
- Early warning signals before diagnosis/outcome
- Time-series inputs for sequence models

## medications.csv
Contains treatment records (364,174 data rows), dose/frequency/indication/start date/adherence. About 94,067 patients have medication records.

Use it for:
- Treatment exposure features
- Adherence-based risk signals
- Pre/post treatment effect analysis on labs/outcomes

## outcomes.csv
Contains hospitalization outcomes (11,001 patients), including LOS, ICU, death, readmission, charges.

Use it for:
- Supervised targets like 30-day readmission, ICU admission, mortality
- Cost prediction
- Severity modeling

## Quick profile highlights for planning
- Join key across all files: patient_id
- Timeline mostly spans 2018-01-01 to 2024-12-30
- Outcomes are much smaller than patient base, so only a subset has admissions
- Readmission target is reasonably usable: 1,643 positive vs 9,358 negative
- ICU and death are rare events (class imbalance handling needed)

## Best way to use these together in one project
A strong starter project is: Early chronic disease risk plus hospitalization risk.

1. Build patient timeline index from diagnoses/labs/meds by date.
2. Create features up to a prediction cutoff date only (avoid leakage).
3. Train model A: predict new CKD (or diabetes/hypertension) onset in next 6-12 months.
4. Train model B: for admitted patients, predict readmitted_30d using prior history.
5. Add explainability (feature importance, SHAP) and subgroup analysis.
