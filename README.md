<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,8,14&height=200&section=header&text=Automobile%20Sales%20Dashboard&fontSize=36&fontColor=ffffff&animation=fadeIn&fontAlignY=40&desc=Interactive%20Recession%20Analysis%20%7C%20Python%20%7C%20Plotly%20Dash%20%7C%20IBM%20Capstone&descAlignY=62&descSize=15" width="100%"/>

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dash-00ADD8?style=for-the-badge&logo=plotly&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/IBM-052FAD?style=for-the-badge&logo=ibm&logoColor=white"/>
  <img src="https://img.shields.io/badge/Data%20Visualisation-Capstone-gold?style=for-the-badge"/>
</p>

</div>

---

## 📋 Project Overview

This repository contains the **Part 2 Final Capstone submission** for IBM's *Data Visualisation with Python* course (`DV0101EN`). It implements a fully interactive **web-based analytics dashboard** using **Plotly Dash**, enabling dynamic exploration of historical automobile sales data across recession and non-recession economic periods (1980–2023).

The dashboard is designed to answer analytical questions around how macroeconomic downturns — specifically recession periods — influenced vehicle sales volumes, advertising expenditure allocation, and unemployment rate correlations across different vehicle categories for a fictional automotive company, **XYZAutomotives**.

---

## 🎯 Analytical Objectives

The dashboard addresses two primary reporting modes:

**1. Recession Period Statistics**
- How did automobile sales fluctuate year-over-year during recession periods?
- Which vehicle types were most and least affected by recessionary conditions?
- What was the advertising expenditure distribution across vehicle types during recessions?
- How did the unemployment rate correlate with vehicle type sales volumes?

**2. Yearly Statistics**
- What are the overall long-term automobile sales trends from 1980 to 2023?
- How did monthly sales volumes vary within a selected year?
- What was the average number of vehicles sold by type for a given year?
- How was advertising expenditure distributed across vehicle categories annually?

---

## 🛠️ Technology Stack

| Technology | Version | Role |
|:---|:---|:---|
| **Python** | 3.x | Core programming language |
| **Dash** | Latest | Web application framework for interactive dashboards |
| **Plotly Express** | Latest | High-level chart generation (line, bar, pie, scatter) |
| **Plotly Graph Objects** | Latest | Low-level chart customisation |
| **Pandas** | Latest | Data ingestion, filtering, aggregation, groupby operations |
| **IBM Skills Network CDN** | — | Remote CSV data source (historical_automobile_sales.csv) |

**Codebase composition:**

```
Python (app logic, callbacks, layout)   ████████████████████  ~95%
Configuration / assets                  █░░░░░░░░░░░░░░░░░░░   ~5%
```

---

## 📊 Dashboard Features & Chart Inventory

The application renders **8 distinct charts** across two report views, all driven by reactive Plotly Dash callbacks:

### Recession Report (4 charts)

| Chart | Type | Metric Visualised |
|:---|:---|:---|
| Sales Fluctuation Over Recession | Line | Year-over-year average automobile sales during recession periods |
| Average Sales by Vehicle Type | Bar | Mean units sold per vehicle category during recessions |
| Advertising Expenditure Share | Pie | % ad spend allocation per vehicle type during recessions |
| Unemployment Rate Effect | Bar | Average unemployment rate per vehicle type during recessions |

### Yearly Report (4 charts)

| Chart | Type | Metric Visualised |
|:---|:---|:---|
| Long-Term Sales Trend | Line | Annual average sales across the full 1980–2023 dataset |
| Monthly Sales (Selected Year) | Line | Total monthly automobile sales for the chosen year |
| Average Sales by Vehicle Type | Bar | Mean units sold per vehicle type in the selected year |
| Advertising Expenditure by Type | Pie | Ad spend distribution per vehicle category for the selected year |

---

## 🗂️ Repository Contents

| File / Asset | Description |
|:---|:---|
| `DV0101EN-Final_Assign_Part_2_Questions (1).py` | Full Dash application — layout, callbacks, chart logic |
| `Bar_graph.png` | Sample output: bar chart (vehicle type vs sales) |
| `Bubble.png` | Sample output: bubble/scatter plot |
| `Line_Plot_1.jpg` | Sample output: line chart — recession period trend |
| `Line_Plot_2.png` | Sample output: line chart — yearly sales over time |
| `Line_Plot_3.png` | Sample output: monthly sales line chart |
| `Pie_1.png` | Sample output: advertising expenditure pie (recession) |
| `Pie_2.png` | Sample output: advertising expenditure pie (yearly) |
| `Scatter_q_1_6.png` | Sample output: scatter plot — sales vs economic indicator |
| `Subplot.png` | Sample output: subplot grid layout |
| `q_1_6_consumer confidence.png` | Consumer confidence correlation chart |
| `vehicle wise during recession and non recession q1_3.png` | Vehicle-type comparison chart |

---

## ⚙️ Application Architecture

```
app.py
├── Layout
│   ├── html.H1 — Dashboard title
│   ├── dcc.Dropdown — Report type selector (Recession / Yearly)
│   └── dcc.Dropdown — Year selector (1980–2023, disabled for Recession mode)
│
└── Callbacks (2 reactive functions)
    ├── update_input_container() — Enables/disables year dropdown based on report type
    └── update_output_container() — Renders 4-chart grid based on selected report + year
        ├── Recession path → filters data['Recession'] == 1 → groupby operations → 4 charts
        └── Yearly path   → filters data['Year'] == input_year → groupby operations → 4 charts
```

**Key Dash patterns demonstrated:**
- `@app.callback` with `Input` / `Output` decorators for reactive UI updates
- `dcc.Dropdown` with dynamic `disabled` property toggling
- `html.Div` grid layout with `className='chart-grid'` for chart organisation
- Pandas `groupby().mean().reset_index()` and `groupby().sum().reset_index()` for aggregation

---

## 🚀 Running the Application

### Prerequisites

```bash
pip install dash plotly pandas
```

### Launch

```bash
python "DV0101EN-Final_Assign_Part_2_Questions (1).py"
```

Then open your browser and navigate to:

```
http://127.0.0.1:8050
```

Select a **report type** from the first dropdown. For **Yearly Statistics**, additionally select a **year** from the second dropdown. Charts update reactively.

---

## 📚 Course Context

| Detail | Value |
|:---|:---|
| Course | Data Visualisation with Python — `DV0101EN` |
| Provider | IBM / Coursera |
| Assignment | Final Capstone — Part 2 |
| Dataset | IBM Skills Network — Historical Automobile Sales CSV |
| Dataset period | 1980–2023 |
| Dataset variables | Year, Month, Automobile_Sales, Vehicle_Type, Recession, Advertising_Expenditure, unemployment_rate |

---

<div align="center">

**👤 Author: [Rutul Raval](https://github.com/rutulraval)** · IBM Data Visualisation Certified · SDET

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,8,14&height=100&section=footer" width="100%"/>

</div>
