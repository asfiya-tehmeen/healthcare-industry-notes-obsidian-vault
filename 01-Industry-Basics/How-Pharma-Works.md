# How Pharma Works

## Simple explanation
Making a drug is like building a skyscraper that costs ~$1–2.5 billion, takes 10–15 years, and where ~90% of projects collapse. Companies recoup that by getting a **patent** (~20 years of exclusivity) and charging high prices until competitors (generics) arrive.

## Value chain
1. **Discovery** – find a target (e.g. a protein driving disease) and a molecule that hits it.
2. **Preclinical** – lab/animal safety tests.
3. **Clinical trials** – Phase I → III in humans.
4. **Regulatory submission** – file the dossier (NDA/BLA/MAA).
5. **Manufacturing** – make it at scale under GMP.
6. **Distribution** – manufacturer → wholesaler → pharmacy/hospital → patient.
7. **Commercial** – marketing, sales, pricing, payer contracts.
8. **Post-market** – safety monitoring, Phase IV, real-world evidence.
9. **Patent expiry** – generics/biosimilars enter; price falls 80–90%.

## Business models
- **Big pharma** (Pfizer, Novartis, Roche, Merck, J&J, AstraZeneca, Sanofi, Lilly, Novo Nordisk) – many products, global.
- **Biotech** – smaller, science-driven; often acquired.
- **Generics** (Teva, Sandoz, Viatris, Sun, Dr. Reddy's, Cipla).
- **CROs / CDMOs** – services (IQVIA, Parexel, ICON, Lonza, Catalent).
- **Medtech/devices** (Medtronic, Abbott, Siemens Healthineers).
- **Health IT / data** (Veeva, IQVIA, Epic, Medidata, Komodo, Flatiron).

## How money flows (US)
Patient pays copay → Insurer (payer) pays pharmacy → PBM negotiates rebates with manufacturer → Wholesaler (McKesson, Cencora, Cardinal) buys from manufacturer and sells to pharmacy. Gross-to-net gap (list price vs. what manufacturer actually nets) is a huge analytics topic. See [[07-Commercial-Market-Access/Pharma-Commercial-101]].

## Why data matters at each step
| Step | Data produced | Typical roles |
|---|---|---|
| Discovery | assay, genomics, chemistry | bioinformatics, cheminformatics |
| Clinical | EDC, lab, imaging | clinical data mgmt, biostat, programming |
| Regulatory | eCTD documents, metadata | regulatory ops / RIM |
| Manufacturing | batch records, sensor data | quality, MES, data eng |
| Commercial | sales, claims, CRM | analytics, data science |
| Safety | AE reports | PV data, signal detection |

## Resources
- Khan Academy / YouTube: "How are drugs developed" (FDA video) – https://www.fda.gov/patients/drug-development-process
- Book: *Bad Pharma* (Goldacre) and *Drug Discovery and Development* (Hill & Rang) – see [[13-Resources/Books]]
- PhRMA primer: https://phrma.org
