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

### 💡 Key Insight
The analysis successfully translated the data into actionable strategic insights:
1.  **The Hidden Cost of Stability:** While fossil fuels provided consistent baseline power, their emission penalties significantly reduced their long-term cost-efficiency compared to newer nuclear models.
2.  **Renewable Seasonality:** Solar and wind showed the lowest LCOE, but the data revealed operational gaps during winter months, highlighting the need for localized battery storage investments.
3.  **The Strategic Sweet Spot:** Nuclear facilities emerged as the most optimal long-term investment, offering zero emissions and the most stable LCOE over the 3-year analyzed period.

### 🎯 Business Impact
This project demonstrates my ability to take fragmented operational data and build a compelling, data-driven narrative that can directly influence capital allocation, sustainability reporting, and strategic energy planning.

---

