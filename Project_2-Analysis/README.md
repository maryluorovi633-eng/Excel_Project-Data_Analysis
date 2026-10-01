# Salary vs. Skills Analysis — Power Pivot

Where the [Dashboard](Project_1-Dashboard/README.md) project is about instant answers, this one is about digging into a real analytical question: **which skills actually correlate with a higher salary in data jobs, and does that answer change once you split by country or data job?**

## What it does

Two Power Query queries — `data_jobs_salary` and `data_jobs_skills` — are loaded straight into Excel's **Data Model** (not onto worksheets), where they're connected and queried through **Power Pivot** and **DAX** measures. Four PivotTables sit on top of that model, each answering a different slice of the question:

| Pivot | Question it answers |
|---|---|
| `Salary_Vs_Skills` | How do median salary and the average number of skills required per posting vary by job title? |
| `Salary_Analysis` | How does median salary for each job title split between US and non-US postings? |
| `Skill_Job_Analysis` | How often does each skill (SQL, Python, Excel, Tableau...) show up across postings? |
| `Skill_Salary_Analysis` | For each skill, what's the median salary of postings that require it, and how common is that skill? |

**Slicers** for Job Title and Country sit alongside the pivots so you can filter all of them interactively instead of reading four static tables.

## Why Power Pivot instead of just PivotTables on a table

The two queries needed to relate to each other (postings ↔ skills) without duplicating rows or forcing a messy VLOOKUP setup. I wanted the "Skill Likelihood" and median-salary figures to be real **DAX measures** that recalculate correctly under any filter combination — job title, country, or both at once — rather than static numbers I'd have to rebuild by hand every time the question changed. That's exactly the problem Power Pivot's data model is built to solve.

## A few numbers that came out of it

- **SQL** and **Excel** are the most commonly requested skills, but the highest *paying* skills (Python, Oracle, Tableau) aren't always the most common ones — likelihood and salary don't move together
- Senior titles (Senior Data Scientist, Senior Data Engineer) show both the highest median salaries and the widest US vs. non-US gap
- Some job titles (Data Analyst, Senior Data Analyst) show almost no US/non-US salary gap at all, while others (Machine Learning Engineer, Software Engineer) show a large one

## Try it yourself

1. Open the file in Excel and allow content/data connections if prompted.
2. Use the **Job Title** and **Country** slicers to filter any of the four pivot tables.
3. Right-click a pivot → **Refresh** if you update the underlying data and want the DAX measures to recalculate.
