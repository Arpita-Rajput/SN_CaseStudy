# SN_CaseStudy
SIOP Forecasting – Executive Dashboard (Revenue, Non-Revenue &amp; CAPEX Forecast Analysis)

# SIOP Forecasting – Executive Dashboard

## Project Overview

This project focuses on **Sales, Inventory & Operations Planning (SIOP)** reporting using Power BI. The objective is to transform forecast snapshot data, merge it with actual sales data, and create an executive dashboard that enables business users to analyze forecast performance, forecast accuracy, forecast bias, and country-level trends.

The dashboard provides insights into **Revenue, Non-Revenue, and CAPEX forecasts** across different countries and forecast snapshots (Resultant, Lag 0, and Lag 1).

---

# Business Problem

In SIOP processes, forecasts are generated periodically and stored as monthly snapshots.

For example:

| As Of Period | Forecast Period |
| ------------ | --------------- |
| 2023 P10     | 2024 P01        |
| 2023 P11     | 2024 P01        |
| 2023 P12     | 2024 P01        |

Business users need to compare forecasts from different snapshots for the same future period.

The latest forecast snapshot is considered:

* **Resultant Forecast**
* Previous Snapshot = **Lag 0**
* Snapshot before previous = **Lag 1**

This comparison helps identify forecast evolution and planning accuracy over time.

---

# Objectives

### Data Transformation

* Transform forecast snapshot data into a comparison-ready structure.
* Create separate columns for:

  * Resultant Revenue Forecast
  * Lag 0 Revenue Forecast
  * Lag 1 Revenue Forecast
  * Resultant Non-Revenue Forecast
  * Lag 0 Non-Revenue Forecast
  * Lag 1 Non-Revenue Forecast
  * Resultant CAPEX Forecast
  * Lag 0 CAPEX Forecast
  * Lag 1 CAPEX Forecast

### Data Integration

Merge Forecast and Actual datasets using:

* Period
* Country
* Item

### Dashboard Development

Create an executive dashboard for:

* Revenue Forecast Analysis
* Non-Revenue Forecast Analysis
* CAPEX Forecast Analysis
* Forecast Accuracy Monitoring
* Forecast Bias Monitoring

---

# Dataset Description

## Forecast Table

Contains:

* As Of Period
* Forecast Period
* Country
* Item
* Revenue Forecast
* Non-Revenue Forecast
* CAPEX Forecast
* Period Offset

## Actual Table

Contains:

* Period
* Country
* Item
* Actual Revenue Quantity
* Actual Non-Revenue Quantity
* Actual CAPEX Quantity

---

# Data Transformation Logic

## Snapshot Classification

| Snapshot                      | Classification |
| ----------------------------- | -------------- |
| Latest Snapshot               | Resultant      |
| Previous Snapshot             | Lag 0          |
| Previous to Previous Snapshot | Lag 1          |

### Example

| Forecast Period | Lag 1 | Lag 0 | Resultant |
| --------------- | ----- | ----- | --------- |
| 2024 P01        | 100   | 110   | 120       |
| 2024 P02        | 95    | 105   | 115       |

---

# Data Model

### Relationships

Forecast and Actual tables are connected using:

```text
Period
Country
Item
```

Additional dimensions:

```text
DimDate
DimCountry
```

---

# Business KPIs

## Forecast Accuracy %

Formula:

Forecast\ Accuracy\ %=1-\frac{|Lag\ Qty-Actual\ Qty|}{Actual\ Qty}

Purpose:

Measures how close the forecasted quantity is to actual quantity.

Higher value indicates better forecasting performance.

---

## Forecast Bias %

Formula:

Forecast\ Bias\ %=\frac{Lag\ Qty-Actual\ Qty}{Actual\ Qty}

Purpose:

Measures whether the forecast is overestimating or underestimating actual demand.

* Positive Bias → Over Forecasting
* Negative Bias → Under Forecasting

---

# Dashboard Features

## Filters

### Lag Selection

Available options:

* Resultant
* Lag 0
* Lag 1

Dynamic selection updates:

* Revenue Forecast
* Non-Revenue Forecast
* CAPEX Forecast
* Forecast Accuracy
* Forecast Bias

### Additional Filters

* Year
* Country

---

# Dashboard Components

## Executive KPI Overview

Cards displaying:

* Revenue Forecast
* Non-Revenue Forecast
* CAPEX Forecast
* Forecast Accuracy %
* Forecast Bias %

---

## Forecast by Country

Visualizations:

### Revenue Forecast by Country

Clustered Column Chart

### Non-Revenue Forecast by Country

Clustered Column Chart

### CAPEX Forecast by Country

Clustered Column Chart

---

## Forecast vs Actual Trend

Line Chart

Comparison between:

* Forecast Values
* Actual Values

Across forecast periods.

---

## Forecast Evolution Analysis

Waterfall Chart displaying:

* Lag 1 Forecast
* Lag 0 Forecast
* Resultant Forecast

Used to analyze forecast movement between snapshots.

---

## Forecast Accuracy Heatmap

Matrix visual with conditional formatting.

Dimensions:

* Country
* Period

Measure:

* Forecast Accuracy %

Color Coding:

* Green = High Accuracy
* Yellow = Medium Accuracy
* Red = Low Accuracy

---

## Country Performance Table

Detailed comparison including:

### Revenue

* Lag 1 Revenue
* Lag 0 Revenue
* Resultant Revenue
* Actual Revenue
* Accuracy %

### Non-Revenue

* Lag 1 Non-Revenue
* Lag 0 Non-Revenue
* Resultant Non-Revenue
* Actual Non-Revenue
* Accuracy %

### CAPEX

* Lag 1 CAPEX
* Lag 0 CAPEX
* Resultant CAPEX
* Actual CAPEX
* Accuracy %

---

# Additional Analysis

## Top Performing Countries

Identify countries with:

* Highest Revenue Forecast
* Highest Accuracy %

## Variance Analysis

Formula:

```text
Variance = Forecast - Actual
```

Used to evaluate planning effectiveness.

## Forecast Trend Analysis

Track forecast evolution from:

```text
Lag 1 → Lag 0 → Resultant
```

to understand planning adjustments over time.

---

# Tools & Technologies

* Power BI Desktop
* Power Query
* DAX
* Data Modeling
* KPI Analysis
* Forecast Analytics

---

# Expected Business Outcomes

* Improved forecast visibility
* Enhanced planning accuracy
* Better demand forecasting decisions
* Identification of forecasting bias
* Country-wise performance monitoring
* Executive-level decision support dashboard

---

## Author

**Arpita Rajput**

**Project:** SIOP Forecasting – Executive Dashboard

**Technology Stack:** Power BI, Power Query, DAX, Data Modeling, Business Intelligence.
