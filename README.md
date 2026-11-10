
# Hotel Revenue Analysis & Dynamic Pricing Dashboard

An end-to-end hotel revenue analytics and dynamic pricing project using Python, SQL, and Tableau. This project analyses historical hotel booking data, identifies business trends, and explores how different pricing strategies can influence estimated hotel revenue.

## Project Overview

The project focuses on understanding hotel performance and exploring data-driven pricing strategies for two hotel types:

- City Hotel
- Resort Hotel

It combines historical booking analysis with a rule-based dynamic pricing simulation. An interactive Tableau dashboard brings the findings together and allows users to compare hotel performance and pricing scenarios.

## Project Objectives

- Analyse historical hotel booking data.
- Understand revenue, ADR, occupancy, and cancellation trends.
- Compare City Hotel and Resort Hotel performance.
- Identify seasonal booking and revenue patterns.
- Examine the relationship between booking lead time and cancellations.
- Develop a rule-based dynamic pricing simulation.
- Compare Conservative, Moderate, and Aggressive pricing scenarios.
- Estimate the potential revenue impact of different pricing strategies.
- Present findings through an interactive Tableau dashboard.

## Tools and Technologies

| Tool / Technology | Purpose |
|---|---|
| Python | Data cleaning, feature engineering, and pricing simulation |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical calculations |
| Matplotlib | Data visualisation |
| Seaborn | Exploratory data visualisation |
| SQL | Business analysis and querying |
| Jupyter Notebook | Analysis workflow and documentation |
| Tableau Desktop | Interactive dashboard development |
| Git and GitHub | Version control and project sharing |

## Project Structure

```text
Hotel-Revenue-Management/
│
├── dashboard/
│   └── Hotel_Pricing_Dashboard.twbx
│
├── data/
│   ├── raw/
│   │   └── hotel_bookings.csv
│   │
│   └── processed/
│       ├── hotel_bookings_cleaned.csv
│       ├── hotel_bookings_cleaned.parquet
│       ├── hotel_daily_pricing.csv
│       ├── hotel_pricing_scenarios.csv
│       └── hotel_scenario_summary.csv
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_cleaning_and_feature_engineering.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
│   ├── 04_sql_business_analysis.ipynb
│   └── 05_dynamic_pricing_engine.ipynb
│
├── project structure.png
├── README.md
├── requirements.txt
└── .gitignore
```

## Project Workflow

### 1. Data Understanding

- Explored the original hotel booking dataset.
- Examined the available variables and their data types.
- Investigated the structure and quality of the data.
- Identified important variables for hotel revenue and booking analysis.

### 2. Data Cleaning and Feature Engineering

- Checked for missing values and duplicate records.
- Cleaned and prepared the booking data.
- Created additional features required for analysis.
- Exported the cleaned dataset in CSV and Parquet formats.

### 3. Exploratory Data Analysis

Analysed historical hotel booking data to understand:

- Monthly revenue trends.
- Revenue differences between City Hotels and Resort Hotels.
- Average Daily Rate (ADR).
- Occupancy patterns.
- Seasonal booking behaviour.
- Cancellation rates.
- The relationship between lead time and cancellations.

### 4. SQL Business Analysis

Used SQL to investigate business questions and extract insights from the cleaned hotel booking data.

The analysis focused on hotel performance, booking behaviour, revenue patterns, and other business-relevant metrics.

### 5. Dynamic Pricing Engine

Developed a rule-based pricing simulation using historical hotel demand and booking indicators.

The engine generates:

- Daily demand classifications.
- Baseline ADR.
- Recommended ADR.
- Price multipliers.
- Expected room demand.
- Estimated dynamic revenue.
- Comparisons across pricing scenarios.

## Dynamic Pricing Methodology

The pricing engine uses a baseline ADR and a demand-based price multiplier to calculate the recommended ADR.

### Recommended ADR

Recommended ADR is calculated as:

`Recommended ADR = Baseline ADR × Price Multiplier`

The simulation uses the following illustrative demand-based multipliers:

| Demand Level | Price Multiplier |
|---|---:|
| Low | 0.90 |
| Normal | 1.00 |
| High | 1.10 |
| Very High | 1.20 |

### Pricing Scenarios

Three pricing scenarios are used to represent different levels of customer price sensitivity.

| Scenario | Elasticity |
|---|---:|
| Conservative | 0.30 |
| Moderate | 0.60 |
| Aggressive | 0.90 |

### Expected Room Demand

Expected room demand is estimated using:

`Expected Rooms = Baseline Rooms × (Price Multiplier ^ -Elasticity)`

Expected rooms are capped using a capacity proxy derived from historical booking data.

### Dynamic Revenue

`Dynamic Revenue = Expected Rooms × Recommended ADR`

