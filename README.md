# Power BI Data Job Dashboard — Without Power Query

A polished, production-ready Power BI report analyzing job market data at scale (~500K rows) **without using Power Query**. All data shaping and logic are performed via DAX and Power BI data modeling. The repository includes the dashboard `.pbix` file, a dataset link, and a demo GIF showing live interactions and visuals.

---

## 🚀 Demo

<img width="1441" height="810" alt="image" src="https://github.com/user-attachments/assets/48dcf44c-df74-47fd-80bd-1a2b9fb96b83" />

<img width="1438" height="805" alt="image" src="https://github.com/user-attachments/assets/e9472dbc-3cf1-4c3c-b916-faad601d559a" />


*Above: Key dashboard visuals and interactive features are shown in the attached demo GIF (`PowerBIDDataJobDemo.gif`).*

---

## 📦 Repository Contents

- `Power-BI-Data-Job-Dashboard-Without-Power-Query.pbix` — Main dashboard file
- `demo.gif` — Animated preview of the dashboard
- `README.md` — This documentation
- `LICENSE` — MIT License

---

## 📊 Dataset

- **Source:** [Big Data CSV (~500K rows)](https://drive.google.com/file/d/1CQSsnEuJYYA87YKOeJa5-Jf-CujsL3Z2/view?usp=sharing)
- **Format:** CSV (or compatible). Download and save locally.
- **Note:** **No Power Query transformations** were applied. Data is imported raw and modeled directly inside Power BI.

---

## 📝 Overview

This dashboard provides an executive and analytical view of job counts, salary medians, hourly rates, job trends, and role comparisons. It is designed for high performance and interactivity on large datasets, using advanced visualization and modeling techniques.

---

## 📈 Visualizations & Techniques Used

**The dashboard (see demo GIF) uses the following Power BI visuals and methods:**

- **KPI / Card Tiles:**  
  - Job Count, Median Yearly Salary, Median Hourly Salary (large numeric tiles)
- **Star Rating Visual:**  
  - Average Job Rating shown with star icons
- **Line Chart + Trend Line + Range Slicer:**  
  - Monthly job count trend (2024), interactive time selection
- **Scatter/Bubble Chart:**  
  - Hourly vs Median Salary comparison for each job title
- **Clustered Horizontal Bar Chart:**  
  - Job counts by title, ranked
- **Matrix/Table with Conditional Formatting and Sparklines:**  
  - Job stats table: Titles, counts, salaries, hourly rates, inline trend sparklines, data bars/colors
- **Cards & Multi-row Cards:**  
  - Grouped, compact KPI summaries
- **Slicers & Dropdown Filters:**  
  - Job Title dropdown, timeline/relative date slicers
- **Drillthrough Button & Navigation:**  
  - "Job Drill Through" button for role-specific detail pages
- **Cross-highlighting & Interaction:**  
  - Clicking visuals filters/highlights other visuals
- **Conditional Formatting:**  
  - Color scales, data bars/icons in tables/matrix
- **Tooltips (Report & Page Level):**  
  - Hover for additional context/details
- **Custom Visuals:**  
  - Star rating, inline sparkline, and any other AppSource visuals as needed
- **Bookmarks (if used):**  
  - Storytelling and navigation

*If you used additional custom visuals (e.g., Chiclet Slicer, Synoptic Panel, etc.), list them here for user reference.*

---

## 🧮 DAX Measures (Examples)

**Replace these with your actual DAX if needed:**
- `Total Jobs = SUM('Jobs'[JobCount])`
- `Median Yearly Salary = MEDIAN('Jobs'[YearlySalary])`
- `Median Hourly Salary = MEDIAN('Jobs'[HourlySalary])`
- `Avg Job Rating = AVERAGE('Jobs'[Rating])`
- `Jobs This Year = CALCULATE([Total Jobs], YEAR('Jobs'[PostedDate]) = YEAR(TODAY()))`
- `Running Total Jobs = CALCULATE([Total Jobs], FILTER(ALLSELECTED('Date'), 'Date'[Date] <= MAX('Date'[Date])))`

---

## 🗂️ Data Modeling Approach

- **Star Schema:** One large fact table (jobs) + dimensions (Date, Title, Location, etc.)
- **Calculated Columns:** Minimized for performance—prefer measures
- **Relationships:** Single-direction from dimension → fact tables

---

## ⚡ Performance & Optimization (Large Data)

- Use **Import mode** (unless DirectQuery needed)
- Limit visuals per page for query performance
- Aggregate high-cardinality columns in visuals
- Consider **incremental refresh** (Pro/Premium)
- Use variables in DAX, avoid repeated calculations
- Disable unneeded visual interactions

---

## 🛠️ How to Run / Open

1. **Install** latest Power BI Desktop.
2. **Download** dataset from the link above and save locally.
3. **Open** `.pbix` file in Power BI Desktop.
4. If prompted, point to the local dataset file.
5. **Refresh** data.
6. If custom visuals are missing, Power BI will prompt to install from AppSource.

---

## 🧩 Custom Visuals & Runtime

- If using **R/Python visuals**, install R/Python runtime and required packages.
- For custom visuals (e.g., Chiclet Slicer, Star Rating, Sparklines), ensure installation from AppSource.
- List any required `.pbiviz` files or AppSource links here.

---

## 🤝 Contributing

- Fork the repo, create a branch, and submit a pull request with a clear description.
- If adding/changing visuals, note versions and runtime requirements.

---

## 📄 License

MIT License — see `LICENSE` for details.

---

## 📬 Contact

**Author:** KavindaRajapaksha  
**GitHub:** [KavindaRajapaksha](https://github.com/KavindaRajapaksha)  
**Email:** rdks.kavinda@gmail.com

---

*Thank you for checking out the Power BI Data Job Dashboard! If you update the dashboard or use additional visuals/measures, please update the README accordingly!*
