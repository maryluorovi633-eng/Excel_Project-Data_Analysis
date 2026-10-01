# 📊 Excel Data Analytics Portfolio

Hi, I'm Maria G. Orozco. This repo holds two Excel projects I built while following [Luke Barousse's Data Analyst Bootcamp](https://www.youtube.com/@LukeBarousse) on YouTube. I wanted a portfolio piece that goes beyond "I know Excel formulas" and actually shows how I think through data — cleaning it, modeling it, and turning it into something someone could open and use.

Both projects run on the same dataset: roughly **32,600 real job postings** for data-related roles (Data Analyst, Data Scientist, Data Engineer, and more), with fields like job title, location, salary, platform, and required skills.

## What's inside

| File | What it does | Core skill |
|---|---|---|
| [`Salary_Dashboard.xlsx`](./Salary_Dashboard.xlsx) | An interactive salary calculator — pick a job title, country, and employment type from dropdowns and get the median salary, charts, top job platfom, and a job count | **Power Query** + dynamic array formulas |
| [`Salary_Analysis.xlsx`](./Salary_Analysis.xlsx) | A deeper look at how salary relates to skills and country, using a proper data model | **Power Pivot / DAX** + PivotTables & Slicers |

## Why two separate projects

I wanted to show both sides of what Excel can do at an intermediate/advanced level. The Dashboard is about **getting and shaping data** (Power Query, dynamic arrays, and a friendly interactive front end). The Analysis is about **modeling data properly**; relating tables in the Data Model and writing DAX measures so the numbers hold up under any filter combination, instead of static one-off calculations.

## Tools & skills demonstrated

- Power Query (import, cleaning, transformation of ~32K rows)
- Power Pivot & the Data Model
- DAX measures
- Dynamic array formulas (`XLOOKUP`, array-based lookups)
- `COUNTIFS` and conditional logic
- Data Validation (dropdown-driven interactivity)
- PivotTables & Slicers
- Working with a large, messy, real-world dataset

## About me

I'm working on building my skills as a data analyst, and this portfolio is part of that. I'm always open to feedback — feel free to open an issue, reach out, or just poke around the files. They're built to be opened in Excel 365 and played with, not just read about.
