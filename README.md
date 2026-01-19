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


🔍 6. Key Insights
From initial analysis:
📍 Coverage
Tier-1 metros dominate oncology capacity (Mumbai/Delhi/Bangalore/Kolkata)

💉 Capability
Surgery & Chemo available >95%
Radiation ~63%
Immuno/Targeted <20% (advanced therapy gap)

💰 Affordability
Private cost varies 4x–6x between states
Some Tier-2 cities offer lower cost at similar quality

⭐ Quality

Higher cost ≠ always higher rating (brand premium effect)

🧾 7. Tech Stack
Layer	Tools
Data Collection	Selenium, Requests, Research
Cleaning	Python (Pandas, Regex)
Dashboard	Power BI
Modeling	DAX
Use Case	Healthcare Analytics
🎯 8. Potential Extensions

Future enhancements:

ML-based patient recommendation
Insurance pricing simulation
Outcome prediction modeling
API or live hospital feeds
Add more cancer types (Pancreatic / Lung / GI)

🔗 9. Use Cases

This project can support:

✔ Oncology Planning
✔ Cost Benchmarking
✔ Insurance Underwriting
✔ Patient Navigation
✔ Healthcare Equity Research

👤 10. Author

Name: Chandra D
Role: Data Analyst
Domain Interests: Healthcare, ML, Data analyst, Data science, PowerBI Developer

📬 Contact / Collaboration

If you work in:

Healthcare analytics
Insurance
Biotech
Hospital IT
Clinical data

Open to meaningful collaboration & learning.

LinkedIn:(https://www.linkedin.com/in/chandra-d-7a9b93176/)
Email: preethamchandu1308@gmail.com
