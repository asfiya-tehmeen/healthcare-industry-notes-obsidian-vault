# Project 1: GxP-style Clinical Data Pipeline (EDC → SDTM → ADaM-lite)

## Goal
Show you can build a traceable, validated, automated pipeline with compliance controls.

## Data
CDISC pilot data (https://github.com/phuse-org/phuse-scripts) or generate fake EDC CSVs with Faker; or `pharmaversesdtm`.

## Steps
1. **Repo setup**: Git, README, folders (`raw/ staging/ sdtm/ adam/ tests/ docs/`).
2. **Ingest**: Python script reads CSV extracts; compute SHA-256, log filename, size, hash, user, timestamp to `ingest_log` (append-only).
3. **Raw validation**: schema + range checks (Great Expectations/pandera).
4. **SDTM build**: DM, AE, LB, VS, EX. ISO 8601 dates, controlled terminology maps, `USUBJID`.
5. **Conformance checks**: custom Python rules (required vars, no future dates, AE end ≥ start) + run Pinnacle 21 Community.
6. **ADaM**: ADSL + ADAE (flags, treatment-emergent logic, age groups).
7. **Reconcile**: row counts source→SDTM, subject counts match.
8. **Orchestrate**: Airflow or Prefect DAG; idempotent re-runs.
9. **Audit trail**: table capturing every transformation run (code git SHA, params).
10. **Validation pack**: URS (10 reqs), RTM, pytest results, Validation Summary Report (markdown/PDF).
11. **Dashboard**: AE incidence by arm in Power BI/Streamlit.

## Deliverables
GitHub repo, architecture diagram, validation docs, 2-min demo video, LinkedIn write-up.

## Skills shown
Python/SQL, CDISC, data quality, compliance thinking, documentation.
Related: [[04-Data-Standards/CDISC-SDTM-ADaM]], [[05-Data-Engineering/Pipeline-Architecture]]
