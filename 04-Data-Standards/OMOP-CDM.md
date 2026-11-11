# OMOP Common Data Model & OHDSI

## Simple explanation
Every hospital/insurer stores data differently, making multi-database studies painful. **OMOP CDM** (Observational Medical Outcomes Partnership) converts everything to one standard schema + vocabulary, so one analysis script runs on any database worldwide. OHDSI is the open community behind it.

## Core tables
- `PERSON`, `OBSERVATION_PERIOD`, `VISIT_OCCURRENCE`
- `CONDITION_OCCURRENCE`, `DRUG_EXPOSURE`, `PROCEDURE_OCCURRENCE`, `MEASUREMENT`, `OBSERVATION`, `DEVICE_EXPOSURE`, `DEATH`
- Derived: `CONDITION_ERA`, `DRUG_ERA`, `COHORT`
- Vocab: `CONCEPT`, `CONCEPT_RELATIONSHIP`, `CONCEPT_ANCESTOR`, `VOCABULARY`
- Each raw code → `*_source_value` + `*_source_concept_id`, mapped to `*_concept_id` (standard concept).

## ETL pattern
Source → profile with **WhiteRabbit** → map with **Rabbit-in-a-Hat** → write ETL (SQL/dbt/Python) → run **Data Quality Dashboard (DQD)** & **Achilles** characterization.

## Why it's valued
Regulators (FDA Sentinel, EMA DARWIN EU) and pharma RWE teams use OMOP for safety and effectiveness studies at scale.

## Sample query: patients with type 2 diabetes who started metformin
```sql
SELECT DISTINCT c.person_id
FROM condition_occurrence c
JOIN concept_ancestor ca ON ca.descendant_concept_id = c.condition_concept_id
JOIN drug_exposure d ON d.person_id = c.person_id
JOIN concept_ancestor da ON da.descendant_concept_id = d.drug_concept_id
WHERE ca.ancestor_concept_id = 201826           -- Type 2 diabetes mellitus
  AND da.ancestor_concept_id = 1503297          -- Metformin
  AND d.drug_exposure_start_date >= c.condition_start_date;
```

## Resources
- The Book of OHDSI (free): https://ohdsi.github.io/TheBookOfOhdsi/
- CDM docs: https://ohdsi.github.io/CommonDataModel/
- OHDSI tools: https://www.ohdsi.org/software-tools/
- EHDEN Academy free courses: https://academy.ehden.eu
- Eunomia sample dataset (R): https://github.com/OHDSI/Eunomia
- Related: [[06-Analytics/Real-World-Evidence]], [[Medical-Coding-Systems]]
