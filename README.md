# ExxonMobil Hackathon 2025

[![Watch the video](https://img.youtube.com/vi/AbxGe0n9HnQ/maxresdefault.jpg)](https://youtu.be/AbxGe0n9HnQ)

## Challenge Overview

This project was developed as part of the **ExxonMobil Hackathon 2025** under the theme: **Analytics & Innovation for Sustainable Operations**.

---

## Business Context

### Organization Overview

* **Parent Company**: Exxon Mobil Corporation, USA – Over 140 years in global energy, gas, and petroleum.
* **Vision**: *Leader of innovation advancing modern living.*
* **Purpose**: *Sustainably improve quality of life.*
* **Key Divisions**:

  * Upstream (e.g., deep-sea drilling, LNG)
  * Product Solutions (e.g., fuel, chemical, lubricants)
  * Low Carbon Solutions (e.g., CCS, biofuels, lithium for EVs)

---

## Business Case: Polymer Product Logistics

The core problem involves warehouse **inventory imbalance**, where mismatch between **inbound shipments** (based on 3-month demand planning) and **outbound logistics** (truck/marine) causes:

* Overflow costs (e.g., Demurrage & Detention)
* Understock scenarios affecting service levels
* Inefficient space utilization, causing operational delays

**Warehouse KPIs**:

* Maximize utilization without breaching capacity
* Maintain inventory levels in optimal range (target: 70–80% capacity)
* Predict and adjust future stock fluctuations early

---

## Dataset Description

The dataset used includes:

* `Warehouse_Max_Capacity`
* `On_Ground_Inventory_2024`
* `Inbound_Data`
* `Outbound_Data`
* `Forecasted_Demand & Sales`
* `Material_Master_Data`

---

## Solution Approach

### 1. Descriptive Analytics (EDA & Monitoring)

* Cleaned and standardized all data sources using Python (Pandas, NumPy)
* Merged datasets across months and material IDs
* Identified aging stock, short shelf life items, and stock with low movement
* Built KPI dashboard (Power BI) showing:

  * Monthly Inventory Utilization
  * Overflow Rate Trends
  * Inventory Accuracy Deviation
  * SLCR (Short Life Clearance Rate) and Alert Zones

**Sample KPIs Created:**

* `InventoryDiff%`: Actual vs Calculated Inventory Deviation
* `SLCR`: % of short shelf life items cleared before expiry
* `OverflowRate`: % over max warehouse capacity

### 2. Forecast Adjustment

> *Performed statistical corrections using historical deviation patterns to fine-tune the existing forecasts.*

* Calculated monthly errors between forecast and actual
* Applied adjustment factor to forecasted values
* Improved alignment for planning next-cycle inbound and outbound schedules

---

### 3. Optimization Engine

#### Phase 1 – Historical Simulation Model

* Simulated monthly warehouse stock using actual Jan–Sep 2024 data
* Set constraints: max capacity, min required service stock, transport delay buffers
* Objective: reduce overflow, stabilize stock between 70–80%

#### Phase 2 – **Forecast-based Predictive Optimization**

> **Build a New Optimization Function for `pred_data`**
> Enabled plug-and-play optimizer to run on newly adjusted forecasts.

* Applied linear programming (via PuLP) to optimize inbound and outbound timing
* Recommended monthly shipment quantities per scenario
* Tracked overflow risk and stockout risk in optimized schedule

---

## Analytics Highlights

| Focus Area                      | Tools/Techniques                        | Impact                              |
| ------------------------------- | --------------------------------------- | ----------------------------------- |
| Forecast Accuracy               | MAPE, MAE, Custom Adjustment Factors    | Improved prediction reliability     |
| Shelf Life Analysis             | Quartile Analysis, SLCR Calculation     | Prioritized risky SKUs              |
| Overflow & Understock Detection | Time-series plotting, anomaly detection | Enabled proactive planning          |
| Dashboarding                    | Power BI visuals with DAX               | Real-time KPI monitoring & insights |

---

## Technical Stack

* **Python** (Pandas, NumPy, Matplotlib, Scikit-learn, PuLP)
* **Power BI** for dashboard visualizations
* **Jupyter Notebook** for model development
* **Git & GitHub** for version control

---

## Highlights & Innovation Value

| Area                | Innovation                                             |
| ------------------- | ------------------------------------------------------ |
| Forecast Refinement | Enhanced accuracy using post-forecast adjustments      |
| Optimization        | Scalable predictive optimizer using linear programming |
| Decision Support    | Actionable KPI dashboards and alert systems            |

> The final solution supports **inventory planning decisions before shipment occurs**, enhancing **efficiency, sustainability, and resilience**.

---

## Hackathon Criteria Mapping

| Criteria                 | Our Approach                                     |
| ------------------------ | ------------------------------------------------ |
| Innovation & Creativity  | Forecast-adjusted optimizer with alert dashboard |
| Technical Implementation | EDA + Forecast Adjustment + Optimization Logic   |
| Impact & Scalability     | Plug-and-play optimizer, scalable KPIs           |
| Presentation & Insight   | Actionable dashboards with storytelling          |

---

## Q\&A Ready

Feel free to reach out with any questions or review our notebooks for detailed modeling, data processing, and optimization logic.

> *Innovation means enabling smarter, faster, and more sustainable operations – today and tomorrow.*
