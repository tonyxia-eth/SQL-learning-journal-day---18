# SQL-learning-journal-day---18

# Day 18 – SQL Learning Journey 🧠💻

## 🗓️ Date: 4/May/2025
## 🔥 Focus Area:
Multi-table JOINs in SQL — specifically, mastering 2-table and 3-table joins across the `players`, `salaries`, and `teams` tables in the Moneyball dataset.

## ✅ What I Practiced:
- Chained multiple `JOIN`s correctly using shared foreign keys
- Filtered results using `WHERE` with salary and year conditions
- Ordered results using `ORDER BY` without needing aggregates
- Avoided incorrect `GROUP BY` usage when no aggregate was needed

## 💡 Key Learnings:
- **JOIN bridges must follow relational paths**: Only join tables that are connected through matching keys (e.g. `players` → `salaries` → `teams`)
- **GROUP BY is only necessary when using aggregate functions like SUM(), AVG(), etc.**
- Writing clean, readable queries makes debugging 10x easier

## 🏆 Highlight Query:
```sql
SELECT players.first_name, players.last_name, teams.name, salaries.salary
FROM players
JOIN salaries ON players.id = salaries.player_id
JOIN teams ON salaries.team_id = teams.id
WHERE salaries.year = 2001
AND salaries.salary >= 10000000
ORDER BY salaries.salary DESC
LIMIT 5;

🚀 Progress Badge
Unlocked: Multi-JOIN Mastery - Level 1 🛡️
