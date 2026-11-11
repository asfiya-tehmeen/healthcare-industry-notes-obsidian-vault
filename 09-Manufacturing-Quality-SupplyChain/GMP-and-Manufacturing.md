# GMP, Manufacturing, Quality Control & Supply Chain

## Simple explanation
Even a perfect molecule is useless if each pill isn't identical, pure and potent. GMP = rules to build quality **into** the process, not just test at the end.

## Manufacturing flow (tablet)
Raw material receipt & testing → weighing/dispensing → blending → granulation → compression → coating → packaging/labeling → QA batch review → **batch release** (by Qualified Person in EU) → distribution.
Biologics: cell bank → fermentation/bioreactor → purification → fill-finish (sterile).
Vocabulary: **CMC** (chemistry, manufacturing & controls), **API**, **excipient**, **batch/lot**, **master batch record (MBR)**, **eBR**, **cleanroom grades**, **sterile**, **lyophilization**.

## Quality units
- **QA** – systems, release decisions, audits, deviations, change control.
- **QC** – lab testing (HPLC, dissolution, micro). Results: pass / **OOS** (out of spec) → investigation.
- **Validation**: process (PPQ), cleaning, analytical methods, equipment (IQ/OQ/PQ), computer systems.
- **Stability studies**, shelf-life.
- **Quality by Design (QbD)**, **Process Analytical Technology (PAT)**, **Continuous Manufacturing**, **Six Sigma/Lean**.
- Key metrics: yield, OEE, right-first-time, deviation rate, batch cycle time, **Cpk** capability.

## Data & systems
ERP (SAP), MES (Syncade, PAS-X), LIMS (LabWare, STARLIMS), QMS (TrackWise, Veeva QMS, MasterControl), historian (PI), SCADA, CDS (chromatography data systems – Empower; notorious for data-integrity findings).
Analytics: SPC control charts, multivariate analysis, predictive maintenance, batch genealogy, anomaly detection, digital twins.

## Supply chain
- **Serialization** (DSCSA US, EU FMD): unique ID per pack, track-and-trace, EPCIS events.
- **Cold chain** (2–8 °C; vaccines –70 °C): temperature excursion handling.
- **Counterfeits**, **shortages** (FDA shortage list), **demand planning**, **S&OP**, 3PLs, **GDP**.
- Globally concentrated API sourcing (India, China) – risk.

## SPC example
```python
import numpy as np
x = batch_potency; mu, s = x.mean(), x.std(ddof=1)
ucl, lcl = mu+3*s, mu-3*s
out = x[(x>ucl)|(x<lcl)]     # Western Electric rules add more
```

## Resources
- FDA CDER pharmaceutical quality: https://www.fda.gov/drugs/pharmaceutical-quality-resources
- ISPE: https://ispe.org ; PDA: https://www.pda.org
- DSCSA: https://www.fda.gov/drugs/drug-supply-chain-integrity/drug-supply-chain-security-act-dscsa
- FDA drug shortages: https://www.accessdata.fda.gov/scripts/drugshortages/
- Related: [[03-Regulatory-Compliance/GxP-Overview]]
