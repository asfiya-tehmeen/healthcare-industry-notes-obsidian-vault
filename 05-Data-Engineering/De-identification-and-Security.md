# De-identification, Linking & Security

## Simple explanation
You often need patient-level data for research but must not reveal who the patients are. Techniques reduce re-identification risk while keeping usefulness.

## Techniques
| Technique | What | Caveat |
|---|---|---|
| Suppression | remove field/rows | lose info |
| Generalization | age→age band, zip→3 digits | small cells still risky |
| Pseudonymization | replace ID with token | still personal data under GDPR |
| Hashing + salt | one-way ID | rainbow tables if unsalted/low entropy |
| Date shifting | random per-patient offset | keeps intervals |
| Noise / differential privacy | add noise | accuracy tradeoff |
| k-anonymity / l-diversity | each record indistinguishable from k−1 | linkage attacks |
| Synthetic data | model-generated | may leak if overfit |
| Tokenization/privacy-preserving record linkage | link across sources w/o PII | vendor dependent |
| Federated analysis | code goes to data | infra heavy (OHDSI, TriNetX) |
| Trusted Research Environments | locked workspace | e.g. UK Biobank RAP |

## Security controls (HIPAA Security Rule & beyond)
Encryption at rest/in transit, KMS key rotation, VPC/private endpoints, IAM least privilege, MFA, row/column security, dynamic masking, DLP scanning for PII in free text, secrets managers, logging/SIEM, vulnerability mgmt, penetration tests, incident response, SOC 2 / ISO 27001 / HITRUST certifications for vendors.

## Python snippet: pseudonymize + generalize
```python
import hashlib, os, pandas as pd
SALT = os.environ["PSEUDO_SALT"]          # in a secrets manager, never in code
def tok(x): return hashlib.sha256((SALT+str(x)).encode()).hexdigest()[:16]
df["patient_token"] = df.mrn.map(tok)
df["age_band"] = pd.cut(df.age,[0,17,39,64,89,200],labels=["<18","18-39","40-64","65-89","90+"])
df = df.drop(columns=["name","mrn","phone","dob"])
```

## Free-text de-id
Names/dates in clinical notes: tools like Microsoft Presidio, Philter, AWS Comprehend Medical, Google DLP.

## Resources
- HHS de-id guidance: https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html
- Presidio: https://microsoft.github.io/presidio/
- HITRUST: https://hitrustalliance.net
- Related: [[03-Regulatory-Compliance/HIPAA-GDPR-Privacy]]
