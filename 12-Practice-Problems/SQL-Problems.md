# SQL & Analytics Problems (with links)

Each skill below maps to a real healthcare task.

## Platforms
- LeetCode SQL 50 plan: https://leetcode.com/studyplan/top-sql-50/
- HackerRank SQL: https://www.hackerrank.com/domains/sql
- StrataScratch: https://www.stratascratch.com
- DataLemur (has healthcare/UnitedHealth/CVS questions): https://datalemur.com/questions
- SQLZoo: https://sqlzoo.net
- PG Exercises: https://pgexercises.com
- Kaggle Learn SQL / Advanced SQL: https://www.kaggle.com/learn/intro-to-sql
- Mode SQL tutorial: https://mode.com/sql-tutorial

## Skill → problem → healthcare use
| Skill | Problem | Healthcare analog |
|---|---|---|
| Top-N per group | [Department Top Three Salaries](https://leetcode.com/problems/department-top-three-salaries/) | top 3 prescribers per specialty |
| Nth highest | [Second Highest Salary](https://leetcode.com/problems/second-highest-salary/) | 2nd largest claim per patient |
| Duplicates | [Duplicate Emails](https://leetcode.com/problems/duplicate-emails/), [Delete Duplicate Emails](https://leetcode.com/problems/delete-duplicate-emails/) | duplicate patient/AE records |
| Consecutive events | [Consecutive Numbers](https://leetcode.com/problems/consecutive-numbers/) | 3 consecutive abnormal labs |
| Retention / next-day | [Game Play Analysis IV](https://leetcode.com/problems/game-play-analysis-iv/) | patient readmission within N days |
| Date comparison | [Rising Temperature](https://leetcode.com/problems/rising-temperature/) | rising lab value vs prior visit |
| Ranking | [Rank Scores](https://leetcode.com/problems/rank-scores/) | rank hospitals by outcome |
| Cancellation rate | [Trips and Users](https://leetcode.com/problems/trips-and-users/) | claim denial rate by payer |
| Self-join/mgmt | [Employees Earning More Than Their Managers](https://leetcode.com/problems/employees-earning-more-than-their-managers/) | hierarchy (org/site) checks |
| Moving avg | [Restaurant Growth](https://leetcode.com/problems/restaurant-growth/) | rolling 7-day cases/TRx |
| Gaps | [Human Traffic of Stadium](https://leetcode.com/problems/human-traffic-of-stadium/) | gaps-and-islands: continuous therapy |
| Pivot/conditional agg | [Reformat Department Table](https://leetcode.com/problems/reformat-department-table/) | long→wide labs |
| Anti-join | [Customers Who Never Order](https://leetcode.com/problems/customers-who-never-order/) | patients with no follow-up |

## Healthcare-flavoured SQL (DataLemur)
Search the site for: "Patient Support Analysis (UnitedHealth)", "Pharmacy Analytics" (CVS Health) series, "Cards", etc. https://datalemur.com/questions?category=SQL

## Do-it-yourself exercise set (make your own tables)
1. Using CMS DE-SynPUF or Synthea: patients with ≥2 diabetes diagnoses 30+ days apart.
2. Compute 30-day readmission rate per hospital.
3. PDC adherence for statins per patient.
4. Top 10 adverse events per drug from FAERS.
5. Detect lab values changing >50% between consecutive visits (LAG).
6. Build "first treatment, line of therapy" sequence per patient.
7. Find duplicate subjects (same DOB+sex+initials) across sites.
8. Audit trail: users modifying >100 records in an hour.

## Tips
Master: window functions, CTEs, joins, date math, conditional aggregation, NULL behavior, indexing, EXPLAIN.
Related: [[Python-and-DataEng-Problems]], [[06-Analytics/Claims-Analytics]]
