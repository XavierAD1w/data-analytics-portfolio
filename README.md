# 🗳️Rivers State 2023 Governorship Election: A Strategic Data Analytics Case Study
> Comprehensive Evaluation of Electoral Logistics, Party Performance, and Voter Behavior using Power BI, Excel, and Power Query.

---

##  📑Table of Contents

- [Project Overview](#project-overview)
- [Project Objectives](#project-objectives)
- [Data Source and Quality Audit](#data-source-and-quality-audit)
- [Technical Stack](#technical-stack)
- [Data Analysis Process (ETL)](#data-analysis-process-etl)
- [Strategic Results and Visualization](#strategic-results-and-visualization)
- [Identified Problems and Data-Driven Solutions](#identified-problems-and-data-driven-solutions)
- [DAX Logic and Measures](#dax-logic-and-measures)
- [Limitations and Future Scope](#limitations-and-future-scope)
- [Conclusion](#conclusion)
- [About the Author](#about-the-author)

---
## Project Overview

### 🌍 Background
The **2023 Rivers State Governorship Election** was a pivotal moment in Nigeria’s democratic landscape, characterized by the deployment of new electoral technologies (BVAS) and a highly competitive multi-party environment. Rivers State, being a major economic hub in the South-South region, presents a complex case study of voter behavior, regional party loyalty, and administrative logistics across its 23 Local Government Areas (LGAs).

### 🎯 The Challenge
Despite high registration numbers, previous electoral cycles have been marred by **voter apathy**, **logistical delays**, and **high invalidation rates**. For analysts and stakeholders, the core challenge is to identify precisely where the "participation leakages" occur:
* Is the low turnout due to a lack of interest, or are there specific LGAs where the accreditation process is failing?
* Are rejected votes scattered randomly, or are they concentrated in specific hotspots that require targeted voter education?

### 💡 The Solution
This project leverages **Power BI** to transform raw, tabular election data into an interactive, geospatial intelligence dashboard. By applying a strategic data lens, this analysis:
* **Quantifies the "Participation Funnel":** Visualizes the drop-off from 3.5M+ Registered Voters to the final Accredited count.
* **Diagnoses Administrative Friction:** Isolates LGAs with disproportionately high rejected ballots (e.g., Gokana and PHC) to create a "Voter Education Roadmap."
* **Maps Political Dominance:** Provides a clear geographic visualization of party strongholds, allowing for a deeper understanding of the state’s political "DNA."

### 📈 Key Impact
By the end of this documentation, users will see how raw electoral data can be used to generate **actionable governance insights**. This project doesn't just show "who won"; it shows **how the election functioned**, providing a blueprint for data-driven electoral reform in Rivers State.

---
![Election map](Election%20Dashboard.png)

## Project Objectives
The primary goal of this documentation is to present a diagnostic view of the **2023 Rivers State Governorship Election**. Rather than just reporting numbers, this project aims to:
* **Quantify the Participation Gap:** Analyze the delta between registration and actual turnout.
* **Map Political Geography:** Identify strongholds for the PDP, APC, SDP, and LP across 23 LGAs.
* **Audit Administrative Integrity:** Highlight hotspots for rejected ballots and accreditation bottlenecks to influence future policy.

## Data Source and Quality Audit
The dataset consists of a detailed breakdown of electoral returns across the **23 Local Government Areas (LGAs)** of Rivers State. 
* **Key Entities:** Registered Voters, Accredited Voters, TVV (Total Valid Votes), and Rejected Votes.
* **Party Metrics:** Performance data for 18 political parties.
* **Integrity Validation:** A cross-reference audit was performed to ensure that `Valid Votes + Rejected Votes = Total Votes Cast`.

## Technical Stack
* **Power BI Desktop:** Used for data modeling, geospatial heat mapping, and interactive dashboarding.
* **Power Query:** Employed for ETL (Extract, Transform, Load) processes, specifically for unpivoting party data and standardizing LGA names.
* **Microsoft Excel:** Utilized for initial data profiling and audit checks.

---

## Data Analysis Process (ETL)
The transformation phase was critical to ensuring the accuracy of the geospatial visuals:
1. **Extraction:** Ingested the raw CSV dataset.
2. **Transformation:** 
    * Standardized LGA names (e.g., converting "PHC" to "Port Harcourt City") for 100% map coverage.
    * Replaced null/placeholder values with `0` for accurate aggregation.
3. **Modeling:** Developed a star schema by separating categorical LGA data from numerical voting results.

---

## Strategic Results and Visualization

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

## Identified Problems and Data-Driven Solutions

### Problem 1: Ballot Invalidation Hotspots (The Gokana/PHC Case)
* **Observation:** Gokana and Port Harcourt City recorded significantly higher rejected votes (1,000+ each) compared to the state average.
* **Data-Driven Solution:** **Targeted Voter Education.** The data suggests these are high-engagement zones where the voting process fails at the thumbprint stage. INEC should prioritize these LGAs for voter education and on-the-spot assistance during future elections.

### Problem 2: Critical Turnout Deficit in Populous LGAs
* **Observation:** Major urban LGAs like **Obio-Akpor** and **Khana** showed turnout rates below 10%.
* **Data-Driven Solution:** **Logistical Audit.** This gap indicates either severe voter apathy or a failure in the timely deployment of BVAS machines. Strategic decentralization of distribution centers and contingency planning for equipment failure are recommended.

---

## DAX Logic and Measures
To drive the insights in the Power BI dashboard, the following measures were created:

```dax
// Measure for Turnout Ratio
Turnout % = DIVIDE(SUM('Results'[Accredited Voters]), SUM('Results'[Registered Voters]), 0)
```

// Measure for Rejection Impact
---

## Limitations and Future Scope
While this analysis provides a high-level strategic overview, several constraints must be acknowledged to maintain data integrity and context:

* **Granularity Constraints:** The current dataset is aggregated at the **LGA level**. Without Ward-level or Polling Unit-level data, we cannot pinpoint specific communities where technical failures occurred.
* **Lack of Qualitative Context:** The data quantifies *what* happened but does not explain *why*. Factors such as localized security incidents, weather conditions, or transportation logistics are not covered.
* **Snapshot Analysis:** This study focuses exclusively on the 2023 cycle. A longitudinal study comparing these results to the 2015 and 2019 elections would be required to identify long-term political trends.
* **Demographic Blindspots:** The dataset lacks voter age and gender metrics, preventing an analysis of how the "Youth Vote" or "Gender Gap" influenced the final outcome.

---

## Conclusion
The strategic analysis of the **2023 Rivers State Governorship Election** highlights a critical paradox: while the state possesses a massive registered voter base, the actual "voice" reflected in the results was limited by low turnout in several populous LGAs and localized ballot invalidation issues.

The data-driven evidence points toward a need for **surgical administrative reforms**. By addressing the logistical bottlenecks in populous LGAs like Obio-Akpor and implementing hyper-local voter education, future cycles can be made more representative.

---

## About the Author
**[Denzel Ayogu]**

Data Analyst & Visualization Specialist — Focusing on transforming complex socio-political data into actionable governance insights.

---
