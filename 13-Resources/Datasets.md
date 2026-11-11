# Free Datasets & APIs for Practice

## Drug / safety / regulatory
- **openFDA** (drug events, labels, recalls, NDC, devices): https://open.fda.gov
- **FAERS quarterly files**: https://www.fda.gov/drugs/fdas-adverse-event-reporting-system-faers/fda-adverse-event-reporting-system-faers-latest-quarterly-data-files
- **DailyMed** labels (SPL XML): https://dailymed.nlm.nih.gov/dailymed/spl-resources.cfm
- **Drugs@FDA** data files: https://www.fda.gov/drugs/drug-approvals-and-databases/drugsfda-data-files
- **Orange Book data**: https://www.fda.gov/drugs/drug-approvals-and-databases/orange-book-data-files
- **ClinicalTrials.gov API/AACT database (full relational copy)**: https://aact.ctti-clinicaltrials.org
- **FDA Warning letters / Inspection data dashboard**: https://datadashboard.fda.gov

## Claims / policy
- **CMS data**: https://data.cms.gov (Part D prescribers, Open Payments, provider utilization)
- **CMS DE-SynPUF** synthetic claims (link in [[06-Analytics/Claims-Analytics]])
- **HCUP** (some free tools): https://hcup-us.ahrq.gov
- **Medicare Part D spending by drug**: data.cms.gov

## Clinical / EHR
- **Synthea** (generate synthetic FHIR/CSV patients): https://synthetichealth.github.io/synthea/
- **MIMIC-IV / MIMIC-IV demo (ICU EHR)**: https://physionet.org/content/mimic-iv-demo/
- **eICU demo**: https://physionet.org/content/eicu-crd-demo/
- **OMOP Eunomia** sample: https://github.com/OHDSI/Eunomia
- **CDISC pilot study data**: https://github.com/phuse-org/phuse-scripts and https://github.com/cdisc-org/sdtm-adam-pilot-project
- **pharmaversesdtm / pharmaverseadam** packages (R, sample SDTM/ADaM): https://pharmaverse.github.io/pharmaversesdtm/

## Biomedical science
- ChEMBL: https://www.ebi.ac.uk/chembl/ · PubChem: https://pubchem.ncbi.nlm.nih.gov · DrugBank (academic): https://go.drugbank.com
- UK Biobank (application), TCGA: https://portal.gdc.cancer.gov
- Open Targets: https://platform.opentargets.org
- PubMed E-utilities API: https://www.ncbi.nlm.nih.gov/books/NBK25501/

## Public health
- WHO GHO: https://www.who.int/data/gho · CDC WONDER: https://wonder.cdc.gov · Our World in Data: https://ourworldindata.org
- India: https://data.gov.in, CDSCO site.

## Kaggle
Search "healthcare", "diabetes", "medical cost", "drug reviews", "FAERS": https://www.kaggle.com/datasets

## Tools to explore them
DuckDB (query CSV/Parquet/NDJSON locally): https://duckdb.org ; Jupyter; Metabase for dashboards.
