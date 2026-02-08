# Global Energy Transition Trade Dynamics

## 📌 Project Overview
This project is an end-to-end data analytics solution built in Power BI to track and analyze global energy dynamics through production, consumption, and trade from 1990 to 2014. It transforms raw international energy statistics into a multi-page interactive dashboard that highlights the structure of countries’ energy mixes, and patterns of international energy trade.

---
## 🎯 Objectives
* Profile Energy Systems: Compare how countries differ in total production, consumption, and net trade of energy over time.
* Visualize Trade Patterns: Identify net exporters and importers by region and commodity using geospatial mapping.
* Understand Energy Mix: Use hierarchical visuals to break down each country’s energy mix by fuel category (coal, oil products, natural gas, nuclear, etc.).

---
## 📂 Project Structure
* `Global_Energy_Analysis.pbix`: The Power BI file containing the data model, DAX measures, and report pages.
* `Multi-page dashboard`: A folder containing high-resolution captures of the three main dashboard pages.

---
## ⚙️ Technical Implementation
### DAX Measures
Key measures driving the analytics:
* Total Quantity – SUM(quantity) as the base measure for all flows.
* Total Production / Total Consumption – CALCULATE([Total Quantity], FlowType = "Production"/"Consumption") to isolate specific energy flows.
* Total Imports / Total Exports – Flow‑filtered measures to support trade analysis.
* Net Trade – [Total Exports] - [Total Imports], showing whether a country is a net exporter or importer.
* % Renewable (Experimental) – A measure built on a custom classification of categories that can be extended in future work; in the current dataset, the provided IsRenewable column is effectively all “Non‑Renewable”, so this KPI is intentionally de‑emphasized in the narrative.
* Card‑Safe Logic – Use of DIVIDE(..., 0) and + 0 patterns to avoid blank or error outputs on KPI cards.
---
## 📈 Visualizations & Dashboard Pages
### Overview
  * KPI cards for Total Production, Total Consumption, and Net Trade at the global level.
### Production & Consumption
  * 100% stacked column chart of total production by year and category, highlighting how fuel types contribute to total output.
  * Bar chart of Total Production vs. Total Consumption by country, making it easy to spot structural importers and exporters.
### Trade & Transitions
  * Map visual (Azure Maps) displaying Net Trade by country, with bubble size representing trade volume and color indicating surplus or deficit.
  * Treemap of Total Production by commodity transaction and country, revealing which fuels dominate in each region’s energy mix.
  * Ribbon chart that shows how the composition of production by category changes from 1990 to 2014.
  * Global slicers for Year and Country to control all pages.

---
## 🔑 Key Takeaways
* **Long‑run production trends**: The dashboard shows how global production scales up over 1990–2014, with fossil fuels (coal, oil products, natural gas) remaining dominant in the total energy mix for most countries.
* **Trade dependencies**: Net‑trade measures and the map highlight traditional exporters (e.g., major oil‑ and gas‑producing countries) versus structurally import‑dependent economies.
* **Energy mix diversity**: Treemap and stacked visuals make it clear which countries rely heavily on a single fuel versus those with a more diversified mix (e.g., significant shares of natural gas or nuclear alongside coal and oil).

---
## 🛠 Tools Utilized
* **Power BI Desktop**: Data visualization & modeling
* **DAX (Data Analysis Expressions)**: Custom measures for production, consumption, and trade KPIs.
* **Power Query**: Cleaning and shaping the energy dataset.
* **Azure Maps**: Geospatial analysis of energy trade patterns.

---
## 📌 Future Enhancements
* **Renewables classification**: Introduce a robust, documented classification of renewable vs non‑renewable fuels based on category, enabling a more reliable % Renewable measure.
* **Predictive Analytics**: Add time‑series forecasting to project production or trade volumes for the next decade.
* **Emissions Integration**: Join the energy dataset with CO₂ emission statistics to relate energy structure and trade to climate impact.
* **Live Data Pipelines**: Replace static CSV input with periodic refresh from official UN or IEA APIs, where available.
