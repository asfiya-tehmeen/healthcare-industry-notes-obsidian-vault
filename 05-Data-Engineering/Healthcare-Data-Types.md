# Healthcare & Pharma Data Types

## Simple explanation
Different data answer different questions. Know source, shape, quality and privacy risk of each.

| Data | Source | Shape | Strengths | Weaknesses |
|---|---|---|---|---|
| Clinical trial (EDC) | sites | structured, CDISC | gold-standard quality | small N, expensive |
| EHR/EMR | hospital | structured + notes | rich clinical detail | messy, site-specific, missing |
| Claims | payers/pharmacies | structured coded | large, longitudinal, billing | no labs/outcomes, coding bias |
| Registry | disease societies | curated | disease depth | selection bias |
| Lab / LIMS | labs | numeric w/ units | objective | unit/LOINC mapping |
| Imaging | PACS | DICOM images | AI potential | huge, labeling |
| Genomics | sequencers | files (VCF) | precision medicine | very large, sensitive |
| Wearables/sensors | devices | time-series | continuous | noise, validation |
| Patient-reported (ePRO) | apps | surveys | patient voice | compliance |
| Safety / PV | spontaneous reports | ICSR | signal detection | under-reporting |
| Manufacturing | MES/SCADA/LIMS | batch, time-series | quality control | silos |
| Commercial | CRM, sales, IQVIA/Symphony | transactional | revenue insight | licensed, aggregated |
| Supply chain | ERP/WMS/EPCIS | events | traceability | partners' data |
| Unstructured | PDFs, notes, labels | text | huge info | NLP needed |
| Public | FAERS, CMS, ClinicalTrials.gov | open | free | needs cleaning |

## Concepts to master
- **Patient identity**: MRN per hospital → need **MPI / EMPI** (master patient index), probabilistic matching, tokenization (Datavant, LexisNexis) to link records across datasets without PII.
- **Longitudinal data**: index date, baseline, look-back/follow-up windows.
- **Missingness**: MCAR/MAR/MNAR.
- **Units & normalization**: mg/dL vs mmol/L.
- **Time**: UTC, ISO 8601, partial dates ("2024-05").
- **Hierarchies**: org → site → subject → visit → record.

## Public datasets to practice on
See [[13-Resources/Datasets]].
