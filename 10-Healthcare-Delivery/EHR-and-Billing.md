# Healthcare Delivery: EHR, Billing & Revenue Cycle

## Simple explanation
The hospital side of the industry: record care (EHR), bill for it (revenue cycle), and measure quality.

## EHR (Electronic Health Record)
Vendors: **Epic** (largest US), Oracle Health (Cerner), Meditech, athenahealth, eClinicalWorks.
Modules: registration/ADT, orders (CPOE), clinical notes, meds (eMAR), labs, radiology, scheduling, billing.
Epic data: Clarity (relational reporting DB), Caboodle (warehouse), Chronicles (operational DB). Data engineers extract from Clarity into warehouses/OMOP.
Data issues: copy-paste notes, structured vs free text, local codes, incomplete.

## Revenue cycle (RCM)
Scheduling → registration & eligibility check → charge capture → medical coding (ICD-10 + CPT) → claim submission (837) → payer adjudication → payment posting (835) → denial management → patient billing.
Metrics: days in A/R, clean claim rate, denial rate, first-pass resolution, cost to collect.
Payment models: fee-for-service, DRG (inpatient), capitation, bundled, ACOs, value-based.

## Quality & population health
HEDIS, CMS Star ratings, readmission penalties (HRRP), risk adjustment (HCC), SDOH data, care gaps.

## Digital health landscape
Telehealth, remote patient monitoring, digital therapeutics (SaMD – software as medical device, FDA regulated), patient portals, AI scribes, clinical decision support, **interoperability rules (ONC / TEFCA / Cures Act information blocking)**, **prior auth automation (CMS-0057)**.

## Devices
Classes I–III, 510(k)/PMA/De Novo, IEC 62304 software lifecycle, ISO 13485 QMS, UDI, post-market surveillance (MAUDE). EU MDR.

## Resources
- HealthIT.gov: https://www.healthit.gov
- AHA/CMS HCUP datasets: https://hcup-us.ahrq.gov
- Epic open API: https://fhir.epic.com
- AMIA: https://amia.org
- Related: [[06-Analytics/Claims-Analytics]], [[04-Data-Standards/HL7-FHIR]]
