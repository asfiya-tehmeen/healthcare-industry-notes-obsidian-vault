# Pharmacovigilance (PV) – Drug Safety

## Simple explanation
Trials are small and short; rare side effects show up only after thousands use the drug. PV is the system to **collect, assess, and act** on safety reports for the life of the drug.

## Key definitions
- **Adverse Event (AE)** – any untoward medical occurrence (causal link not required).
- **Adverse Drug Reaction (ADR)** – AE with a reasonable causal link.
- **Serious** = death, life-threatening, hospitalization, disability, congenital anomaly, other medically important.
- **Expected/Unexpected** vs reference safety information (IB, label). **SUSAR** = suspected unexpected serious ADR.
- **Causality** (WHO-UMC, Naranjo), **seriousness vs severity** (not same).

## Case lifecycle
Intake (doctor, patient, literature, trial, social media) → triage (valid case needs: identifiable patient, reporter, suspect product, event) → data entry in safety DB (Argus/ArisG) → MedDRA/WHODrug coding → medical review & narrative → **submission** to regulators within timelines → follow-up.

## Timelines (expedited)
Fatal/life-threatening unexpected: **7 days** initial; other serious: **15 days**. Periodic: **PSUR/PBRER**, **DSUR** (annual for trials), **RMP/REMS** risk management.

## Signal detection
Disproportionality statistics on spontaneous report DBs: **PRR**, **ROR**, **EBGM** (Bayesian). Compare observed vs expected count for drug-event pair.
```sql
-- 2x2 table per drug-event pair: a = drug&event, b = drug&other events, c = other drugs&event, d = rest
-- PRR = (a/(a+b)) / (c/(c+d)) ;  ROR = (a*d)/(b*c)
```

## Data sources
**FAERS** (FDA), **VigiBase** (WHO), **EudraVigilance** (EU), **VAERS** (vaccines), **MAUDE** (devices), literature (PubMed monitoring), social listening.

## Systems & automation
Oracle Argus, ArisG, Veeva Vault Safety; E2B(R3) gateways; **AI for case intake, auto-coding, narrative generation, duplicate detection** (heavy automation opportunity, high validation burden).

## Careers
Drug safety associate, PV scientist, safety data analyst/engineer, signal analyst, PV systems/compliance (inspection readiness).

## Resources
- FAERS data: https://www.fda.gov/drugs/fdas-adverse-event-reporting-system-faers/fda-adverse-event-reporting-system-faers-public-dashboard
- openFDA drug events API: https://open.fda.gov/apis/drug/event/
- ICH E2A–E2F, EU GVP modules: https://www.ema.europa.eu/en/human-regulatory-overview/post-authorisation/pharmacovigilance-post-authorisation
- WHO Uppsala Monitoring Centre: https://who-umc.org
- Project: [[15-Portfolio-Projects/Project-2-FAERS-Signal-Detection]]
