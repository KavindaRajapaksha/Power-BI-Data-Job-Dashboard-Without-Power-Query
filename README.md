```markdown
# Power BI Data Job Dashboard 

A polished, production-ready Power BI report that analyzes job market data at scale (≈500K rows). This project intentionally avoids Power Query — all shaping, relationships and logic are done in the model and with DAX. The repository contains the Power BI (.pbix) file and a short demo GIF (attach as `demo.gif` — see Image 1).

![Power BI Project1](https://github.com/user-attachments/assets/54dc4a6c-9bc9-4cac-97d3-9781010f1459)


Repository contents
- Power-BI-Data-Job-Dashboard-Without-Power-Query.pbix
- demo.gif (short animated preview showing interactions)
- README.md (this file)
- LICENSE (MIT)

Dataset
- Source (big data, ~500K rows): https://drive.google.com/file/d/1CQSsnEuJYYA87YKOeJa5-Jf-CujsL3Z2/view?usp=sharing
- Format: CSV (or similar). Place locally and point the PBIX file to it if needed.
- Note: No Power Query transformations were applied — data is imported raw and modeled inside Power BI.

Overview
This dashboard gives a clear executive and analytical view of job counts, salary medians, hourly rates, job trends and role comparisons. It emphasizes performance and interactivity for large datasets and demonstrates a set of visualization techniques used to communicate insights effectively.

What you see in the demo GIF (Image 1) — visuals & techniques used
The demo specifically highlights the following visuals and interactive techniques (each bullet describes how it is used in the GIF):

- Large KPI / Card tiles
  - Job Count (big, formatted with "K"), Median Yearly Salary, Median Hourly Salary — used for high-level KPIs.
- Star Rating visual
  - Avg. Job Rating displayed with star icons (custom visual or formatted icon set) to show qualitative score at a glance.
- Line chart with trendline + range slicer
  - "What is trend of jobs in 2024?" — line chart showing monthly job counts, dashed trendline and a horizontal range slicer / timeline control for interactive time-window selection.
- Scatter / Bubble chart
  - "Hourly vs Median Salary" — plots job titles by median salary (x-axis) and hourly median (y-axis) with labeled points for each role to compare pay structures across roles.
- Horizontal Bar chart (clustered)
  - "Job Counts" — ranked horizontal bars for job count by title with data labels (e.g., 129K).
- Matrix / Table with conditional formatting and sparklines
  - "Job Stats" table showing Job Title, Job Count, Yearly Salary (with data bars/color), Hourly Salary and a mini-sparkline/trend icon column to show job-trend small visuals inline.
- Cards & Multi-row cards
  - Compact numeric summaries for quick reference and small grouped metrics.
- Slicers and dropdown filters
  - Job Title dropdown slicer, relative date selection, single/multi-select slicers for cross-filtering the visuals.
- Drillthrough button and bookmarked navigation
  - A "Job Drill Through" button and drillthrough functionality to navigate to detail pages for a selected job title.
- Cross-highlighting and interaction
  - Clicks on the bar chart or scatter highlight and filter other visuals in-context.
- Conditional formatting
  - Data bars and color scales in the matrix/table for immediate value comparison.
- Tooltips (report or page-level)
  - Hover tooltips with additional details; advanced tooltip pages may be used for richer context.
- Custom visuals (used where needed)
  - Examples visible in the demo: star rating icon visual, inline sparkline visual, any third-party visuals required for the star/sparkline appearance.
  - If you used specific custom visuals (Chiclet Slicer, Synoptic Panel, Sparkline, etc.), add their names to the repo readme and include installation notes.

Example DAX measures used (replace with your exact measures)
- Total Jobs = SUM('Jobs'[JobCount])
- Median Yearly Salary = MEDIAN('Jobs'[YearlySalary])
- Median Hourly Salary = MEDIAN('Jobs'[HourlySalary])
- Avg Job Rating = AVERAGE('Jobs'[Rating])
- Jobs This Year = CALCULATE([Total Jobs], YEAR('Jobs'[PostedDate]) = YEAR(TODAY()))
- Running Total Jobs = CALCULATE([Total Jobs], FILTER(ALLSELECTED('Date'), 'Date'[Date] <= MAX('Date'[Date])))

Data modelling approach
- Star schema where possible: one large fact table for job records + dimensions for Date, Job Title, Location, Company, and Category to optimize DAX performance.
- Minimize calculated columns; prefer measures for calculations and aggregations.
- Relationship direction: typically single-direction from dimension -> fact for clarity and performance.

Performance & optimization notes (for ~500K rows)
- Use Import mode for best interactive performance (unless DirectQuery is required).
- Keep visuals per page to a reasonable number — each visual issues queries.
- Use aggregated visuals for high-cardinality columns and avoid heavy iterators over rows in DAX.
- Consider incremental refresh for large, frequently updated datasets (Power BI Pro/Premium).
- Use variables in measures and avoid repeated calculations to speed queries.
- Disable unnecessary visual interactions when not needed.

How to open / run the report
1. Install the latest Power BI Desktop.
2. Download the dataset from the Drive link above and save locally.
3. Open the .pbix file in Power BI Desktop.
4. If prompted for the data file path, point to the local dataset.
5. Refresh the report to load the data.
6. If any custom visuals are missing, Power BI will prompt to download them from AppSource — install them when asked.

Custom visuals & external runtimes
- If you used R or Python visuals, the reader must have R or Python installed locally and the required packages.
- If you used third-party visuals (e.g., Chiclet Slicer, Sparkline visual, Star Rating), list them here and/or include any .pbiviz files or references to AppSource.

Contributing
- Fork the repository, create a branch, and open a pull request with a description of your changes.
- If you add or change visuals, include notes about versions and any runtime requirements.

License
- MIT License — see LICENSE for details.



---
What I did: I updated the README to specifically reflect the visuals and interactive techniques shown in your demo GIF (Image 1) and clarified dataset, modeling and performance instructions.  
Next: Attach the demo GIF (`demo.gif`) in the repository root (or confirm its filename) so the README demo image renders correctly. If you want, tell me the exact custom visual names or exact DAX measures you used and I will update the README to list them precisely.
```
