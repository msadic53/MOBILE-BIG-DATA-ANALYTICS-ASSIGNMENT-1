# Mobile Big Data Analytics - Assignment 1

## Project Overview
This project analyzes mobile communication patterns (SMS, calls, and internet usage) across geographic grid squares in Milan, Italy using data from November 2-6, 2013. The analysis explores temporal patterns, domestic vs. international communication, and correlations between different communication types.

## Datasets
The analysis combines three datasets:
- `sms-call-internet-mi-2013-11-02.csv` - Data from November 2, 2013
- `sms-call-internet-mi-2013-11-04.csv` - Data from November 4, 2013
- `sms-call-internet-mi-2013-11-06.csv` - Data from November 6, 2013
- I use combined the above dataset by using the concat method from pandas.

**Total Records:** Combined dataset containing comprehensive communication activity across all grid squares

## Data Features
- **CellID:** Geographic grid square identifier
- **DateTime:** Timestamp of activity
- **countrycode:** International calling code (39 = Italy/Domestic)
- **smsin/smsout:** Incoming and outgoing SMS counts
- **callin/callout:** Incoming and outgoing call counts
- **internet:** Internet usage data

## Analysis Sections

### 1. Data Preprocessing
- Loading and combining three separate CSV files using the concat method from pandas
- The dataframe orginally had 6 features(colunms)
- Splitting datetime into separate date and time columns by the total Data features to be 9 
- The datetime feature was subsequently dropped
- Handling missing values using mean imputation
- Aggregating SMS and call metrics into total columns

### 2. Exploratory Analysis
- Use the info() method, five features had datatype float, 2 had datatype int and 2 also had  datatype object 
-



- Total number of records across all datasets
- Unique grid squares (CellIDs) in the region
- Unique country codes present in the data
- 
### 3. Peak Hour Analysis
- Identification of peak and off-peak hours
- Distribution visualization of activity by hour
- Statistical analysis (mean, median, std, min, max) of total calls by hour

### 4. Temporal Activity Patterns
- Daytime vs. Nighttime activity analysis (6am-8pm vs. 8pm-6am)
- Percentage breakdown of total activity by time period
- Visualization of temporal patterns

### 5. Domestic vs. International Communication
- Analysis of calls between domestic (Italy, countrycode=39) and international contacts
- Percentage breakdown of call volume
- Percentage breakdown of SMS volume
- Hourly trends comparison

### 6. International Call Patterns
- Ratio analysis of outbound to inbound international calls
- Time-series visualization of international call trends

### 7. Correlation Analysis
- Pearson correlation between SMS volume and call volume at grid level
- Scatter plot visualization
- Interpretation of correlation strength

## Key Findings
- **Peak Hours:** Identified most active and least active hours for communication
- **Activity Distribution:** Breakdown of daytime vs. nighttime communication patterns
- **Domestic Dominance:** Percentage of domestic versus international calls and SMS
- **International Patterns:** Ratio and trends of international communication
- **SMS-Call Correlation:** Strength and nature of relationship between SMS and calling behavior

## Technologies & Libraries
- **Python 3.x**
- **pandas:** Data manipulation and analysis
- **numpy:** Numerical computing
- **matplotlib:** Data visualization

## How to Run
1. Ensure all three CSV files are in the same directory as the notebook
2. Install required dependencies: `pandas`, `numpy`, `matplotlib`
3. Open and run `MBD assignment 1.ipynb` in Jupyter Notebook or JupyterLab
4. Execute cells sequentially to perform the complete analysis

## Output Files
The notebook generates several visualization outputs:
- `domestic_vs_international_calls.png` - Pie chart of call distribution
- `domestic_vs_international_sms.png` - Pie chart of SMS distribution
- `international_call_volume.png` - Bar chart of international call volume
- `sms_call_volume_correlation.png` - Scatter plot of SMS-call correlation

## Notes
- Missing values in numerical columns were filled using column means
- Daytime is defined as 6:00 AM to 8:00 PM
- Nighttime is defined as 8:00 PM to 6:00 AM
- Domestic calls/SMS are identified by country code 39 (Italy)
