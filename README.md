# [TXST Library Circulation Analysis (FY14–FY24)](https://dataverse.tdl.org/dataset.xhtml?persistentId=doi:10.18738/T8/XDCXAT)
### Open Datathon 2026 Submission

**Team:** NAND
**Track:** Open Datathon (Library Data)

## 📌 Project Overview
This project analyzes a decade of Texas State University library circulation data to understand how student engagement with physical resources has changed post-COVID. By integrating internal circulation reports with IPEDS enrollment data, we identified a divergence between student population growth and physical collection usage.

Our analysis concludes with a **predictive model** for future circulation volume and a **prescriptive "Reallocation Matrix"** to help library administration prioritize shelf space for growing services (tech lending) over declining collections (DVDs/Juvenile).

## 📊 Key Findings
* **The Engagement Gap:** While enrollment has recovered to ~42k students, physical checkouts per student have dropped from **2.04 (FY20)** to **1.52 (FY24)**.
* **The Hardware Flip:** Traditional print circulation is stagnant, but equipment and laptop lending has increased by **66%** since FY2021.
* **Forecast:** Our linear trend model predicts annual circulation will stabilize at a new baseline of **~64,000 transactions/year** through FY2026, rather than returning to pre-2019 levels.

## 📂 Repository Structure
* `Analysis2.ipynb`: **[Main Analysis]** Jupyter notebook containing data extraction, cleaning, forecasting models (Holt's Linear/Polyfit), and visualization generation.
* `txst_library_visuals_v3.html`: Interactive HTML dashboard summarizing the project's descriptive, predictive, and prescriptive analytics.
* `data/`: Contains the raw Excel reports (FY15-FY24) and IPEDS enrollment CSVs.
* `visuals/`: Directory containing the high-resolution charts used in our poster (Forecast, Matrix, Engagement Gap).

## 🛠 Methodology
1.  **Data Cleaning:** We extracted "Annual Total" and "Patron Group" data from 10 years of Excel reports. To ensure accuracy, we manually verified key aggregate numbers against the original source PDFs to correct for inconsistent semester labeling in older files.
2.  **Normalization:** We calculated "Circulation Velocity" (Checkouts divided by Enrollment) to isolate behavioral changes from simple population growth.
3.  **Modeling:** We used a linear regression model on the post-COVID recovery period (FY21–FY24) to forecast short-term trends (FY25–FY26), as pre-2020 data no longer reflects current usage patterns.

## ⚖️ AI & Integrity Statement
* **Code Assistance:** Python scripts for data visualization and cleaning were drafted with the assistance of GitHub Copilot and Claude.
* **Data Verification:** All data points used in the final analysis (enrollment numbers, annual totals) were **manually verified** by team members to ensure 100% accuracy.
* **Analysis:** The research questions, strategic recommendations, and final interpretations are the original work of the team.
