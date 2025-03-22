# 🚲 Seoul Public Bicycle Sep 2023 Breakdown Rate Validation Report

## 1. Background

This report documents the additional analysis conducted to verify the **monthly breakdown rate data for 2023 and 2024** that was analyzed in the original project.

The previous project concluded that the breakdown rate in **September 2024 was high**, without closely examining the unusually **low breakdown rate in September 2023**. This omission left an important analytical gap.

Thus, the core objective of this analysis is to **validate whether the breakdown rate in September 2023 is reliable**, and to check whether **any errors occurred during the analysis process**.

---

## 2. Review & Reanalysis of Existing Data

### 1) Review of the Previous Project’s Findings

- The original project only compared the breakdown rates for September 2023 and September 2024, **without further investigating why September 2023 showed such a low rate.**
- We needed to verify whether **the low breakdown rate in September 2023** was truly reliable and whether any mistakes occurred in the analysis process.

### 2) Revalidation of September 2023 Data

- **Reprocessed the data using the same method as the original project:**
  - Downloaded the same dataset from the Seoul Open Data Portal
  - Performed the same data cleaning, including **removal of duplicate breakdown reports** and formatting

- **Result:** The recalculated breakdown rate matched the original project’s result → **No analysis error was found**
  
- **Cross-checking with alternative approaches:**
  - In addition to repeating the same method, we tried **alternative data sources and aggregation techniques**
  - The original analysis used **Station-Based Usage Data**, while this reanalysis also utilized **Per-Rental Usage Data**
  - **However, the total number of usage events differed significantly between datasets:**

| Dataset                  | Total Usage (Returns) |
|--------------------------|------------------------|
| Station-Based Usage Data | 44,488,134             |
| Per-Rental Usage Data    | 1,246,386              |
| Difference               | 43,241,748             |

#### Reason for the Gap:
- **Station-Based Usage Data** aggregates monthly rental/return counts per station
- **Per-Rental Usage Data** includes individual trip records with user and trip time info
- Therefore, **aggregating the Per-Rental dataset by month does not produce comparable figures**, making it **unsuitable for validation**

---

### 3) Breakdown Count vs. Usage Volume Analysis – Graph 1 (Dual Y-Axis)

- Instead of using breakdown rates directly, this analysis **visualized raw breakdown and return counts on a single graph**
- A **dual Y-axis (TWINX)** chart was used to separate return counts and breakdown counts for direct visual comparison

### Interpretation:
- Even with different visualization methods, the **sharp drop in breakdowns in September 2023** consistently appeared
- **Breakdown counts rose again in October**, suggesting a **specific factor may have suppressed breakdowns only in September**
- **Conclusion:** The anomaly is unlikely to be caused by analytical or data errors, but rather a genuine data phenomenon

---

### 4) Breakdown Count vs. Usage Volume Analysis – Graph 2 (Normalized)

- In addition to the previous graph, this version applied **Min-Max normalization (0–1 range)** to compare the metrics on equal scale
- Allowed a direct comparison between **breakdown reports** and **return volumes** over time

### Interpretation of Normalized Graph:
- Return counts (blue line) and breakdown reports (red dashed line) showed **similar patterns overall**
  - Generally, **higher usage correlates with more breakdowns**
  - Both values peaked in **May–June and October**
- **Only September breaks the pattern:**
  - Despite return counts staying level, **breakdown counts drop significantly**
  - This anomaly is consistent with findings from earlier analyses
- **Breakdowns surged again in October**, aligned with a rise in returns
- While the general trend confirms that usage volume and breakdowns are positively correlated, **the steep decline in September 2023 stands out**
- This normalization technique **further reinforces the reliability of the finding**, showing the same pattern without using the breakdown rate formula

---

### 5) Next Steps for Further Analysis

- Investigate **why breakdown reports decreased in September**
- Compare with **September data from 2021 and 2022** to determine whether this was a recurring pattern
- Check for any **special maintenance policies implemented in September**
- Examine whether **weather conditions** (rainfall, temperature, typhoons) influenced breakdown rates
- Analyze **breakdown patterns by bike model** (e.g., old vs. new bikes)

---

## 3. Outlook & Anticipated Impact

- This validation addresses a key limitation of the original project by thoroughly investigating whether the low breakdown rate in September 2023 was a data error or real event
- Based on confirmed results, the project will now **expand the research scope** to explore external causes and **analyze earlier years (2021–2022)** for context and confirmation
