# Project 3: FHIR → OMOP ETL + Part 11 Audit Trail Monitor

## Part A: FHIR → OMOP
1. Generate 1,000 Synthea patients as FHIR bundles (or CSV).
2. Flatten Patient, Condition, MedicationRequest, Observation, Encounter with Python/DuckDB.
3. Download OMOP vocabularies from Athena (https://athena.ohdsi.org); map SNOMED/RxNorm/LOINC to standard concepts.
4. Load `person`, `visit_occurrence`, `condition_occurrence`, `drug_exposure`, `measurement`.
5. Run OHDSI Data Quality Dashboard; report pass rate & fix failures.
6. Run a cohort question: "new users of metformin, 1-year follow-up outcomes".

## Part B: Audit Trail Monitor
1. Add triggers/CDC on key tables writing to append-only `audit_trail` (user, time UTC, old/new, reason).
2. Build SQL review reports: after-hours changes, mass edits, changes without reason, repeated edits to same field, shared IP/user.
3. Alert via email/Slack; weekly PDF review report with reviewer e-signature (simulated: name + meaning + timestamp).
4. Write mini SOP: "Periodic Audit Trail Review" + validation test cases.

## Deliverables
Repo, ERD, ETL docs, DQ report, SOP, short blog post.
Related: [[04-Data-Standards/OMOP-CDM]], [[04-Data-Standards/HL7-FHIR]], [[03-Regulatory-Compliance/21-CFR-Part-11]]

## Extra project ideas
- Commercial: HCP segmentation on Medicare Part D data + Open Payments join.
- Quality: SPC dashboard for batch data with Western Electric rules.
- Automation: Daily ClinicalTrials.gov monitor → Slack digest.
- NLP: extract inclusion/exclusion criteria from trial records into structured JSON, with evaluation set.
