# Claims Analytics

## Simple explanation
A claim is a bill: "this patient got these diagnoses/procedures/drugs, costing X." Claims let you see utilization, cost, adherence and patient journeys for millions of people.

## Key tables
- **Enrollment/eligibility** (member months) · **Medical claims** (header + lines: ICD-10, CPT/HCPCS, revenue code, place of service, allowed/paid amounts) · **Pharmacy claims** (NDC, days supply, quantity, fill date) · **Provider** (NPI, specialty).

## Core metrics
- **PMPM** (per member per month) cost = total cost ÷ member months
- **Incidence / prevalence**
- **Medication adherence**: PDC (proportion of days covered) ≥ 80%, MPR
- **Persistence**: days until gap > 30/60 days
- **Line of therapy** sequencing
- **Readmission rate** (30-day), ED visits per 1,000
- **Comorbidity scores**: Charlson, Elixhauser
- **Risk adjustment**: HCC (Medicare Advantage)
- **Switching, discontinuation, time to treatment**

## SQL patterns you must know
```sql
-- PDC for 365 days after first fill (simplified)
WITH fills AS (
  SELECT patient_id, fill_date, days_supply,
         fill_date + days_supply - 1 AS end_date
  FROM rx_claims WHERE drug_class = 'STATIN'),
first_fill AS (SELECT patient_id, MIN(fill_date) idx FROM fills GROUP BY 1)
-- then generate calendar days, mark covered days, divide by 365
SELECT 1;

-- Gaps between fills using window function
SELECT patient_id, fill_date,
  fill_date - LAG(fill_date + days_supply) OVER (PARTITION BY patient_id ORDER BY fill_date) AS gap_days
FROM rx_claims;
```
Practice: window functions (LAG/LEAD, ROW_NUMBER, SUM OVER), date arithmetic, gaps-and-islands, cohort retention. See [[12-Practice-Problems/SQL-Problems]].

## Caveats
Claims have no lab values/outcomes; lag of weeks; fills ≠ ingestion; coding for reimbursement; patients switching insurers vanish.

## Data sources
CMS Part D prescribers, Medicare Provider Utilization, **CMS DE-SynPUF** synthetic claims, commercial (Optum, MarketScan, IQVIA PharMetrics), Medicaid T-MSIS.
- https://data.cms.gov
- https://www.cms.gov/data-research/statistics-trends-and-reports/medicare-claims-synthetic-public-use-files

## Resources
- Mode SQL tutorials: https://mode.com/sql-tutorial
- HEDIS measures overview (NCQA): https://www.ncqa.org/hedis/
- Related: [[Real-World-Evidence]], [[10-Healthcare-Delivery/EHR-and-Billing]]
