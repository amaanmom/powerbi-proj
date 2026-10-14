# powerbi-proj
📊 Data Science Job Market Dashboard (Power BI)
This project presents an interactive Power BI dashboard built on a dataset of data science job postings. The analysis explores how job title, experience level, country, work mode and skills influence salary and hiring demand.

The dataset is synthetic and was created for learning. Images below are layout previews made from the sample data.

🎯 Objectives
Explore how experience, country, work mode and company size affect salaries.
Build a clear, interactive Power BI dashboard with KPIs, slicers and drill-through.
Practise advanced Power BI skills: Power Query, DAX, time intelligence, LOD, parameters, dataflows and Power BI Service.
Draw practical insights about the data science job market.
⚙️ Data Preparation
🧼 Data Cleaning (Power Query Editor)
Removed 40 duplicate rows (1,540 → 1,500)
Trimmed spaces and fixed text casing in job_title
Standardised country names (USA, us → United States)
Converted salary text like $120,000 to numbers
Corrected data types; kept 75 missing salaries as null with a salary_missing flag
🔄 Data Transformation
Created a date table (Dim_Date) and dimension tables (Dim_JobTitle, Dim_Country)
Split the skills column into rows (Jobs_Skills)
Created custom column Salary Band (Low / Medium / High)
Added parameters DataPath and MinSalary; code pasted via Advanced Editor (scripts/power_query/)
📈 Data Enrichment (DAX Measures)
Total Jobs, Avg Salary, Median Salary, Remote %
Time intelligence: Jobs YTD, Jobs Previous Year, Jobs YoY %, Jobs Rolling 3M
LOD-style: Overall Avg Salary, Avg Salary by Country (fixed), Salary vs Overall
What-if parameter: Jobs Above Threshold (see scripts/dax/measures.dax)
📊 Dashboard Overview

The dashboard consists of two interactive pages:

🧾 1. Summary Page

Show Image

A high-level overview with interactive KPIs, charts, slicers and navigation buttons.

🟢 KPIs
Total Jobs
Average Salary
Median Salary
Remote %
🎛️ Slicers / Interactive Buttons

Users can filter data by:

Year
Country
Job Title
Experience Level
Work Mode
Company Size

Show Image

📊 Charts & Visuals
Donut Chart – Jobs by experience level
Pie Chart – Work mode distribution
Clustered Bar Chart – Average salary by job title and work mode
Bar Chart – Jobs by country (with drill-through)
Bar Chart – Average salary by country vs overall average (LOD)
Line Chart – Jobs per month: current year vs previous year (time intelligence)
Clustered Column Chart – Average salary by company size and experience
Bar Chart – Most requested skills
Clustered Column Chart – Remote % by experience level and company size
🔍 Drill-Through Functionality

From the "Jobs by country" and "Average salary by country" charts, users can drill through to the Detail page to see:

Total jobs
Average salary
The individual job postings

🔁 Page Navigation
Details Button on the Summary Page → Detail Page
Back Button on the Detail Page → Summary Page
📋 2. Detail Page

A record-level view of job postings with cards, filters and a detailed table.

📌 Cards
Total Jobs
Remote Jobs
Average Salary
Median Salary
Jobs YoY %
🎛️ Slicers / Filters

Filter by:

Country
Job Title
Experience Level
Work Mode
Year

☁️ Power BI Service, Dataflows & Storytelling
Report published to Power BI Service, visuals pinned to a dashboard, scheduled refresh set up
Cleaning logic reusable through a Dataflow
Report follows a short story: context → overview → salary → trend → takeaways

See scripts/notes/.

🔑 Key Insights
Research Scientist roles pay the most (avg $144,057); Data Analyst roles pay the least ($74,012).
Experience has a clear effect: Executive pay is about 2.2x Entry-level pay.
Country matters: United States has the highest average salary and India the lowest.
About 39% of postings are remote.
Postings changed -7.6% in 2024 vs 2023.
SQL is the most requested skill.
✅ Conclusion

This dashboard shows how role, experience, location and skills shape data science salaries and demand. The interactive filters and drill-through make it easy for learners and job seekers to explore the market and plan their careers.

🚀 How to Use
Clone this repo or download the files.
Open ds-job-market-dashboard.pbix in Power BI Desktop.
If the data fails to load, update the DataPath parameter (Home → Transform data → Edit parameters).
Explore the slicers, charts and drill-through.
📁 Project Structure
├── ds-job-market-dashboard.pbix     # Power BI dashboard
├── data
│   ├── raw/ds_jobs_raw.csv          # Messy source dataset
│   └── cleaned/ds_jobs_clean.csv    # Cleaned dataset
├── images                           # Dashboard screenshots
├── scripts
│   ├── power_query/                 # M code (parameters, cleaning, date table)
│   ├── dax/measures.dax             # DAX measures
│   └── notes/                       # Build guide, Service, Dataflows, Storytelling
└── README.md
🛠 Tools Used
Power BI Desktop – data modelling and dashboard creation
Power Query (M) – data cleaning and transformation
DAX – measures, time intelligence, LOD-style calculations
Power BI Service – publishing, dataflows, refresh
👤 Author

Amaan Momin

Email: amaanmomin8@gmail.com
GitHub: github.com/<your-username>
LinkedIn: linkedin.com/in/<your-profile>
🌟 Feedback & Support

Suggestions are welcome. If you found this project useful, please give it a ⭐️.
