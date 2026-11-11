# Project 2: FAERS Safety Signal Detection

## Goal
Analyze FDA adverse event reports to detect disproportionate drug–event pairs.

## Data
FAERS quarterly ASCII files (DEMO, DRUG, REAC, OUTC, INDI, THER) – see [[13-Resources/Datasets]]. Or openFDA API.

## Steps
1. Load into DuckDB/Postgres; document schema.
2. Clean: deduplicate cases (keep latest `caseversion` per `caseid`), standardize drug names (map to RxNorm/ingredient via RxNav API), keep PRIMARY SUSPECT (`role_cod='PS'`).
3. Build 2x2 counts per drug-event (MedDRA PT).
4. Compute PRR, ROR with 95% CI; apply thresholds (PRR ≥ 2, χ² ≥ 4, n ≥ 3).
5. Validate on known signals (e.g. fluoroquinolones–tendon rupture).
6. Visualize: volcano-style plot, top events per drug, time trend.
7. Build a Streamlit app: pick drug → see top signals.
8. Document limitations (under-reporting, stimulated reporting, confounding, no denominator).
9. Add tests, README, data lineage.

## Stretch
Add EBGM; add automated quarterly refresh with Airflow; add LLM-free narrative template for each signal.

## Skills shown
SQL, stats, domain knowledge (PV), reproducibility.
Related: [[08-Pharmacovigilance/Pharmacovigilance-Basics]]
