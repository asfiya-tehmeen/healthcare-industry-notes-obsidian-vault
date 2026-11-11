# Interview Questions & Model Answers

## Industry basics
**Q: Explain how a drug gets to market.** Discovery → preclinical → IND → Phases I–III → NDA/BLA → review → approval → Phase IV/PV. Mention ~10–15 yrs, high attrition, GxP at each stage.
**Q: Difference between NDA, ANDA, BLA?** NDA new small molecule; ANDA generic (bioequivalence); BLA biologics.
**Q: What is a CRO and why used?** Outsourced trial/service provider; flexibility, expertise, speed.

## Compliance
**Q: What is GxP?** Good practice regulations ensuring quality & data reliability across lab, clinical, manufacturing, distribution, vigilance.
**Q: Explain ALCOA+.** (see [[03-Regulatory-Compliance/Data-Integrity-ALCOA]]) – give example violations.
**Q: What does Part 11 require?** Validation, audit trails, access control, e-signatures with meaning, record retention.
**Q: How do you validate a data pipeline?** Requirements → risk assessment → tests (unit, integration, reconciliation) with traceability → approvals → change control → monitoring/periodic review.
**Q: CSV vs CSA?** CSA = risk-based, critical thinking, less documentation burden for low-risk.
**Q: What is a deviation/CAPA?** Unplanned departure; CAPA fixes root cause + prevents recurrence + effectiveness check.
**Q: HIPAA vs GDPR?** HIPAA: US, covered entities, PHI. GDPR: EU, any personal data, stronger rights, higher fines.
**Q: How de-identify data?** Safe Harbor (remove 18 identifiers) or Expert Determination; plus tokenization, date shifting.

## Data standards
**Q: SDTM vs ADaM?** SDTM = standardized tabulation of collected data; ADaM = derived analysis datasets traceable to SDTM.
**Q: What's USUBJID?** Unique subject identifier across a submission.
**Q: What's FHIR and how differs from HL7 v2?** REST/JSON resources vs pipe-delimited messages.
**Q: Why OMOP?** Standardize heterogeneous data for portable analytics.
**Q: What are ICD, SNOMED, LOINC?** Diagnoses (billing), clinical concepts, lab tests.

## Data engineering / SQL
**Q: Design a pipeline ingesting weekly lab vendor files into EDC-aligned datasets.** Landing zone, checksum, schema validation, unit conversion with LOINC mapping, reconciliation vs EDC, quarantine bad records, queries to vendor, immutable raw, audit logs, alerts.
**Q: Find patients with 3 consecutive missed visits.** Window functions/gaps-and-islands.
**Q: How handle late-arriving data / corrections?** Bi-temporal modeling, versioned records, SCD2, never overwrite.
**Q: Idempotency?** Rerun yields same result — use upserts/merge, deterministic keys.
**Q: How ensure data integrity during migration?** counts, hash totals, sampled comparisons, audit trail migration, sign-off.

## Behavioral (STAR format)
- Time you found a data error → how reported and fixed.
- Time you balanced speed vs compliance.
- Explaining technical issue to non-technical (QA, physician).
- Handling ambiguous requirements.

## Questions to ask them
"What does your validation approach look like (CSV vs CSA)?" "What stack: Snowflake/Databricks? SAS/R?" "How are regulatory inspections handled for data systems?"

Related: [[Career-Paths]], [[12-Practice-Problems/Compliance-Case-Exercises]]
