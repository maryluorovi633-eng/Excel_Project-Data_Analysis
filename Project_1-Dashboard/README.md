# Data Job Salary Dashboard — Power Query

An interactive, dropdown-driven salary calculator built on top of a raw dataset of roughly **32,600 data job postings**. The goal was simple: let someone with zero Excel experience answer "what does a Data Engineer or another job title listed in the US or any other country as a full-timer or another employment type make?" in three clicks, without touching a formula.

## What it does

Open the **`Salary_Calculator`** sheet and pick a **Job Title**, **Country**, and employment **Type** from the dropdowns. The workbook instantly:

- Looks up the matching **median salary**
- Recalculates job-count breakdowns by platform (LinkedIn, Indeed, etc.)
- Updates two bar charts and a **geographic map** showing salary by country

Nothing is hardcoded — every number on the sheet reacts live to your selection.

## How it's built

**Power Query** does the heavy lifting up front: the raw postings data is imported and loaded into a structured Excel Table (`jobs`, 32,673 rows × 16 columns) — job title, location, salary rate, skills, country, schedule type, and more — cleaned and shaped before a single formula touches it.

From there, the sheet logic is entirely formula-driven:

- **`XLOOKUP`** pulls the median salary that matches the current dropdown selection
- **`COUNTIFS`** builds the platform/job-count breakdowns behind the calculator
- Dynamic array formulas populate the helper tables (`Title`, `Country`, `Type`, `Platform`) that feed the dropdowns and charts, so adding new job titles or countries to the source data doesn't require touching the formulas
- A `Data_Validation` sheet keeps the dropdown lists clean and sorted

## Sheet map

| Sheet | Purpose |
|---|---|
| `Data` | The full raw job postings table, loaded via Power Query |
| `Salary_Calculator` | The interactive front end — dropdowns + calculated median salary |
| `Title` / `Country` / `Type` / `Platform` | Helper tables that calculate the median salary and counts for every possible filter combination |
| `Data_Validation` | Sorted, de-duplicated lists that power the dropdown menus |

## Why this approach

A dashboard like this needs to feel instant and forgiving — no "refresh and wait," no broken formulas when someone picks an option you didn't expect. Building it on Power Query for the data layer and dynamic formulas for the logic layer meant the whole thing scales if the source data grows, without a redesign.

## Try it yourself

1. Open the file in Excel and allow content/data connections if prompted.
2. Go to the `Salary_Calculator` sheet.
3. Change the **Job Title**, **Country**, or **Type** dropdown and watch the salary, chart, and map update.
