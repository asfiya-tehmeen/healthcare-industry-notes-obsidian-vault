# CDISC: SDTM, ADaM, Define-XML

## Simple explanation
Every pharma company used to structure trial data differently. FDA (and PMDA) now **require CDISC standards** so reviewers can load any submission the same way. Think of it as a mandatory schema.

## The flow
```
CDASH (how to collect on forms) → SDTM (tabulate what was collected)
→ ADaM (derive what's needed for analysis) → TLFs (tables/listings/figures)
Metadata described in Define-XML; controlled terms from CDISC Controlled Terminology (NCI EVS)
```

## SDTM – Study Data Tabulation Model
Data organised in **domains** (one table each), long/"tall" format, one row per observation.
| Domain | Contents |
|---|---|
| DM | Demographics (one row per subject) |
| AE | Adverse events |
| CM | Concomitant meds |
| EX | Exposure (dosing) |
| LB | Lab results |
| VS | Vital signs |
| MH | Medical history |
| DS | Disposition |
| SV/SE | Visits / elements |
| TS/TA/TE | Trial summary / arms / elements |
Key variables: `STUDYID`, `USUBJID` (unique subject), `DOMAIN`, `--SEQ`, `--TERM`, `--STDTC` (ISO 8601 dates), `VISIT`. Naming rule: 2-letter domain prefix (e.g. `AETERM`, `LBTESTCD`).

## ADaM – Analysis Data Model
- **ADSL** – subject-level (one row/subject; treatment arms, flags like `SAFFL`, `ITTFL`).
- **BDS** (Basic Data Structure) – e.g. ADLB, ADVS: `PARAMCD`, `PARAM`, `AVAL`, `BASE`, `CHG`, `ADT`.
- **OCCDS** – ADAE, ADCM (occurrence data).
- **ADTTE** – time-to-event (`AVAL`, `CNSR`).
- Principle: **traceability** back to SDTM and "analysis-ready" – one proc away from the stat result.

## Mini example (SDTM DM in pandas)
```python
import pandas as pd
raw = pd.DataFrame({"subj":["001","002"],"sex":["Male","Female"],"dob":["1980-03-04","1975-11-20"],
                    "rfstdtc":["2024-01-10","2024-01-12"]})
dm = pd.DataFrame({
  "STUDYID":"ABC123","DOMAIN":"DM",
  "USUBJID":"ABC123-"+raw.subj,
  "SUBJID":raw.subj,
  "SEX":raw.sex.map({"Male":"M","Female":"F"}),
  "BRTHDTC":raw.dob,
  "RFSTDTC":raw.rfstdtc})
dm["AGE"]=((pd.to_datetime(dm.RFSTDTC)-pd.to_datetime(dm.BRTHDTC)).dt.days/365.25).astype(int)
```

## Tools & jobs
- SAS (still dominant), **R** (`pharmaverse`: admiral, sdtm.oak, xportr, pharmaversesdtm), Python (growing)
- **Pinnacle 21 Community** – validator, **Define-XML** generators
- Roles: statistical programmer, clinical data engineer, standards specialist

## Resources
- CDISC (free standards after login): https://www.cdisc.org/standards
- Pharmaverse: https://pharmaverse.org
- admiral docs (ADaM in R): https://pharmaverse.github.io/admiral/
- CDISC pilot data & scripts: https://github.com/phuse-org/phuse-scripts
- Pinnacle 21 Community: https://www.certara.com/software/pinnacle-21-enterprise/ (search "P21 Community")
- PHUSE: https://phuse.global ; PharmaSUG papers: https://www.pharmasug.org
- Next: [[Medical-Coding-Systems]]
