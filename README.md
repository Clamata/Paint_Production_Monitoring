# 🎨 Paint Production Monitoring – Power BI Project

This Power BI project focuses on analyzing **paint manufacturing production data** along with **employee performance metrics**. It demonstrates skills in **data modeling**, **DAX calculations**, and **dashboard visualizations**.

---

## 🧠 Key Objectives

- Monitor production output and downtime
- Evaluate operator performance
- Analyze machine efficiency
- Track defect rates and trends over time

---

## 🗂️ Data Model

The project uses a **star schema** with the following tables:

### 🔷 Fact Table
- `Manufacturing Data`

### 📘 Dimension Tables
- `Product Lookup`
- `Shift Lookup`
- `Operator Lookup`
- `Machine Lookup`
- `Calendar Lookup`

### 🔗 Relationships

All lookups have a **one-to-many** relationship with the `Manufacturing Data` fact table:

- `Product Lookup` ➝ `Manufacturing Data`
- `Shift Lookup` ➝ `Manufacturing Data`
- `Operator Lookup` ➝ `Manufacturing Data`
- `Machine Lookup` ➝ `Manufacturing Data`
- `Calendar Lookup` ➝ `Manufacturing Data`

### 🗺️ Data Model Diagram

![Data Model](Readme%20images/Data%20Model.png)

---

## 🧮 DAX Measures

The **Measure Table** includes:
- `Defects %`
- `Downtime %`
- `Max Production`
- `Previous Month Defects`
- `Previous Month Production Efficiency`
- `Previous Month Units`
- `Production Efficiency %`
- `Total Defects`
- `Total Downtime`
- `Total Units`
- `Total Work Time`

### ✏️ Example Measure:

```DAX
Previous Month Production Efficiency = 
CALCULATE(
    [Production Efficiency %],
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)
```
The measure calculates previous month production efficiency rate using an existing DAX measure and the `DATEADD()` function.

## 📊 Visualisations

Dashboard 1: Overview
![Overview](Readme%20images/Overview.png)
Dashboard 2: Operator Detail
![Operator Detail](Readme%20images/Operator%20Detail.png)
Dashboard 3: Machine Detail
![Machine Detail](Readme%20images/Machine%20Detail.png)

## 📁 Folder Structure

```
Paint_Production_Monitoring/
│
├── report.pbix
├── README.md
└── assets/
    ├── Data Model.png
    ├── Overview.png
    ├── Operator Detail.png
    └── Machine Detail.png
```

## 🚀 How to Use

1. Open `report.pbix` in Power BI Desktop.
2. Update data sources if necessary.
3. Refresh and explore the dashboards.

---
