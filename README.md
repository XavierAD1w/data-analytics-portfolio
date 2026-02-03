# 🗳️ Rivers State 2023 Governorship Election: A Strategic Data Analytics Case Study
> **Comprehensive Evaluation of Electoral Logistics, Party Performance, and Voter Behavior using Power BI, Excel, and Power Query.**

---

## 📋 Table of Contents
1. [Project Objectives](-#-project-objectives)
2. [Data Source & Quality Audit](-data-source--quality-audit)
3. [Technical Stack](-technical-stack)
4. [Data Analysis Process (ETL)](-data-analysis-process-etl)
5. [Strategic Results & Visualization](-strategic-results--visualization)
6. [Identified Problems & Data-Driven Solutions](-identified-problems--data-driven-solutions)
7. [DAX Logic & Measures](-dax-logic--measures)
8. [Limitations & Future Scope](-limitations--future-scope)
9. [Conclusion](-conclusion)

---
![Election map](Election%20Dashboard.png)

## 🎯 1. Project Objectives
The primary goal of this documentation is to present a diagnostic view of the **2023 Rivers State Governorship Election**. Rather than just reporting numbers, this project aims to:
* **Quantify the Participation Gap:** Analyze the delta between registration and actual turnout.
* **Map Political Geography:** Identify strongholds for the PDP, APC, SDP, and LP across 23 LGAs.
* **Audit Administrative Integrity:** Highlight hotspots for rejected ballots and accreditation bottlenecks to influence future policy.

## 📂 2. Data Source & Quality Audit
The dataset consists of a detailed breakdown of electoral returns across the **23 Local Government Areas (LGAs)** of Rivers State. 
* **Key Entities:** Registered Voters, Accredited Voters, TVV (Total Valid Votes), and Rejected Votes.
* **Party Metrics:** Performance data for 18 political parties.
* **Integrity Validation:** A cross-reference audit was performed to ensure that `Valid Votes + Rejected Votes = Total Votes Cast`.

## 🛠️ 3. Technical Stack
* **Power BI Desktop:** Used for data modeling, geospatial heat mapping, and interactive dashboarding.
* **Power Query:** Employed for ETL (Extract, Transform, Load) processes, specifically for unpivoting party data and standardizing LGA names.
* **Microsoft Excel:** Utilized for initial data profiling and audit checks.

---

## ⚙️ 4. Data Analysis Process (ETL)
The transformation phase was critical to ensuring the accuracy of the geospatial visuals:
1. **Extraction:** Ingested the raw CSV dataset.
2. **Transformation:** * Standardized LGA names (e.g., converting "PHC" to "Port Harcourt City") for 100% map coverage.
    * Replaced null/placeholder values with `0` for accurate aggregation.
3. **Modeling:** Developed a star schema by separating categorical LGA data from numerical voting results.

---

## 📊 5. Strategic Results & Visualization

### A. Total Votes Cast per LGA
The following visualization highlights the distribution of valid votes across the state, identifying the high-volume voting centers versus rural clusters.

![Election map](Election%20map.png)

### B. High-Level Performance Metrics
| LGA | Registered Voters | Accredited Voters | Rejected Votes | Turnout % |
| :--- | :--- | :--- | :--- | :--- |
| **Gokana** | 145,566 | 40,702 | 1,235 (High) | 27.9% |
| **Obio-Akpor** | 684,812 | 67,196 | 764 | 9.8% |
| **Port Harcourt City** | 502,370 | 47,605 | 1,094 | 9.5% |

---

## 💡 6. Identified Problems & Data-Driven Solutions

### **Problem 1: Ballot Invalidation Hotspots (The Gokana/PHC Case)**
* **Observation:** Gokana and Port Harcourt City recorded significantly higher rejected votes (1,000+ each) compared to the state average.
* **Data-Driven Solution:** **Targeted Voter Education.** The data suggests these are high-engagement zones where the voting process fails at the thumbprint stage. INEC should prioritize these LGAs for community-led ballot marking workshops.

### **Problem 2: Critical Turnout Deficit in Populous LGAs**
* **Observation:** Major urban LGAs like **Obio-Akpor** and **Khana** showed turnout rates below 10%.
* **Data-Driven Solution:** **Logistical Audit.** This gap indicates either severe voter apathy or a failure in the timely deployment of BVAS machines. Strategic decentralization of distribution centers in these large LGAs is recommended to speed up the morning-of accreditation.

---

## 🧪 7. DAX Logic & Measures
To drive the insights in the Power BI dashboard, the following measures were created:
```dax
// Measure for Turnout Ratio
Turnout % = DIVIDE(SUM('Results'[Accredited Voters]), SUM('Results'[Registered Voters]), 0)
```
// Measure for Rejection Impact
---

## ⚠️ 8. Limitations & Future Scope
While this analysis provides a high-level strategic overview, several constraints must be acknowledged to maintain data integrity and context:

* **Granularity Constraints:** The current dataset is aggregated at the **LGA level**. Without Ward-level or Polling Unit-level data, we cannot pinpoint specific communities where technical failures (BVAS) or voter suppression may have occurred.
* **Lack of Qualitative Context:** The data quantifies *what* happened but does not explain *why*. Factors such as localized security incidents, weather conditions, or transportation logistics are not captured in the numerical dataset.
* **Snapshot Analysis:** This study focuses exclusively on the 2023 cycle. A longitudinal study comparing these results to the 2015 and 2019 elections would be required to identify long-term political shifts or permanent voter apathy.
* **Demographic Blindspots:** The dataset lacks voter age and gender metrics, preventing an analysis of how the "Youth Vote" or "Gender Gap" influenced the final outcome.

---

## 🏁 9. Conclusion
The strategic analysis of the **2023 Rivers State Governorship Election** highlights a critical paradox: while the state possesses a massive registered voter base, the actual "voice" reflected in the valid votes is significantly diminished by low turnout and high rejection rates.

The data-driven evidence points toward a need for **surgical administrative reforms**. By addressing the logistical bottlenecks in populous LGAs like Obio-Akpor and implementing hyper-local voter education in high-rejection zones like Gokana, the electoral commission can bridge the participation gap. Ultimately, this Power BI dashboard serves not just as a historical record, but as a roadmap for improving the integrity and inclusivity of future democratic exercises in Rivers State.

---

## 👨‍💻 About the Author
**[Your Name]** *Data Analyst & Visualization Specialist* Focusing on transforming complex socio-political data into actionable governance insights.



---
