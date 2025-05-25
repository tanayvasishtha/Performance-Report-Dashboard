# Plant Co. Performance Report Dashboard

## Overview

A comprehensive Power BI dashboard that provides dynamic performance analysis of Plant Co.'s quantity sales for 2023, featuring SWITCH measures and conditional formatting to deliver actionable insights.



## Features

- **Dynamic KPI Tracking** - Real-time metrics including YTD (555.66K), YTD vs PYTD comparison (17.05K), PYTD (538.61K), and Gross Profit % (39.62%)
- **Geographical Performance Analysis** - Bottom 10 countries comparison showing YTD vs PYTD variances
- **Time-Series Visualization** - Monthly performance waterfall chart with conditional formatting
- **Product Segmentation** - Filter by Indoor, Landscape, and Outdoor product types
- **Profitability Analysis** - Scatter plot mapping GP% against Quantity for account profitability segmentation

## Project Structure

### 1. Data Layer (Power Query)
- Automated ETL process for data cleansing and transformation
- Star schema data model with dimension and fact tables
- Custom column calculations and parameter-driven queries

### 2. Model Layer (DAX Measures)
- **SWITCH Measures** for dynamic metric selection
- Year-to-date (YTD) calculations
- Previous year-to-date (PYTD) comparisons
- Gross Profit percentage formulas
- Time intelligence functions

### 3. Visuals Layer
- Matrix visualization with conditional formatting
- Waterfall chart for monthly performance tracking
- Combo charts for trend analysis
- Scatter plot for profitability segmentation
- KPI cards with dynamic formatting

### 4. Report Publishing
- Interactive filters and slicers
- Cross-filtering capabilities
- Mobile-optimized layout
- Automated refresh schedule

## Data Model

The dashboard uses a structured data model with:
- **Dimension Tables**:
  - Dim_Accounts
  - Dim_Date
  - Dim_Product
- **Fact Tables**:
  - Fact_Sales
- **Calculation Groups**:
  - SWITCH (for dynamic measure selection)
  - YTD
  - PYTD
  - GP%

## Key DAX Measures

```dax
// Sample measures (not actual code, for illustration)
YTD Sales = 
    CALCULATE([Total Sales], DATESYTD(Dim_Date[Date]))

PYTD Sales = 
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DATESYTD(Dim_Date[Date])))

YTD vs PYTD = [YTD Sales] - [PYTD Sales]

GP% = DIVIDE([Gross Profit], [Total Sales], 0)
```

## Installation and Usage

1. **Prerequisites**:
   - Power BI Desktop (latest version recommended)
   - Access to Plant Co. data source

2. **Setup**:
   - Clone this repository
   - Open the `.pbix` file in Power BI Desktop
   - Configure data source connections

3. **Customization**:
   - Adjust date parameters for current reporting period
   - Modify product type filters as needed
   - Configure conditional formatting thresholds

## Future Enhancements

- Integration with automated data pipeline
- Additional profitability metrics
- Regional comparison dashboard
- Forecast modeling with what-if parameters
- Mobile-optimized view

## Contributors

- Tanay Vasishtha (Project Lead)

## License

This project is licensed under the MIT License - see the LICENSE file for details.
