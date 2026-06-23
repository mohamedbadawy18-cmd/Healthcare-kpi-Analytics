# 🏥 Healthcare KPI Analytics
> Identifying bed allocation inefficiencies, staff workload imbalances, and patient fall risk patterns across 500,000 patient records

---

## 📌 Project Overview

| | |
|---|---|
| **Industry** | Healthcare / Hospital Operations |
| **Tools** | Python (EDA) · Power BI (Dashboard) |
| **Dataset Size** | 500,000 patient admissions · 5 departments · 2 years |
| **Dashboard Pages** | 3 pages — Overview · Treatment Efficiency · Patient Safety & Recommendations |
| **Type** | Portfolio Project |

---

## 🎯 Business Problem

A multi-department hospital needed to understand three operational risk areas:

1. Are beds being allocated efficiently across departments, and is occupancy sustainable?
2. Is staff workload (nurse-to-patient ratios) balanced, or are specific departments overstretched?
3. Where are patient fall incidents concentrated, and which patient groups are highest-risk?
4. How much treatment-timeline inefficiency exists between ideal and actual length of stay?

---

## 📊 Dataset

- **Source:** Synthetic dataset modeled on realistic hospital operations patterns
- **Size:** 500,000 patient admission records across 5 departments (Emergency, ICU, Surgery, Pediatrics, General Medicine)
- **Supporting tables:** Daily bed occupancy and staff workload logs (3,655 department-day records each)
- **Time range:** 2 years (2024–2025)

**Data Model:** Star schema using a composite `Dept_Date_Key` (Department + Date) to link patient-level admission data to department-day-level occupancy and staffing data — since these operate at different levels of granularity.

---

## 🔍 Methodology

### Phase 1 — Data Cleaning & EDA (Python)
- Engineered `Age_Group` bins and the `Dept_Date_Key` composite join key
- Calculated department-level occupancy, workload, and fall-rate aggregates using `pandas groupby`
- Built 4 exploratory visualizations (occupancy, workload, stay efficiency, fall rates) with `matplotlib`/`seaborn`

### Phase 2 — Dashboard Build (Power BI)
- Modeled a star schema with Many-to-One relationships via `Dept_Date_Key`
- Built 3 dashboard pages combining 6 different visual types (Gauge, Treemap, Donut, Line, Scatter, Waterfall) to avoid visual repetition
- Added interactive slicers for Department, Year, and Age Band

---

## 💡 Key Findings

| # | Finding | Data |
|---|---|---|
| 1 | **Overall fall incident rate** | 2.05% across 500,000 patients (10,240 incidents) |
| 2 | **ICU has the highest fall rate** | **3.51%** — nearly double the hospital-wide average |
| 3 | **ICU runs hottest on occupancy** | **91.1%** average bed occupancy — highest of all 5 departments |
| 4 | **General Medicine has the weakest staffing ratio** | **6.01** patients per nurse — highest patient load per caregiver |
| 5 | **Elderly patients are at significantly higher fall risk** | Patients 65+ fall at **3.53%** vs. **1.00%** for patients under 18 |
| 6 | **Treatment timelines run 17% over ideal** | Length of stay inefficiency of **17.01%** hospital-wide |
| 7 | **More than 1 in 3 patients face discharge delays** | **37.89%** discharge delay rate, concentrated in bed-availability bottlenecks |
| 8 | **ICU and General Medicine drive most of the inefficiency** | Largest contributors in the per-department inefficiency waterfall |

---

## 📈 Dashboard Pages

### Page 1 — Overview
5 KPI cards (Total Patients, Fall Rate, Discharge Delay Rate, Avg Length of Stay, Avg Occupancy Rate) + Occupancy trend line over time + Gauge vs. 85% target + Donut of fall incidents + Treemap of patient volume by department + Bar chart of occupancy by department

### Page 2 — Treatment Efficiency
KPI cards (Overall Inefficiency %, Avg Ideal vs Actual Stay) + Scatter plot comparing ideal vs. actual stay per department + Waterfall chart of discharge delay contribution by department + Detailed comparison table + Ribbon chart of stay trends by department

### Page 3 — Patient Safety & Recommendations
KPI cards (Inefficiency %, High-Risk Fall Rate 65+, Occupancy Rate) + Line chart of fall rate by age band + Bar chart of fall rate by department + Three written recommendations addressing the top operational risks

---

## ✅ Recommendations

### 1. 🔴 Strengthen ICU Fall Prevention Protocols
ICU records the highest fall incident rate at 3.51% — nearly double the hospital-wide average — combined with the highest bed occupancy (91.1%). Recommend hourly rounding checklists and bed-exit sensor alarms specifically for ICU.

### 2. 🟡 Implement Targeted Monitoring for Patients Aged 65+
Patients 65+ fall at more than triple the rate of patients under 18 (3.53% vs. 1.00%). Age-based risk scoring at admission, paired with proximity alerts for this group, could reduce incidents without added staffing costs.

### 3. 🔵 Resolve the Discharge Process Bottleneck
38% of patients experience discharge delays, driving a 17% increase in length of stay beyond clinically ideal timelines. This points to administrative or bed-availability friction. A dedicated discharge coordinator per department could recover meaningful bed capacity.

---

## 📁 Repository Structure

```
├── README.md
├── eda_analysis.py                  ← Python EDA script (4 charts)
├── charts/
│   ├── chart1_occupancy.png
│   ├── chart2_workload.png
│   ├── chart3_stay_efficiency.png
│   └── chart4_falls.png
└── data/
    ├── patient_admissions.csv       ← 500,000 rows
    ├── bed_occupancy.csv
    └── staff_workload.csv
```

---

## 🛠 Tools Used

- **Python** (pandas, matplotlib, seaborn) — Data generation, EDA, visualizations
- **Power BI** — Star schema data modeling, DAX measures, 3-page interactive dashboard with diverse visual types

---

## 👤 About

This project simulates a real-world hospital operations analytics scenario, built end-to-end from a synthetically generated dataset modeled on realistic departmental risk profiles, occupancy patterns, and patient demographics.

📧 [Your Email] | 💼 [Your LinkedIn URL] | 🐙 [Your GitHub URL]
