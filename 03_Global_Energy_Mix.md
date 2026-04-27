# 🌍 Project 3: Global Energy Mix Transitions (2004 - 2024)

### 📖 The Data Story: Tracking the Global Energy Transition
The global energy landscape is undergoing a massive transformation. As nations strive to meet climate goals, understanding the historical shift from traditional fossil fuels to renewable and low-carbon energy sources is crucial for strategic long-term planning. 

The objective of this project was to analyze macro-level global energy consumption trends over the last two decades, answering a vital business question: *How fast is the world actually adopting renewable energy, and what is the persisting role of traditional fuels in maintaining global energy security?*

---

### 🗄️ The Data Journey
To perform this analysis, I bypassed static local files and established a **Live Web Connection** to the authoritative *'Our World in Data'* (OWID) global energy repository. This dataset was massive, containing over **22,000 historical records** across 120+ technical columns.

#### Data Engineering & Cleansing 
Working with global datasets often means dealing with missing or sparse data. I utilized **Power Query** to surgically clean and optimize the model before any visual analysis took place:
* **Data Reduction:** Filtered the dataset to focus strictly on the last 20 years (>= 2004), significantly reducing processing load and focusing the narrative on modern transition phases.
* **Dimensional Modeling:** Extracted only the core consumption metrics (Coal, Oil, Gas, Nuclear, Renewables), stripping away irrelevant columns to create a lean, highly performant data model.
* **Handling Data Sparsity:** Engineered data cleansing steps to identify `null` values (common in developing nations' reports) and intelligently replaced them with `0` to ensure accurate mathematical aggregations in the final visualizations.

---

### 💡 Key Insights 
The dynamic visualization revealed several profound macro-trends:
1.  **The Rise of Renewables:** A highly visible, exponential expansion in the renewable energy band (solar and wind) post-2010, driven by global policy shifts and dropping technology costs.
2.  **The Resilience of Natural Gas:** Despite the push for green energy, natural gas consumption showed steady, resilient growth, cementing its role as the critical "bridge fuel" stabilizing the grid during the transition.
3.  **Stagnation of Coal in Developed Markets:** The data highlighted a clear plateau and subsequent decline in coal reliance within specific advanced economies, contrasting with steady usage in emerging markets.

### 🎯 Business Impact
This project highlights my capability to connect to live, massive external databases, engineer clean data models from chaotic sources, and build macro-economic dashboards. These skills are directly transferable to monitoring global market trends, competitor analysis, and strategic forecasting.

---

### 💻 Data Transformation (Power Query M-Code)
### 🛠️ Data Engineering & Cleansing (Power Query)
To ensure absolute accuracy and control over the data model, I manually engineered and cleansed the raw dataset using the Power Query interface. My step-by-step transformation process included:

* **Direct Data Connection:** Connected directly to the external repository via the Power BI interface, ensuring the data model could handle massive datasets without relying on static Excel downloads.
* **Strategic Filtering:** Filtered the dataset to focus exclusively on the last 20 years (>= 2004). This crucial step significantly reduced processing load and focused the narrative purely on modern energy transition phases.
* **Dimensional Modeling:** Manually selected only the core consumption metrics (Coal, Oil, Gas, Nuclear, Renewables), stripping away irrelevant columns to create a lean, highly performant data model.
* **Data Imputation:** Identified `null` values (common in developing nations' historical reports) and systematically replaced them with `0` using the transform features, ensuring flawless mathematical aggregations in the final visual layers.



  
### 📊 The Energy Landscape Visualized (Power BI):
[Global Energy Mix Transitions & Consumption Trends (2004 - 2024).pdf](https://github.com/user-attachments/files/27099060/Global.Energy.Mix.Transitions.Consumption.Trends.2004.-.2024.pdf)

<img width="1112" height="639" alt="GE" src="https://github.com/user-attachments/assets/9120eeca-7c57-4a44-8233-5fd311b2f80b" />

