# Regulatory Approval Process

## Simple explanation
Regulators act as independent judges: the company submits evidence; the agency decides whether benefits outweigh risks and what the label (allowed uses/warnings) says.

## US (FDA)
1. **Pre-IND meeting** → **IND** (30-day review) → trials may start.
2. **End-of-Phase-2 meeting** to align Phase 3 design.
3. **NDA** (small molecule) or **BLA** (biologic) submitted in **eCTD** format.
4. FDA review: standard 10 months, priority 6 months (after 60-day filing). Advisory committee optional.
5. Outcome: **Approval** or **Complete Response Letter (CRL)**.
6. Post-approval: labeling changes, REMS, Phase IV commitments.
- **505(b)(2)** – hybrid path using existing data. **ANDA** – generics (bioequivalence). **Biosimilar 351(k)**.
- **Accelerated approval** based on surrogate endpoints; confirmatory trials required.

## EU (EMA)
Centralised procedure → **CHMP** opinion → European Commission decision (~210 active days + clock stops). Plus national procedures (MRP/DCP).

## Other
Japan PMDA, China NMPA, India CDSCO, UK MHRA, Health Canada. **ICH** harmonizes formats (CTD).

## eCTD structure (5 modules)
1. Regional admin info 2. Summaries 3. Quality (CMC) 4. Nonclinical 5. Clinical.
Datasets (SDTM/ADaM + define.xml) go in Module 5. Tooling is "RIM" (Regulatory Information Management, e.g. Veeva Vault RIM).

## Data relevance
- Submission-ready datasets must pass **validation** (Pinnacle 21 / CDISC conformance rules).
- Regulators can request raw data and inspect systems (GCP/GMP inspections) → [[03-Regulatory-Compliance/Inspections-and-Audits]].

## Resources
- Drugs@FDA (read real approval packages): https://www.accessdata.fda.gov/scripts/cder/daf/
- FDA Drug Approval Process: https://www.fda.gov/drugs/information-consumers-and-patients-drugs/fdas-drug-review-process-ensuring-drugs-are-safe-and-effective
- EMA medicines: https://www.ema.europa.eu/en/medicines
- eCTD overview (ICH): https://www.ich.org/page/ctd
