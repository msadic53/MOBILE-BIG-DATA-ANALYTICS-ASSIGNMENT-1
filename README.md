# Mobile Big Data Analytics - Assignment 1

## Overview
This project analyzes mobile communication activity (SMS, calls, and internet usage) across Milan grid squares using three daily datasets from November 2013. The notebook loads, cleans, and merges the data, then answers the assignment questions with statistical summaries and visualizations.

## Data Sources
Files used:
- sms-call-internet-mi-2013-11-02.csv
- sms-call-internet-mi-2013-11-04.csv
- sms-call-internet-mi-2013-11-06.csv

All three files are concatenated into one dataframe.

## Approach and Key Decisions
1. **Load and merge**: Read the three CSVs and concatenate them into a single dataframe.
2. **Feature engineering**: Split the datetime column into date and time, then drop datetime.
3. **Missing values**: Apply mean imputation for smsin, smsout, callin, callout, and internet.
4. **Aggregation**: Create total_sms and total_calls, then drop the original in/out columns to simplify analysis.

## Data Summary 
- **Total records**: 6,564,031
- **Columns after aggregation**: 7
- **Unique grid squares (CellID)**: 10,000
- **Unique country codes**: 302

### Missing Values (before imputation)
Missing counts per column:
- smsin: 3,964,171
- smsout: 5,025,738
- callin: 4,761,685
- callout: 3,764,484
- internet: 3,621,117

Most missing values occurred in **smsout**. All missing values were imputed using the column mean.



## Peak Hour Analysis
- **Most common peak hour**: 12:00:00
- **Least common hour**: 03:00:00
- **Total calls by hour**: Mean, median, std, min, and max computed in the notebook using groupby on total_calls by time.

### Daytime vs Nighttime Activity
- **Daytime (6:00–20:00)**: 78.51% of total activity
- **Nighttime (20:00–6:00)**: 21.49% of total activity

### Domestic vs International Communication
- **Calls**: 33.11% domestic, 66.89% international
- **SMS**: 24.98% domestic, 75.02% international
- **International call ratio (inbound/outbound)**: 1.67

### Correlation Between Activity Types
- **Correlation (SMS vs Calls at grid level)**: 0.9862
- **Interpretation**: Strong positive relationship—high SMS areas tend to be high call areas.

## Visual Outputs Generated
- peak_hours_distribution.png
- domestic_vs_international_calls.png
- domestic_vs_international_sms.png
- international_call_volume.png
- sms_call_volume_correlation.png

## Tools and Libraries
- Python 3.x
- pandas
- numpy
- matplotlib

## How to Run
1. Place the three CSV files in the same folder as the notebook.
2. Install dependencies: pandas, numpy, matplotlib.
3. Open and run abubakam_MobileBigDataAnalytics_Ass1.ipynb from top to bottom.

## Notes
- Daytime is defined as 6:00 AM to 8:00 PM.
- Nighttime is defined as 8:00 PM to 6:00 AM.
- Domestic communication is identified using country code 39 (Italy).
