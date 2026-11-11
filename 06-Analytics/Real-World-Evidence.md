# Real-World Data & Evidence (RWD / RWE)

## Simple explanation
Trials show what happens in ideal conditions. **RWE** shows what happens in everyday practice, using data collected during routine care (EHR, claims, registries, wearables).

## Uses
- Regulatory: label expansions, external control arms, post-marketing safety (FDA Sentinel).
- HEOR / market access: prove value to payers.
- Commercial: patient journey, treatment patterns, unmet need.
- Clinical development: feasibility, site selection, patient finding.

## Study designs
- **Cohort** (exposed vs unexposed → outcome), **Case-control**, **Self-controlled case series**, **New-user active-comparator design**.
- Key concepts: index date, washout/look-back, follow-up, censoring, **confounding**, **bias** (selection, immortal time), **propensity scores**, **Kaplan-Meier**, **Cox regression**, incidence rate, hazard ratio.

## Data pipeline
Raw EHR/claims → harmonize (OMOP) → define cohort (inclusion/exclusion, phenotype algorithm) → covariates → analysis (R/Python) → report. Reproducibility + audit trail matter if used for regulatory decisions.

## Sample cohort SQL idea
Patients with first-ever diagnosis (index) after 365 days of enrolment (washout), then outcome within 180 days:
```sql
WITH first_dx AS (
  SELECT person_id, MIN(condition_start_date) idx
  FROM condition_occurrence WHERE condition_concept_id IN (/*concept set*/) GROUP BY person_id)
SELECT f.person_id, f.idx
FROM first_dx f JOIN observation_period op ON op.person_id=f.person_id
 AND f.idx BETWEEN op.observation_period_start_date + 365 AND op.observation_period_end_date;
```

## Guidance
FDA RWE framework & guidances: https://www.fda.gov/science-research/science-and-research-special-topics/real-world-evidence

## Resources
- Book of OHDSI: https://ohdsi.github.io/TheBookOfOhdsi/
- Sentinel Initiative: https://www.sentinelinitiative.org
- ISPOR (HEOR): https://www.ispor.org
- Course: "Real-World Evidence" – Coursera (search) ; Harvard "Causal Diagrams" (edX) – [[13-Resources/Free-Courses]]
- Book: *Causal Inference: What If* (free) – https://miguelhernan.org/whatifbook
- Related: [[Claims-Analytics]], [[04-Data-Standards/OMOP-CDM]]
