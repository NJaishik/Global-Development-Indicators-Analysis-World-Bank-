## Project Overview

This project presents an interactive **Power BI dashboard** analyzing **global economic, social, and environmental indicators** using World Bank–style data.
The dashboard enables comparison of countries across **GDP, population, employment, life expectancy, CO₂ emissions, and infrastructure access**, with a strong focus on **data accuracy and decision-oriented insights**.

The project follows **best practices in BI modeling**, DAX calculations, and visualization design, making it suitable for **policy analysis, executive reporting, and analytics roles**.

## Dashboard Structure

### Page 1: Global Overview

**Purpose:** High-level snapshot of global development

**Key KPIs:**

* Total Countries
* Latest Year
* Global GDP (Latest Year)
* Global Population (Latest Year)
* Average Unemployment Rate
* Average Life Expectancy

**Visuals:**

* Global GDP Trend (Year-wise)
* Global Population Trend
* Year & Country slicers for dynamic analysis

### Page 2: Economic Analysis

**Purpose:** Compare economic scale, demographic pressure, and employment stress

**Visuals:**

* Top Countries by GDP (Latest Year)
* GDP vs Population (Scatter Chart)
* Countries with Highest Unemployment Rate

**Key Insight:**

> Population size does not directly translate to economic output; some countries generate disproportionately high GDP with smaller populations.

### Page 3: Social & Environmental Analysis

**Purpose:** Evaluate quality of life, sustainability, and infrastructure access

**Visuals:**

* Top Countries by Life Expectancy
* CO₂ Emissions per Capita (Latest Year)
* Countries with Lowest Access to Electricity

**Key Insight:**

> Development disparities are visible across health outcomes, environmental impact, and access to basic infrastructure.

## Key DAX Concepts Used

### Latest-Year Based Measures

To avoid multi-year aggregation distortion, **latest-year filtering** was applied using DAX:

```DAX
Latest Year = MAX(world_bank_dataset[Year])
```

Example:

```DAX
Access to Electricity (Latest Year) =
CALCULATE(
    AVERAGE(world_bank_dataset[Access to electricity(%)]),
    FILTER(
        world_bank_dataset,
        world_bank_dataset[Year] = [Latest Year]
    )
)
```

**Why this matters:**

* Prevents inflated averages
* Ensures policy-grade accuracy
* Aligns with World Bank reporting standards

## Tools & Technologies

* **Power BI Desktop**
* **DAX (CALCULATE, FILTER, context handling)**
* **Power Query**
* **Data Modeling & Visualization**
* **Analytical storytelling**

## Key Learnings

* Correct aggregation is critical for ratio-based indicators
* Latest-year logic improves accuracy in time-series datasets
* Scatter charts are powerful for relationship analysis
* BI dashboards should balance trends with snapshot KPIs
---

