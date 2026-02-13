# TXST Datathon — Library Resource Reallocation (Datasets + Reproducible Analysis)

## Project Summary
This dataset package supports a TXST Datathon analysis of how Texas State University Library circulation has shifted over time (physical materials vs. technology/equipment demand), and what that implies for reallocating library resources (space, access model, service focus).

**Core idea:** Use circulation patterns as a demand signal to identify which categories are declining and which are growing, then recommend reallocation (e.g., storage/ARC for steeply declining physical collections; reinvestment for growing tech demand).

---

## Files Included (What each file is)

### 1) Raw circulation workbook (source)
**`Datathon-Library Circulation Data (1).xlsx`**  
Original circulation workbook provided for the datathon.  
Contains fiscal-year-based circulation tables (including location-level tables used to recover FY2017 baseline values).

**Used for:**
- FY2017 baseline circulation by location (legacy collections)
- Cross-checking against cleaned outputs

---

### 2) Cleaned analysis-ready workbook
**`TXST_Library_Circulation_Enrollment_Clean.xlsx`**  
Cleaned and structured workbook used directly by the notebook.

**Key sheets used:**
- **Annual Summary** — annual totals over time (macro trend)
- **Circulation by Type** — categories such as Print/Media, Reserve, Equipment/Keys, Laptops/Computers (recent years)
- **Circulation by Location** — location/collection breakdown across recent years
- **Circulation by Patron** — patron group demand patterns (optional supporting analysis)

**Notes on cleaning:**
- Standardized year columns and numeric types
- Aggregated and reshaped tables for easier analysis
- Produced derived tables (e.g., annual summaries and pivots) where helpful

---

### 3) Enrollment dataset (external reference)
**`IPEDS Enrollment Data 2019-2024.csv`**  
IPEDS enrollment data (2019–2024) used to compute per-capita circulation metrics (e.g., circulation per student) and contextualize trends.

**Used for:**
- Per-capita demand trends (circulation / enrollment), where applicable

---

### 4) Analysis notebook (reproducibility artifact)
**`Analysis.ipynb`**  
Jupyter notebook that reproduces:
- data reads from the cleaned workbook + (optionally) raw workbook
- visualizations
- trend metrics (YoY change / CAGR depending on time window)
- reallocation prioritization logic

> If Dataverse only accepts datasets, this notebook is included as a reproducibility artifact. The core “dataset” files are the .xlsx and .csv files listed above.

---

## Key Metrics (How the analysis is computed)
To keep the analysis transparent and not misleading, trends are computed using:

- **YoY % Change (FY23→FY24)** for short-window “demand signals”
- **Annualized % Change (CAGR)** for longer windows (e.g., FY17→FY24 when available)

**Why this matters:** Some categories (especially technology/equipment) only exist for a shorter time window in the structured sheets. Long-window and short-window insights are shown separately to avoid mixing inconsistent time ranges.

---

## How to Reproduce the Results
1) Place the following files in the same folder:
   - `Analysis.ipynb`
   - `TXST_Library_Circulation_Enrollment_Clean.xlsx`
   - `Datathon-Library Circulation Data (1).xlsx`
   - `IPEDS Enrollment Data 2019-2024.csv`

2) Open the notebook:
   - JupyterLab / Jupyter Notebook / VS Code

3) Run the notebook top-to-bottom.
   - Recommended: **Restart Kernel → Run All** to ensure a clean run.

**Python packages used (typical):**
- pandas
- numpy
- matplotlib
- openpyxl

---

## What the dataset supports (analysis questions)
This dataset package can support:
- How circulation has changed over time (overall and per-capita)
- Which types of items are growing in demand (equipment/technology) vs. declining (some physical categories)
- Which locations/collections show persistent declines vs. sustained demand
- Which patron groups are driving usage changes
- Evidence-based resource reallocation recommendations (space + access model)

---

## Limitations / Integrity Notes
- **Circulation is a demand proxy**, not direct financial “investment.”  
  Recommendations focus on aligning **space, access model (e.g., ARC/storage), and service emphasis** to observed demand.
- Some categories exist only in recent years; short-window results are explicitly labeled as **demand signals** rather than long-run trends.
- Any cross-domain comparisons (e.g., enrollment vs. circulation) are treated as context, not causal claims.

---


If you reuse or adapt this dataset package, please cite the original datathon source workbook and this derived cleaned workbook accordingly.
