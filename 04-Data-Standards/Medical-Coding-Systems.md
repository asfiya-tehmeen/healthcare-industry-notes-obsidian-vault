# Medical Coding Systems & Terminologies

## Simple explanation
Doctors write "heart attack", "MI", "myocardial infarction". Computers need ONE code. Coding systems are the dictionaries.

| System | What it codes | Owner | Example |
|---|---|---|---|
| **ICD-10-CM / ICD-10 / ICD-11** | Diagnoses (and ICD-10-PCS procedures in US inpatient) | WHO / CDC | I21.9 acute MI |
| **CPT** | Procedures/services (US billing) | AMA (licensed) | 99213 office visit |
| **HCPCS** | Supplies, drugs, services (Medicare) | CMS | J-codes for injected drugs |
| **SNOMED CT** | Clinical concepts (very granular) | SNOMED Intl | 22298006 MI |
| **LOINC** | Lab tests & observations | Regenstrief | 4548-4 HbA1c |
| **RxNorm** | Normalized US drug names/ingredients | NLM | |
| **NDC** | Drug product package ID (labeler-product-package) | FDA | 0002-3227-30 |
| **ATC** | Drug classification by therapeutic area | WHO | A10BA02 metformin |
| **MedDRA** | Adverse events & regulatory medical terms | ICH/MSSO | hierarchy LLT→PT→HLT→HLGT→SOC |
| **WHODrug** | Medications in trials | Uppsala Monitoring Centre | |
| **UCUM** | Units of measure | | mg/dL |
| **DICOM** | Imaging format/standard | | |
| **CDISC CT** | Controlled terms in trials | CDISC | SEX: M/F/U |
| **GTIN / GS1** | Product barcodes, serialization | GS1 | |
| **UMLS** | Crosswalk of many vocabularies | NLM | |

## Coding in practice
- Trials: verbatim AE term → MedDRA code (auto-coder + human coder). Meds → WHODrug.
- Claims: ICD-10 + CPT + NDC drive reimbursement and analytics.
- Lab interoperability: local lab code → LOINC mapping (big data-engineering task).
- OMOP: everything mapped to "standard concepts" (SNOMED, RxNorm, LOINC) → [[OMOP-CDM]].

## Data pitfalls
- ICD-9 → ICD-10 transition in 2015 (US); code histories change.
- Many-to-many mappings; versions (MedDRA releases twice a year, mid-study version upgrades).
- Free-text → NLP.

## Resources (free)
- ICD-10-CM browser: https://www.cdc.gov/nchs/icd/icd-10-cm/index.html
- WHO ICD-11: https://icd.who.int/browse/
- SNOMED browser: https://browser.ihtsdotools.org
- LOINC (free account): https://loinc.org
- RxNorm / RxNav: https://rxnav.nlm.nih.gov
- NDC directory: https://www.fda.gov/drugs/drug-approvals-and-databases/national-drug-code-directory
- MedDRA: https://www.meddra.org
- ATC/DDD: https://atcddd.fhi.no/atc_ddd_index/
- Athena (OHDSI vocabularies): https://athena.ohdsi.org
