# Clinical Trials Explained

## Simple explanation
A clinical trial is a controlled experiment on people to answer: *is this treatment safe and does it work better than what we already have (or placebo)?*

## Phases
- **Phase I** – small, mostly healthy volunteers (cancer: patients). Safety, dose.
- **Phase II** – patients, dose-finding and early efficacy.
- **Phase III** – large, randomized, often double-blind, multi-country. Basis for approval.
- **Phase IV** – after approval; long-term safety.

## Key design concepts
- **Randomization** – chance decides group, avoids bias.
- **Blinding** – single/double blind so expectations don't skew results.
- **Control** – placebo or active comparator.
- **Endpoint** – the measured outcome (primary / secondary). e.g. overall survival, HbA1c change.
- **Inclusion/exclusion criteria** – who can join.
- **Informed consent**, **IRB approval**, **ICH-GCP E6** ethics rules.
- **DSMB** – independent group monitoring safety.
- **Protocol** – master plan. **SAP** – statistical plan written *before* unblinding.
- **Intent-to-treat vs per-protocol** populations.
- **Adaptive, basket, umbrella, decentralized trials** – modern designs.

## Who's involved
Sponsor (pharma), CRO, sites (hospitals), investigators, CRAs (monitors), data managers, biostatisticians, medical writers, safety physicians, regulators.

## Clinical data flow (the part you'll work on)
```
Patient visit → Site enters into eCRF (EDC) ─┐
Lab/ECG/imaging vendors → external data ─────┤→ Clinical Data Management
Wearables / ePRO / eCOA ─────────────────────┘     (cleaning, queries, coding MedDRA/WHODrug)
→ Database lock → SDTM (tabulation) → ADaM (analysis) → TLFs (tables, listings, figures)
→ Clinical Study Report → eCTD submission
```
See [[04-Data-Standards/CDISC-SDTM-ADaM]].

## Systems
EDC (Medidata Rave, Veeva EDC, Oracle InForm), CTMS (trial management), eTMF, IRT/IWRS (randomization), ePRO, safety DB, SAS/R for stats.

## Real-world example
COVID-19 vaccine Phase III: ~44,000 participants, randomized vaccine vs placebo, primary endpoint = symptomatic COVID cases; interim analysis by independent DSMB.

## Resources
- ClinicalTrials.gov (search any trial): https://clinicaltrials.gov
- ICH E6 GCP: https://www.ich.org/page/efficacy-guidelines
- FDA clinical trials info: https://www.fda.gov/patients/clinical-trials-what-patients-need-know
- Coursera/NIH free: "Clinical Trials Operations" (search) – see [[13-Resources/Free-Courses]]
- ClinicalTrials.gov API (data engineering practice): https://clinicaltrials.gov/data-api/api