### Revenue Uplift

`Revenue Uplift = Dynamic Revenue - Baseline Revenue`

The scenarios help compare how different customer price-sensitivity assumptions affect expected room demand and estimated revenue.

## Tableau Dashboard

The interactive dashboard is divided into two main sections.

### Historical Hotel Performance

The historical analysis section includes:

- Estimated Historical Room Revenue
- Average ADR
- Occupancy Rate
- Cancellation Rate
- Monthly Revenue Trend
- Seasonality Heatmap
- Hotel Revenue Comparison
- Hotel ADR Comparison
- Hotel Cancellation Comparison
- Lead Time and Cancellations

### Dynamic Pricing Simulation

The dynamic pricing section includes:

- Daily Baseline ADR vs Recommended ADR
- Estimated Revenue by Hotel and Selected Pricing Scenario
- Average Recommended ADR
- Expected Revenue
- Estimated Revenue Uplift

### Interactive Dashboard Controls

The dashboard includes two dropdown controls:

**Hotel Type**
- All
- City Hotel
- Resort Hotel

**Pricing Scenario**
- Conservative
- Moderate
- Aggressive

The Hotel Type selection filters the relevant historical and dynamic pricing analyses.

The Pricing Scenario selection updates the scenario-based revenue and uplift calculations.

The Average Recommended ADR is based on hotel and demand conditions and does not change across pricing scenarios in the current model. The scenarios change expected demand through their elasticity assumptions.

## Key Business Questions Explored

1. How does hotel revenue vary across months?
2. Which hotel type generates higher estimated room revenue?
3. How does ADR differ between City Hotels and Resort Hotels?
4. Which seasons show stronger or weaker booking patterns?
5. How do cancellations vary across hotel types?
6. Is booking lead time associated with cancellation behaviour?
7. How does recommended ADR compare with baseline ADR?
8. How do different pricing scenarios influence expected room demand?
9. Which pricing scenario produces the highest estimated revenue?
10. How does estimated revenue uplift vary between hotel types?

## Assumptions and Limitations

This project is an analytical and illustrative pricing simulation, not a production revenue-management system.

- Historical room revenue is estimated using ADR multiplied by stay duration for non-cancelled bookings. It is not verified financial revenue.
- Occupancy and capacity calculations use a capacity proxy derived from historical occupied rooms, not verified hotel room inventory.
- The recommended ADR is calculated from baseline ADR and demand-based price multipliers.
- Pricing scenarios change the assumed customer price elasticity and therefore affect expected room demand.
- The scenario results are simulated counterfactual estimates, not observed outcomes from actual pricing experiments.
- Revenue uplift is an estimate under the model assumptions and is not a guaranteed increase in revenue.
- The model does not incorporate every real-world factor, such as competitor pricing, operating costs, distribution commissions, and actual customer booking responses.
- Results depend on the assumptions and quality of the underlying dataset.

## How to Explore the Project

1. Review the Jupyter notebooks in numerical order to understand the analysis workflow.
2. Explore the Tableau dashboard.
3. Select a hotel type to compare City Hotel and Resort Hotel performance.
4. Change the pricing scenario to compare Conservative, Moderate, and Aggressive assumptions.
5. Observe how expected revenue, revenue uplift, and other relevant dashboard components respond.

## Repository Contents

- **dashboard:** Packaged Tableau workbook.
- **data/raw:** Original booking dataset, subject to source redistribution permissions.
- **data/processed:** Cleaned dataset and generated pricing outputs.
- **notebooks:** Data understanding, cleaning, exploratory analysis, SQL business analysis, and dynamic pricing implementation.

## Dashboard Link

**Tableau Public:** [View the Interactive Dashboard](https://public.tableau.com/app/profile/bushra.syeda/viz/Hotel_Pricing_Dashboard/Dashboard1)

## Dataset Source

This project uses the Hotel Booking Demand dataset, originally described by:

Antonio, N., de Almeida, A., & Nunes, L. (2019).
"Hotel booking demand datasets."
Data in Brief, 22, 41–49.
https://doi.org/10.1016/j.dib.2018.11.126

Dataset download: https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

The dataset contains hotel booking records for a city hotel and a resort hotel in Portugal, covering July 2015 to August 2017. It includes both completed and cancelled bookings.

The original research article is published under a Creative Commons Attribution licence (CC BY). Check the specific Kaggle copy's licence and attribution requirements before redistributing the downloaded files.

## Project Summary

This project demonstrates an end-to-end analytics workflow, combining data preparation, exploratory analysis, SQL-based business investigation, rule-based pricing simulation, and interactive dashboard development.

It aims to demonstrate how historical booking data can be transformed into business insights and used to explore potential pricing strategies.
