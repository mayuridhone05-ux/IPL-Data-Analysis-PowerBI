# 🏏 IPL Analytics & Strategy Dashboard

An end-to-end business intelligence and data engineering portfolio project analyzing historical Indian Premier League (IPL) data. This project features both a robust Power BI data model and a custom-built, fully responsive interactive web application clone.

**🌐 Live Interactive Web App**
Don't just look at screenshots—interact with the charts, change filters, and explore the datasets in real-time right from your browser!

**[➡️ 👉 CLICK HERE TO OPEN THE LIVE INTERACTIVE DASHBOARD 👈](https://mayuridhone05-ux.github.io/IPL-Data-Analysis-PowerBI/)**

---

## 📌 Project Overview & Key Files

This repository contains the complete analytical lifecycle of the IPL performance dataset:

* **The Power BI Core:** The primary desktop analysis file with advanced visual dashboards is saved as `power bi project.pbix`.
* **The Project Workflow:** A detailed breakdown of the engineering steps, data cleaning methodology, metrics design, and delivery phases is documented in `ipl-project-work-flow (1).docx`.
* **The Custom Web App:** An automated, single-page interactive replica built inside the `docs/` folder to host a live GUI experience using Chart.js on GitHub Pages.

---

## 🎯 Business Objective & Problems Solved

IPL franchises, coaching staff, and athletic evaluators rely heavily on objective data models to make high-stakes recruitment and on-field decisions. This dashboard answers critical stakeholder questions:

* **Franchise Dominance:** Which franchises perform most consistently across multiple seasons and distinct playing conditions?
* **Toss Bias:** How significantly does winning the toss influence match outcomes, and what is the optimal toss decision per venue?
* **Venue & Ground Indexing:** Which stadiums act as high-probability "lucky" venues for specific team structures?
* **Player Consistency:** Who are the high-impact boundary hitters (Sixes/Fours) and dominant wicket-taking bowlers?

---

## 🛠️ Data Architecture & Workflow

### Data Architecture Flow

```text
[Raw Datasets (Matches & Deliveries)] 
               │
               ▼ (Power Query / ETL)
[Data Cleaning & Standardizing Team Names] 
               │
               ▼ (Star Schema Modeling)
[Relational Model: matches.id (1) ↔ deliveries.match_id (*)]
               │
               ▼ (DAX Measures & Chart.js Computations)
[Interactive GUI / Visual Presentation Layer]

```

### 1. Robust ETL & Data Cleaning

* **Historical Team Alignment:** Standardized team naming conventions across historic years (e.g., mapped legacy "Delhi Daredevils" records into the modern "Delhi Capitals" structure to prevent split analytics).
* **Data Type Enforcement:** Verified correct metadata typing for dates, run tallies, wicket values, and text descriptors.
* **Integrity Audits:** Cleaned nested null values and removed redundant duplicate rows to preserve baseline statistics.

### 2. Star Schema Data Modeling

A highly efficient relational star schema was built by linking the core datasets together. The crucial link in our model is:

* **Relationship:** `matches.id` (One) ↔ `deliveries.match_id` (Many)
* **Impact:** This structural connection links individual ball-by-ball delivery events straight to global match results.

### 3. Key Performance Indicators (KPIs) & Calculated Measures

* **Batting Performance:** Evaluated Strike Rates, Boundaries Hit (Total Fours/Sixes), and individual run accumulations.
* **Bowling Performance:** Quantified total Bowler Wickets, Runs Conceded, and Economy Rates:

$$\text{Economy Rate} = \frac{\text{Runs Conceded}}{\text{Overs Bowled}}$$


* **Team Strategy:** Calculated overall Win Rates, Toss Win Rates, and Chase Success Indices.

---

## 🖥️ Dashboard Previews & Visual Replication

### 1. Team Analysis Page

*Visualizes historical franchise success, fielding/batting distributions, boundary frequency, and fielder catches.*

### 2. Player Analysis Page

*Tracks player longevity, top boundary contributors (sixes and fours), and consistent Match Winners.*

### 3. Venue & Match Analysis Page

*Displays lucky stadiums, toss outcomes, city host frequencies, and total runs trended across seasons.*

---

## 💡 Strategic Business Insights & Recommendations

* **Tailor Strategy by Ground:** Visualizations indicate that chasing teams have a distinct advantage in specific grounds (such as Eden Gardens and Chinnaswamy). Captains should prioritize selecting an extra bowler and electing to field first upon winning the toss in these locations.
* **Smart Squad Building:** Recruit players whose data displays high consistency coefficients over multiple seasons, rather than focusing on highly expensive marquee names whose metrics fluctuate wildly.
* **Leverage Venue-Specific Bowl Plans:** Align pace and spin ratios based on historic pitch behavior. Certain venues heavily favor defensive, slower bowling styles while others are batting-friendly express tracks.

---

## 👨‍💻 Technical Deployment Note
To maximize portfolio visibility, the Power BI layouts inside `power bi project.pbix` were recreated using standard frontend technologies (HTML5, CSS3, JavaScript, and Chart.js). This allows anyone, including recruiters without a Power BI desktop license, to interact with the responsive dashboard elements directly on the web.
