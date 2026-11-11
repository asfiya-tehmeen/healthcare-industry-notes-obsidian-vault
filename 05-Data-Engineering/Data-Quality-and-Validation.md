# Data Quality, Cleaning & Reconciliation

## Simple explanation
"Garbage in, garbage out" — and in pharma, garbage can mean a rejected submission or patient harm. Data quality (DQ) = systematic checks that data is fit for purpose.

## DQ dimensions
Completeness · Validity (format/range/code list) · Uniqueness · Consistency (cross-field/cross-table) · Accuracy · Timeliness · Integrity (foreign keys) · Plausibility (clinically sensible).

## Typical clinical checks (edit checks / data listings)
- AE end date before start date
- Visit date after death date
- Age outside 18–75 inclusion range
- Lab value unit inconsistent (mg/dL vs mmol/L)
- Dose given when subject withdrawn
- Duplicate subject IDs across sites
- Missing mandatory forms
- Protocol deviation flags
Output = **queries** sent back to site, tracked to closure → "clean" → **database lock**.

## Check patterns in SQL
```sql
-- 1. Logical date errors
SELECT usubjid, aeterm, aestdtc, aeendtc FROM ae WHERE aeendtc < aestdtc;
-- 2. Duplicates
SELECT usubjid, aeterm, aestdtc, COUNT(*) FROM ae GROUP BY 1,2,3 HAVING COUNT(*)>1;
-- 3. Orphans (referential integrity)
SELECT a.usubjid FROM ae a LEFT JOIN dm d USING (usubjid) WHERE d.usubjid IS NULL;
-- 4. Range
SELECT * FROM lb WHERE lbtestcd='ALT' AND lbstresn NOT BETWEEN 0 AND 2000;
```

## Tools
- **Great Expectations**, **Soda**, **dbt tests**, **Deequ**, **Pandera**
- OHDSI **DQD** (Kahn framework)
- Pinnacle 21 for CDISC conformance
- Risk-based monitoring (RBM) / central statistical monitoring

## Reconciliation (very pharma!)
- **SAE reconciliation**: safety DB vs clinical DB must match.
- **External data reconciliation**: lab vendor file vs EDC.
- **Source-to-target counts, checksums, totals**.
- **Medical coding review** (MedDRA/WHODrug).

## Principle: don't "fix" silently
Corrections go through documented queries + audit trail, never ad-hoc UPDATE in prod.

## Great Expectations example
```python
import great_expectations as gx
v = gx.get_context().sources.pandas_default.read_csv("ae.csv")
v.expect_column_values_to_not_be_null("USUBJID")
v.expect_column_values_to_be_in_set("AESEV", ["MILD","MODERATE","SEVERE"])
v.expect_column_pair_values_A_to_be_greater_than_B("AEENDTC","AESTDTC", or_equal=True)
```

## Resources
- Great Expectations: https://docs.greatexpectations.io
- Soda: https://docs.soda.io
- DQD: https://github.com/OHDSI/DataQualityDashboard
- SCDM (Society for Clinical Data Management) GCDMP: https://scdm.org
- Related: [[Pipeline-Architecture]]
