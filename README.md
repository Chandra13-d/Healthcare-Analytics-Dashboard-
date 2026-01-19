# 🏥 Breast Cancer Hospital Coverage & Recommendation Dashboard (India)

This project analyzes breast cancer treatment availability, cost, and quality across 100 oncology-capable hospitals in India.  
It combines scraped, researched, and manually validated healthcare signals to support benchmarking, accessibility analysis, and patient recommendation.

---

## 📌 1. Project Overview

Breast cancer care in India is unevenly distributed across cities and states, and patients often face challenges related to:

- Treatment availability (e.g., Radiation, Targeted Therapy)
- Cost affordability 
- Quality & outcomes (rating + review signals)
- Geographic accessibility

This dashboard provides visibility into these dimensions through:

✔ Coverage Analysis  
✔ Cost Insights  
✔ Quality Insights  
✔ Clinical Capability Scoring  

---

## 📊 2. Dataset Summary

**Total Hospitals:** 100  
**Geographic Coverage:** 20 States & 44 Cities  
**Disease Focus:** Breast Cancer (Oncology)

### **Key Features Collected**

| Category | Details |
|---|---|
| Hospital Info | Name, City, State, Website |
| Treatment Types | Surgery, Chemo, Radiation, Hormone, Immunotherapy, Targeted |
| Clinical Capability | Clinical Score (0–7) |
| Cost | Cost (Min–Max) |
| Quality Signals | Rating, Review Count |
| Facility Source | Govt / Private / Trust |

---

## 🧹 3. Data Engineering & Cleaning

Performed using **Python (Pandas)**

Key transformations:

- Treatment → Binary Flags (1/0)
- Cost conversion → `₹1.7L – ₹4.8L` → `170000 – 480000`
- Review normalization → `K` notation expanded
- Clinical Score Calculation → Sum of treatment flags
- Added Quality Index = Weighted rating + reviews
- Added Review Intensity per state

---

## 📈 4. Dashboard & KPIs (Power BI)

The solution is implemented in **Power BI** using measures and DAX modeling.

### **Primary Pages:**

#### **🗺 Page 1 — Coverage Insights**
- Total Hospitals
- Clinical Coverage %
- Treatment Availability %
- Hospital Distribution (State/City Maps)

#### **💰 Page 2 — Cost Insights**
- Avg / Median / Min / Max Cost
- Cost Distribution by State & City
- Cost Comparison

#### **⭐ Page 3 — Quality Insights**
- Avg Rating & Review Intensity
- Quality Index by State
- Cost vs Rating Scatter

---

## 🧮 5. Key Metrics & DAX Measures

Example DAX measures:

```DAX
Total Hospitals = COUNTROWS('Hospital')

Avg Rating = AVERAGE('Hospital'[rating])

Clinical Coverage % =
AVERAGEX(
    'Hospital',
    DIVIDE('Hospital'[clinical_score], 7)
)

Review Intensity =
SUM('Hospital'[review_count]) / [Total Hospitals]
