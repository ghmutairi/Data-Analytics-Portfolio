# ⚡ Project 1: Energy & Emissions Efficiency Analysis

### 📖 The Data Story: Balancing Cost and Climate
In the current era of global energy transition, energy providers face a critical trilemma: securing energy that is reliable, affordable, and environmentally sustainable. Decision-makers often struggle to see the true trade-offs between the **Levelized Cost of Energy (LCOE)** and the **Carbon Footprint ($CO_2$ Emissions)** across different power generation facilities. 

The goal of this project was to transform raw, disconnected daily operational logs into a cohesive narrative that reveals which energy sources truly offer the best balance between economic viability and environmental responsibility.

---

### 🗄️ The Data Journey
To ensure the analysis reflected real-world scale and complexity, I processed a simulated dataset of **15,000+ daily operational records** spanning from 2024 to 2026. The data encompassed multiple facility types, including Renewable (Solar/Wind), Nuclear, and traditional Fossil Fuel plants.

#### 1. Data Extraction & Transformation (SQL)
The raw data was chaotic and highly granular. I utilized **SQL** to extract, clean, and aggregate the daily logs into meaningful monthly and yearly summaries. 

*Key SQL techniques applied:*
* **`JOIN` Operations:** Merged operational logs with facility metadata to categorize plants by energy type.
* **Aggregation (`GROUP BY`, `SUM`, `AVG`):** Calculated the average LCOE and total emissions per facility over time.
* **CTEs (Common Table Expressions):** Created temporary result sets to isolate high-emission plants for deeper comparative analysis.

#### 2. The Visual Narrative (Power BI)
Once the data was structured and refined, I connected it to **Power BI** to build an interactive dashboard designed for executive stakeholders. The visual strategy focused on clarity and contrast:
* **Scatter Plots:** Plotted LCOE against $CO_2$ emissions to visually separate high-efficiency/low-emission leaders from costly/polluting laggards.
* **Time-Series Charts:** Tracked the seasonal performance and cost fluctuations of renewable sources versus the steady baseline of nuclear energy.
* **Interactive Slicers:** Enabled users to filter the narrative by year, facility type, and region.

---

### 💡 Key Insights
The analysis successfully translated the data into actionable strategic insights:
1.  **The Hidden Cost of Stability:** While fossil fuels provided consistent baseline power, their emission penalties significantly reduced their long-term cost-efficiency compared to newer nuclear models.
2.  **Renewable Seasonality:** Solar and wind showed the lowest LCOE, but the data revealed operational gaps during winter months, highlighting the need for localized battery storage investments.
3.  **The Strategic Sweet Spot:** Nuclear facilities emerged as the most optimal long-term investment, offering zero emissions and the most stable LCOE over the 3-year analyzed period.

### 🎯 Business Impact
This project demonstrates my ability to take fragmented operational data and build a compelling, data-driven narrative that can directly influence capital allocation, sustainability reporting, and strategic energy planning.

---
### 💻 Data Engineering & Aggregation Logic (SQL)
Below is the core analytical logic used to extract and aggregate the daily operational logs. This specific query structures the raw data to calculate the Levelized Cost of Energy (LCOE) and track CO2 emissions intensity across different facility types:

```sql
/* ========================================================================
Project 1: Energy & Emissions Efficiency Analysis
Objective: Aggregating daily operational logs to calculate LCOE and CO2 
          emissions intensity per energy source.
========================================================================
*/

-- 1. Aggregating operational data to calculate key performance indicators (KPIs)
WITH Facility_Monthly_Stats AS (
    SELECT 
        Facility_ID,
        Facility_Name,
        Energy_Type,
        FORMAT_DATE('%Y-%m', Date) as Month,
        SUM(Daily_Output_MWh) as Total_MWh,
        SUM(Operational_Cost_USD) as Total_Cost,
        SUM(CO2_Emissions_Tons) as Total_Carbon
    FROM 
        `Project_Energy_DB.Daily_Logs`
    WHERE 
        Date >= '2024-01-01'
    GROUP BY 
        1, 2, 3, 4
)

-- 2. Calculating LCOE and Emission Intensity
SELECT 
    Energy_Type,
    ROUND(SUM(Total_Cost) / NULLIF(SUM(Total_MWh), 0), 2) as LCOE_USD_per_MWh,
    ROUND(SUM(Total_Carbon) / NULLIF(SUM(Total_MWh), 0), 4) as Emission_Intensity_Tons_per_MWh
FROM 
    Facility_Monthly_Stats
GROUP BY 
    Energy_Type
ORDER BY 
    LCOE_USD_per_MWh ASC;
```
### 📊 Visual Narrative: The Cost per m³ of Energy Emissions

This visualization bridges the gap between environmental impact and financial accountability by tracking the **Cost per Cubic Meter (m³)** of energy emissions. 

Rather than looking at abstract emission volumes, this chart translates raw gas outputs into a direct cost metric. The visual narrative empowers decision-makers to:
* **Identify Inefficiencies:** Quickly spot which facilities or fuel types are incurring the highest environmental and operational costs per volume of emissions.
* **Optimize Budgets:** Align sustainability targets with financial realities by targeting high-cost emission areas for process improvements or technological upgrades.
<img width="1160" height="674" alt="PowerBIRepernstation" src="https://github.com/user-attachments/assets/2418e17e-be83-4b40-993b-c8f8df251ad8" />

