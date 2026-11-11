# Interview Prep: Resources & Best Practices

## Process (typical for pharma/health data roles)
1. Recruiter screen (motivation, salary, notice) → 2. Hiring manager (experience, projects) → 3. Technical (SQL/Python, data modeling, sometimes take-home) → 4. Domain/compliance round (GxP, validation, data integrity) → 5. Behavioral/panel → 6. HR/offer.
CROs and services firms often add an aptitude test or case. Consulting (ZS etc.) adds case interviews.

## 6-week prep plan
| Week | Focus |
|---|---|
| 1 | SQL: joins, window functions, CTEs (20 problems) – [[12-Practice-Problems/SQL-Problems]] |
| 2 | Python/pandas + one coding pattern per day |
| 3 | Data modeling + pipeline design (draw 3 architectures from memory) |
| 4 | Domain: GxP, Part 11, ALCOA+, CSV/CSA, HIPAA/GDPR, CDISC; flashcards |
| 5 | Industry awareness: [[16-Industry-Now/Trends-2026]], [[16-Industry-Now/Deals-Tracker]]; company deep-dives |
| 6 | Mock interviews (2 technical, 2 behavioral), resume polish, project walk-through |

## Free practice resources
**SQL/coding**: [DataLemur](https://datalemur.com), [StrataScratch](https://www.stratascratch.com), [LeetCode](https://leetcode.com), [HackerRank](https://www.hackerrank.com), [NeetCode](https://neetcode.io).
**System/data design**: [System Design Primer](https://github.com/donnemartin/system-design-primer), GitHub "data engineering interview questions" lists (search), [Start Data Engineering](https://www.startdataengineering.com).
**Behavioral**: STAR method – [Big Interview](https://www.biginterview.com) (free resources), Amazon-style leadership principles as a story-bank template.
**Mock interviews**: [Pramp](https://www.pramp.com), [interviewing.io](https://interviewing.io), peers, or ask an AI to role-play a GxP auditor.
**Domain flashcards**: make your own in Anki from [[00-Start-Here/02-Glossary]] ([Anki](https://apps.ankiweb.net)).
**Compliance reading**: FDA warning letters (read 10), MHRA data integrity guidance, FDA Q&A on data integrity – links in [[03-Regulatory-Compliance/Regulators-FDA-EMA-ICH]].
**Industry news**: Fierce Pharma, Endpoints, STAT, BioPharma Dive.
**Salary research**: Glassdoor, Levels.fyi (tech), AmbitionBox (India), LinkedIn Salary.

## Best practices — technical rounds
- **Clarify first**: restate the problem, ask about data size, nulls, ties, time zones.
- **Think aloud**; write simple correct SQL first, then optimize.
- For SQL: always state assumptions on NULLs/duplicates; use CTEs for readability; test edge cases (no rows, ties).
- For pipeline design: lead with *requirements → data flow → quality checks → security/compliance → monitoring → failure handling*. Mention immutability, audit trail, idempotency, validation evidence. **This compliance layer is what separates you.**
- Don't claim tools you haven't used. Say "I haven't used X, but I've used Y; they're similar because…".

## Best practices — domain/compliance rounds
- Use real structure: *Regulation → risk → control → evidence*.
- Always tie answers to **patient safety and data trustworthiness**.
- Use examples: shared logins, deleted OOS result, unvalidated Excel, hot-fix to prod.
- Know the difference: **validation vs verification**, **deviation vs CAPA**, **audit vs inspection**, **GCP vs GMP vs GLP**, **SDTM vs ADaM**, **HIPAA vs GDPR**, **pseudonymization vs anonymization**.
- Be able to explain a hypothetical inspection: "Show me who changed this value."

## Best practices — behavioral
STAR (Situation, Task, Action, Result) with numbers. Prepare 6 stories: data error found, conflict, tight deadline, learning something fast, improving a process, mistake you owned. Add one story about **choosing quality over speed**.

## Best practices — projects & resume
- 1 page (2 if >8 years). Lead with impact verbs and numbers.
- Put projects with links (GitHub) from [[15-Portfolio-Projects/Project-1-Clinical-Data-Pipeline]].
- Keywords mirror job description (SDTM, GxP, Part 11, Veeva, OMOP, FHIR, Snowflake, Airflow, dbt).
- Include certs: GCP, HIPAA, cloud.
- Tailor 3 bullets per application.

## Questions to ask interviewers
- "How is validation handled — traditional CSV or CSA?"
- "What does the data platform look like and who owns data quality?"
- "How did your last inspection go regarding data systems?"
- "How are AI tools governed here?"
- "What does success look like at 6 months?"

## Salary & negotiation
Research ranges; give a range anchored on market data; negotiate after offer; consider total comp, learning, brand (pharma GCC brand opens doors); in India compare fixed vs variable, notice-period buyout.

## Day-before checklist
Re-read job description · 2 recent company news items · your 3 projects' architecture · your 6 stories · questions to ask · test video/audio · sleep.

## Common mistakes
Memorizing definitions without examples · ignoring compliance in design answers · overclaiming · not knowing the company's pipeline/products · giving no questions at the end.

Related: [[Interview-Questions]], [[Career-Paths]], [[12-Practice-Problems/Compliance-Case-Exercises]]
