# US Airline Delay Analysis

This project explores US airline flight data to understand where delays are happening, what causes them, and how airlines and airports perform over time.

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

## Data Preparation
While working with the dataset, a few issues came up:

- Some rows had no flights (`arr_flights` was null) so they were removed since delay metrics wouldn’t make sense
- Airline names were inconsistent across years (eg: "Delta Air Lines Inc." vs "Delta Air Lines Network") so they were standardized
- Missing values in delay-related columns were handled carefully instead of blindly dropping rows
- A few negative values were checked and validated (early arrivals)

## Analysis Performed

### 1. Airline Performance
- Compared airlines based on traffic and delay rates
- Southwest, Delta, and American Airlines handled the highest volume
- Delay rates varied significantly even among top carriers

### 2. Airport Performance
- Major hubs like ATL, ORD, and DFW handled the most traffic
- Some mid-traffic airports showed higher delay rates than busy hubs

### 3. Delay Breakdown
- Late aircraft delay was the largest contributor
- Security delays had minimal impact
- This suggests most delays are operational rather than external

### 4. Correlation Analysis
- Strong relationship between carrier delays and late aircraft delays (~0.85)
- NAS delays also showed high correlation with other delay types
- Indicates delays are not independent, one issue can cascade into others

### 5. Distribution Insights
- Most flights fall within a moderate delay range
- A small number of extreme cases (outliers) significantly impact averages

## Key Takeaway
Delays are interconnected. Fixing airline-level operational issues can reduce multiple delay categories at once, especially late aircraft and NAS-related delays.

## Tools Used
- Python (Pandas, NumPy)
- Matplotlib, Seaborn for visualization
