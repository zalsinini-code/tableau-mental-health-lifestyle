# tableau-mental-health-lifestyle
# 📊 Tableau Project Documentation: 🧠 Mental Health & Lifestyle Analysis
An interactive Tableau analysis exploring the impact of lifestyle factors—such as sleep, diet, and work hours—on mental health and stress levels across regional demographics (Canada &amp; India).

---

## 📌 Project Overview
This project explores the relationship between various lifestyle factors—such as sleep hours, work hours per week, diet type, and gender—and stress levels or mental health conditions across different countries. Using Tableau Desktop, an interactive visualization system was built to isolate high-stress demographics, examine proportion ratios for mental health conditions, and analyze regional lifestyle patterns (focusing particularly on top regions like Canada and India).

---

## 1. 📁 Data Source
* **File Name:** `Mental_Health_Lifestyle_Dataset.csv`
* **Fields & Metadata:**
  * `Country` *(String / Categorical)*
  * `Age` *(Integer)*
  * `Gender` *(String)*
  * `Exercise Level` *(String)*
  * `Diet Type` *(String - e.g., Balanced, Vegetarian, Vegan, Keto, Junk Food)*
  * `Sleep Hours` *(Float / Continuous)*
  * `Stress Level` *(String - High, Moderate, Low)*
  * `Mental Health Condition` *(String)*
  * `Work Hours per Week` *(Integer)*
  * `Screen Time per Day (Hours)` *(Float)*
  * `Social Interaction Score` *(Float)*
  * `Happiness Score` *(Float)*

---
## 📊 Data Source
* ** Source:** [Kaggle](https://www.kaggle.com/)
* **📄 Dataset File:** `Mental_Health_Lifestyle_Dataset.csv`
* **🔑 Key Fields:**
  * **🌐 Demographics / Geography:** `Country`, `Age`, `Gender`
  * **🏃 Lifestyle Indicators:** `Exercise Level`, `Diet Type`, `Sleep Hours`, `Work Hours per Week`, `Screen Time per Day (Hours)`, `Social Interaction Score`, `Happiness Score`
  * **💔 Mental Health Indicators:** `Stress Level`, `Mental Health Condition`
---

## 🧮 Calculated Fields & Formulas

### 1. 💤 Sleep Hours Classifications
Categorizes individuals based on whether their daily sleep falls below or above a specific threshold (6.4 hours):

```tableau
IF [Sleep Hours] < 6.4 THEN 'Insufficient'
ELSEIF [Sleep Hours] > 6.4 THEN 'Sufficient'
END
```

---

## 2. 📐 Proportional Ratio Calculations
🥧 Mental Health Condition Proportional Ratio
Calculates the relative percentage proportion of individuals within a given partition relative to the total population count:

```tableau
COUNT([Mental_Health_Lifestyle_Dataset.csv]) / TOTAL(COUNT([Mental_Health_Lifestyle_Dataset.csv]))
```
---
⚙️ Formatting: Displayed as a percentage (p0%) on pie/wedge visuals to show proportional distributions across gender and mental health conditions.
📋 Worksheet Structure

```markdown
| 📊 Worksheet Name | 📈 Visual Type | 🧩 Primary Dimensions & Measures | 🎯 Key Purpose |
| :--- | :--- | :--- | :--- |
| **Stress Level Bar Chart** | Bar Chart | `Country`, `COUNT(Stress Level)` | Highlights the **Top 5 countries** with the highest counts of **High** stress levels. |
| **Canada: Stress Level Vs Diet Type** | Bar Chart | `Diet Type`, `Stress Level`, `COUNT(Diet Type)` | Analyzes diet type distributions under high stress within Canada. |
| **Canada: Stress Levels Vs Mental Health** | Pie Chart | `Gender`, `Mental Health Condition`, Proportional Ratio Calculation | Displays proportional ratios of mental health conditions broken down by gender for Canada. |
| **Canada: Stress Levels Vs Sleep Hour Classifications** | Bar Chart | `Sleep Hours Classifications`, `Stress Level`, `COUNT(Dataset)` | Displays high stress counts against **Insufficient** vs **Sufficient** sleep in Canada. |
| **Canada: Stress Levels Vs Work Hours** | Bar Chart | `Stress Level`, `COUNT(Work Hours per Week)` | Compares weekly work hour impacts across stress tiers in Canada. |
| **India: Stress Level Vs Diet Type** | Bar Chart | `Diet Type`, `Stress Level`, `COUNT(Diet Type)` | Evaluates dietary habits relative to stress levels in the India region. |
| **India: Stress Levels Vs Mental Health** | Pie Chart | `Gender`, `Mental Health Condition`, Proportional Ratio Calculation | Measures mental health conditions and gender proportions under high stress in India. |
| **India: Stress Levels Vs Sleep Hour Classifications** | Bar Chart | `Sleep Hours Classifications`, `Stress Level`, `COUNT(Dataset)` | Analyzes sleep sufficiency vs high stress counts for India. |
| **India: Stress Levels Vs Work Hours** | Bar Chart | `Stress Level`, `COUNT(Work Hours per Week)` | Highlights workload distribution across stress levels in India. |
```

---

⚡ Interactivity & Dashboard Actions
The workbook includes several dynamic Filter Actions to seamlessly cross-filter charts upon user selection:

🌍 Global Stress Level / Country Actions: Selecting a country or high-stress segment filters detailed regional charts dynamically.

🔄 Cross-Sheet Filtering: Interacting with specific worksheets (e.g., clicking on a high-stress tier or gender segment) automatically passes context across the regional lifestyle charts (Canada: Lifestyle and India: Lifestyle).

🧹 Selection Clearing: Filter actions are configured to clear or restore values on deselect to ensure fluid exploration.

---

## 📁 Repository Structure
```text
├── data/
│   └── Mental_Health_Lifestyle_Dataset.csv   # Primary CSV dataset downloaded from Kaggle
├── tableau/
│   └── Mental_Health_Lifestyle_Analysis.twb   # Tableau Workbook containing worksheets and dashboards
└── README.md                                 # Project documentation



