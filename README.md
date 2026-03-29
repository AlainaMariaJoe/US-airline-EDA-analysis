
# US Airline Delay Analysis

End-to-end analysis of US airline delay data to understand traffic patterns, delay causes, and performance across airlines and airports.

## Dataset Overview
Dataset - https://www.kaggle.com/datasets/ryanjt/airline-delay-cause
- ~398K aggregated records
- Time range: 2003- 2025
- Includes airline, airport, flight counts, and delay breakdowns

## Objective
The goal was to move beyond basic metrics and answer:
- Which airlines and airports are most affected by delays?
- What are the main drivers of delays?
- Are delays caused by isolated factors or connected issues?

The project includes data cleaning, exploratory analysis, and visualization using EDA

---

##  1. Data Cleaning & Preparation

Main issues observed in the dataset:

- Rows with no flights (`arr_flights` = null)
- Inconsistent airline names across years
- Missing values in delay-related columns
- Few negative values (early arrivals)

Steps performed:

- Removed rows where `arr_flights` was null (no flights → no analysis value)
- Handled missing values in delay columns instead of dropping entire rows
- Standardized airline names (e.g., "Delta Air Lines Inc." → "Delta Air Lines")
- Checked and retained valid negative values (representing early arrivals)
- Fixed data types (floats → integers where applicable)

---

##  2. Dataset Structure

The dataset is already aggregated and includes:

- Airline (`carrier`, `carrier_clean`)
- Airport
- Flight counts (`arr_flights`)
- Delay counts (`arr_del15`)
- Delay causes:
  - Carrier
  - Weather
  - NAS (National Airspace System)
  - Security
  - Late Aircraft

This structure reflects real-world reporting data rather than raw flight-level data.

---

##  3. Analysis Performed

### a) Airline Performance
- Identified busiest airlines based on total flights
- Compared delay rates across airlines
- Found airlines with highest and lowest delay %

### b) Airport Analysis
- Identified busiest airports by traffic
- Compared delay rates across airports
- Observed that some mid-traffic airports had higher delay rates than major hubs

### c) Delay Cause Analysis
- Analyzed contribution of each delay type
- Compared total delays by cause

### d) Correlation Analysis
- Checked relationships between delay types
- Identified strong correlations between:
  - Carrier delay & Late aircraft delay
  - NAS delay & other operational delays

### e) Distribution & Outliers
- Most flights fall under moderate delay ranges
- Few extreme cases significantly impact averages

---

##  4. Key Findings

### 1. Airline Insights
- Southwest, Delta, and American Airlines handle the highest traffic
- Delay rates vary even among high-volume carriers

### 2. Airport Insights
- ATL, ORD, and DFW are the busiest airports
- Some medium-traffic airports show higher delay rates than major hubs

### 3. Delay Causes
- Late aircraft delay is the biggest contributor
- Security delays are minimal

### 4. Correlation
- Carrier delay ↔ Late aircraft delay (~0.85)
- NAS delay also strongly linked with other delays

This shows delays are interconnected rather than isolated events.

---

## 💡 5. Key Insight

Delays are not independent.

Improving airline operations (carrier delays) can reduce multiple delay types, especially late aircraft and NAS delays.

---

##  6. Visualizations

Used:
- Matplotlib
- Seaborn

Charts created:
- Top airlines by delay rate
- Airport delay comparisons
- Delay cause distribution
- Correlation heatmap

---

##  Tools Used

- Python (Pandas, NumPy)
- Matplotlib & Seaborn
- Google Colab

---


##  Notes

Most effort went into cleaning and standardizing the data. The dataset reflects real-world challenges where data is not clean or consistent.
