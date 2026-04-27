# 🚚 Project 2: Rig Spare Parts Logistics & Supply Chain Optimization

### 📖 The Data Story: Minimizing Operational Downtime
In the energy sector, drilling rigs operate 24/7, and every hour of downtime due to missing equipment translates to significant financial losses. The core challenge was to optimize the supply chain network, ensuring that critical spare parts—ranging from drill bits to sensor valves—are dispatched efficiently from the central logistics hub in Dhahran to remote operational sites.

This project aimed to proactively identify shipping bottlenecks, analyze delivery delay patterns, and optimize routing modes to minimize equipment wait times and reduce unnecessary expedited shipping costs.

---

### 🗄️ The Data Journey
Given the sensitive nature of corporate supply chain data, I engineered a highly scalable Python environment to simulate and analyze complex logistics operations. I generated a **50,000+ record dataset** of synthetic shipping logs to rigorously test my analytical scripts.

#### Data Processing & Analysis (Python)
Using **Python** (specifically `pandas` and `numpy`), I transformed this massive dataset into actionable operational intelligence. 

*Key Python techniques applied:*
* **Synthetic Data Generation:** Built a robust data-generation script to simulate realistic supply chain complexities, including varied shipping modes, random delay days, and destination rig locations (e.g., Haradh, Shaybah, Safaniya).
* **Data Aggregation (`groupby`):** Segmented the data to calculate average delay times and total shipping costs per destination and per shipping mode.
* **Bottleneck Identification:** Filtered and sorted the DataFrames to isolate high-risk delivery routes that consistently exceeded the acceptable delivery timeframe.

---

### 💡 Key Insights
The Python-driven analysis uncovered several critical operational insights:
1.  **Mode-to-Destination Mismatch:** The data revealed that relying on standard truck freight for remote rigs (like Shaybah) caused exponential delays, suggesting that utilizing air freight for critical parts to these specific locations is more cost-effective than the resulting downtime.
2.  **Hub Efficiency:** The central Dhahran hub effectively managed high-volume orders, but delays spiked during specific clustered order periods, indicating a need for predictive inventory pre-positioning.
3.  **Cost-Delay Trade-off:** By identifying the routes with the highest delay-to-cost ratios, the analysis provided a data-backed foundation for renegotiating contracts with third-party logistics (3PL) providers.

### 🎯 Business Impact
This project showcases my ability to leverage Python to process massive datasets and uncover hidden logistical inefficiencies. The resulting insights provide a direct pathway to reducing operational downtime and optimizing supply chain OPEX.

---

### 💻 Code Implementation (Python)
Below is a snippet of the Python code used to generate the synthetic operational data and perform the bottleneck analysis using `pandas`:

```python
import pandas as pd
import numpy as np

# Data generation script for 50,000 logistics records...
# (Full script available in repository)

# Analyzing average delay days and costs per Rig Destination
delay_analysis = df_massive.groupby(['Destination_Rig', 'Shipping_Mode']).agg({
    'Delay_Days': 'mean',
    'Cost_USD': 'sum',
    'Order_ID': 'count'
}).rename(columns={'Order_ID': 'Total_Shipments'}).reset_index()

# Identifying severe bottlenecks (Average delay > 7 days)
critical_bottlenecks = delay_analysis[delay_analysis['Delay_Days'] > 7].sort_values(by='Delay_Days', ascending=False)

print(critical_bottlenecks.head())
```


### 📊 Analysis Output

[TheRootCauseOfTheDelayDays.pdf](https://github.com/user-attachments/files/27099089/TheRootCauseOfTheDelayDays.pdf)
<img width="733" height="490" alt="TheRootCauseOfTheDelayDays" src="https://github.com/user-attachments/assets/8b697926-bb36-446a-8744-93887cf0fc4c" />
