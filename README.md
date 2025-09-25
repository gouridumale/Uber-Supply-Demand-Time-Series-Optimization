# Uber-Supply-Demand-Time-Series-Optimization

## Project Objectives
- Diagnose mismatches between **rider demand** (`eyeballs`) and **driver supply** (`unique drivers`).
- Perform **time series rolling analysis** to detect spikes, busiest intervals, and supply shortfalls.
- Calculate **efficiency metrics** (e.g., trips per driver ratio, weekend zero-supply share).
- Identify **strategic scheduling changes** for optimized fleet allocation.
- Visualize demand–supply dynamics to validate hypotheses and operational definitions.

---

## Dataset
- **Size:** 336 rows × 7 columns  
- **Columns:** date, time local, requests, completed trips, unique drivers, eyeballs, zeros  
- **Period:** 2 weeks of Uber operational data  
- **Notes:**  
  - 321 missing values in the `date` column (imputed with forward fill).  
  - Minor inconsistencies corrected (e.g., trailing spaces in column names).  

---

## Methodology
### Data Pre-processing
- Verified data quality, standardized column names, and inspected types (`.info()`).
- Imputed missing values in `date` using **forward fill (`ffill`)** for time series continuity.
- Engineered a combined **`datetime` index** to enable rolling window calculations.
- Filtered rows with zero drivers to prevent division errors.

### Analysis & Modeling
- Applied **rolling sum windows** (8h, 24h, 72h) to detect demand peaks and supply shortfalls.
- Computed the **weighted average trips-per-driver ratio** (8.83).
- Segmented data by **day of week + time** to reveal that **44.86% of “zeros”** occurred on weekends.
- Pinpointed the **busiest 8h and 24h periods** and the **lowest supply-to-demand ratio hour**.

### Business Insights
- Optimal hour to add **five drivers**: **23:00–00:00**, when demand far exceeds supply.
- Re-defined Uber’s **operational day boundary** from midnight to **4–5 a.m.**, aligning with natural demand troughs.
- Validated that driver supply does **not always rise with demand**, disproving a common assumption.

---

## Results & Key Findings
- Highest completed trips in 24h: **278 trips**.  
- Weighted trips-per-driver ratio: **8.83**.  
- Weekend “zero supply” share: **44.86%**.  
- Busiest demand interval: **Sep 21, 5 p.m. – Sep 22, 1 a.m.**.  
- Operational “end day” shifted to **4–5 a.m.**.  

---

## Resume Highlights (STAR-style Bullets)
- Designed an end-to-end data science workflow on Uber’s operational dataset to evaluate **rider demand vs driver supply**.  
- Engineered a **time-indexed dataset**, imputed missing values, and implemented **rolling time series windows** (8h, 24h, 72h) for demand forecasting.  
- Quantified **peak demand spikes**, **weighted trips-per-driver ratio (8.83)**, and revealed **weekend zero-supply concentration (44.86%)**.  
- Identified the **hour with lowest supply-to-demand ratio (23:00–00:00)** and re-defined the **operational boundary (4–5 a.m.)** to optimize scheduling.  
- Visualized supply–demand dynamics with Matplotlib, delivering **business insights for forecasting, resource allocation, and operational optimization**.  

---
