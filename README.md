# 🚲 Seoul Public Bicycle Sep 2023 Breakdown Rate Validation Report

## 1. Background

This report documents the extended analysis conducted to verify and interpret monthly breakdown rate data for 2023 and 2024, specifically addressing analytical gaps identified in the original project.

The original analysis highlighted the high breakdown rate in **September 2024** but overlooked the **unusually low rate in September 2023**. This omission raised concerns regarding potential data or analysis errors.

The core objective of this report is to:
- Validate whether the **low breakdown rate in September 2023** was real or a result of analytical issues.
- Investigate **external factors** that could explain breakdown trends.


---

## 2. Validation of September 2023 Breakdown Rate

### 2.1 Review of the Original Analysis
- The original project only compared the breakdown rates for September 2023 and September 2024, **without further investigating why September 2023 showed such a low rate.**
- We needed to verify whether **the low breakdown rate in September 2023** was truly reliable and whether any mistakes occurred in the analysis process.

### 2.2 Reanalysis Process

- **Re-downloaded** the same dataset from the Seoul Open Data Portal.
- Performed the **same preprocessing** steps: cleaning duplicates, formatting, and breakdown rate calculation.
![graph1](https://github.com/user-attachments/assets/11feb584-23bb-4f79-b7d4-4ebfb60e12be)

✅ **Result:** The recalculated breakdown rate **matched** the original result → **No analysis error** detected.
  
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

📌 **Conclusion:** Per-Rental data does not offer comparable monthly aggregation → Not suitable for validation.

---

### 2.3 Breakdown Count vs. Usage Volume – Dual Y-Axis Graph (TWINX)
![graph2](https://github.com/user-attachments/assets/f2e5ef15-5a93-45d3-9dca-a5b0072a0e95)


- Visualized **raw breakdown counts** and **return volumes** on one chart using `twinx()` to separate axes.
- This method allowed direct visual comparison without relying on calculated rates.

**Interpretation:**
- The sharp drop in breakdowns in **September 2023** remained visible.
- Breakdown numbers rose again in **October**, suggesting the drop was **not a data error**, but a **real-world anomaly**.

**Conclusion:** The anomaly is unlikely to be caused by analytical or data errors, but rather a genuine data phenomenon

---

### 2.4 Normalized Comparison (Min-Max Scaling)

- Applied Min-Max normalization (0–1 scale) for better visual comparison over time.

![graph3](https://github.com/user-attachments/assets/88da1877-a464-42b3-8517-6b6b6219a5ce)

**Observation:**
- Breakdown reports and return counts followed a similar pattern overall.
- 📉 September 2023 showed a **notable breakdown drop**, despite stable return counts.
- Confirms the breakdown anomaly was **real**, even without using rate formulas.

---

## 3. Breakdown Rate Comparative Analysis (Aug–Sep, 2023 vs. 2024)

### 3.1 Usage Volume by Month

| Month | 2023 Usage | 2024 Usage | % Change |
|-------|------------|------------|----------|
| August | 3,935,440 | 3,998,334 | +1.60% |
| September | 4,548,991 | 4,250,763 | -6.56% |

### 3.2 Breakdown Count by Type (Aug–Sep)

| Breakdown Type | 2023 | 2024 | % Change |
|----------------|------|------|----------|
| Tire | 7,971 | 7,904 | -0.84% |
| Other | 7,206 | 7,420 | +2.96% |
| Chain | 5,853 | 8,393 | +26.31% |
| Pedal | 3,873 | 4,829 | +24.68% |
| Saddle | 4,568 | 3,869 | -15.30% |

### 3.3 Breakdown Count by Type (September Only)

| Breakdown Type | Sep 2023 | Sep 2024 | % Change |
|----------------|-----------|-----------|----------|
| Tire | 3,561 | 4,365 | +22.57% |
| Other | 3,117 | 4,021 | +29.00% |
| Chain | 2,748 | 3,901 | +41.95% |
| Pedal | 1,898 | 2,592 | +36.56% |
| Saddle | 2,129 | 2,080 | -2.30% |

📌 Chain, pedal, and tire breakdowns increased **significantly** in September 2024 → especially **chain (+41.95%)**

---

## 4. Potential Causes of Bicycle Failures

### 4.1 Mechanical Factors
- Chain stretching or rust due to lack of lubrication
- Pedal stiffness from bearing corrosion
- Tire pressure drop, cracking from sun exposure
- Brake wear, gear shifting problems, frame damage

### 4.2 Environmental Factors
- High rainfall → increased corrosion and wear
- Heat/cold → material expansion, lubricant hardening
- Poor road conditions → mechanical stress
- Outdoor storage → exposure to weather accelerates wear

### 4.3 User Behavior
- Rough handling, misuse of gears/brakes
- Lack of breakdown reporting
- Vandalism, overloading bikes

### 4.4 Maintenance & Operational Issues
- Missed regular inspections
- Delayed part replacements
- Docking station malfunctions
- Imbalanced bike redistribution

---

## 5. Environmental Trends (Weather Data Overview)

| Month | Avg Temp (°C) | Avg Rainfall (mm) |
|-------|---------------|-------------------|
| Aug 2023 | 27.2 | — |
| Sep 2023 | 23.7 | — |
| Aug 2024 | 29.3 | ↑ Higher |
| Sep 2024 | 25.5 | ↑ Significantly Higher |

📌 While temperature differences were moderate, **rainfall showed a more significant impact** on breakdowns.  
📉 Humidity was analyzed but **did not show meaningful influence**.

---

## 6. Next Steps

- Analyze September data from **2021 and 2022** for recurring patterns.
- Investigate whether **maintenance policy changes** occurred in Sep 2023.
- Study weather influence in more detail using precise rainfall & temperature data.
- Segment breakdown data by **bike model (old vs. new)** for further insight.

---

## 7. Conclusion & Outlook

This validation effort successfully addressed a key gap in the original project:  
✅ Confirmed that the low breakdown rate in September 2023 was **not caused by data or analytical errors**  
✅ Verified the anomaly using multiple methods (original formulas, raw counts, normalization, visualization)

Looking forward, the project will **expand to long-term data (2021–2022)** and explore **external contributing factors** to strengthen policy recommendations and improve public bicycle maintenance strategies.
