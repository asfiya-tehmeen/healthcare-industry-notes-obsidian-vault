# Clinical Trial Analytics & Biostatistics Basics

## Simple explanation
Biostatistics decides if the observed difference between drug and placebo is real or luck.

## Core stats concepts
- **Hypothesis testing**: null (no effect) vs alternative; **p-value**; **alpha** 0.05; **power** (80–90%); **sample size**.
- **Confidence intervals**; **effect size**; **non-inferiority / superiority**.
- **Endpoints**: continuous (change in BP) → t-test/ANCOVA/MMRM; binary (responder) → chi-square/logistic; time-to-event (survival) → **Kaplan–Meier**, log-rank, **Cox**; counts → Poisson.
- **Multiplicity**, interim analyses, alpha spending.
- **Missing data**: LOCF (old), MMRM, multiple imputation; **estimands** (ICH E9(R1)).
- **Populations**: ITT, mITT, PP, Safety.
- **Subgroup / forest plots**, **waterfall plots**, **swimmer plots**.

## Outputs: TLFs
Tables (demographics Table 14.1.1, AE summary), Listings, Figures. Programmed in SAS/R from ADaM, validated by **double programming** (independent programmer reproduces results).

## Operational analytics
Enrollment rate vs plan, screen failure %, site performance, query aging, protocol deviations, data entry lag, risk indicators (KRIs), dashboards in CTMS/JReview/Spotfire/Power BI.

## Tools
SAS, R (`survival`, `lifelines` in Python, `tidyverse`, `gtsummary`, `Tplyr`, `rtables`, `tern`), Python (`statsmodels`, `scipy`), JMP, East/nQuery (sample size).

## Mini-exercise (Python)
```python
from lifelines import KaplanMeierFitter
km = KaplanMeierFitter()
for arm, g in adtte.groupby("TRT01P"):
    km.fit(g.AVAL, event_observed=1-g.CNSR, label=arm); km.plot()
```

## Resources
- FDA guidance E9 / E9(R1): https://www.ich.org/page/efficacy-guidelines
- Free: Penn State STAT 509 "Design and Analysis of Clinical Trials" – https://online.stat.psu.edu/stat509/
- Free: Johns Hopkins "Biostatistics in Public Health" (Coursera audit)
- Book: *Fundamentals of Clinical Trials* (Friedman et al.) → [[13-Resources/Books]]
- Related: [[04-Data-Standards/CDISC-SDTM-ADaM]]
