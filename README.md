# E-Commerce Sales Analytics Dashboard

![Project Status](https://img.shields.io/badge/status-active-brightgreen)
![Python](https://img.shields.io/badge/python-3.13%2B-blue)
![Streamlit](https://img.shields.io/badge/streamlit-1.35%2B-orange)

## Overview

An AI-powered data analytics and business intelligence dashboard designed to convert raw e-commerce sales data into strategic business decisions. The application identifies clear trends, business drivers, risks, opportunities, and actionable management recommendations from transactional sales data.

## Problem Statement

Raw e-commerce sales data contains valuable insights that are difficult to extract manually. This dashboard automates the process of converting millions of transactional records into interactive visualizations, KPIs, and actionable business intelligence that helps management make data-driven decisions.

## Features

### Executive Overview
- **Top 5 KPIs**: Total Revenue, Total Orders, Total Customers, Avg Order Value, Growth YoY
- **Historical Revenue Trends**: Monthly line charts showing revenue trajectory
- **Quarterly Heatmaps**: Revenue distribution across quarters and months
- **Seasonality Analysis**: Identify peak sales periods

### Sales & Product Analysis
- **Category Revenue Rankings**: Top 10 categories by revenue
- **Profit Margin Analysis**: Average profit margins across categories
- **Product Performance Scatter**: Revenue vs. profit margin visualization
- **Monthly Category Trends**: Revenue trends by product category over time

### Customer & Risk Analysis
- **RFM Segmentation**: Recency-Frequency-Monetary customer segmentation
- **Customer Lifetime Value**: Identify high-value customers
- **At-Risk Customer Identification**: Customers likely to churn
- **Geographic Analysis**: Revenue by region
- **Opportunities & Risks**: Strategic insights with recommended actions

### Data Overview
- **Column Dictionary**: Complete data schema reference
- **Data Quality Report**: Cleaning and preprocessing summary
- **Raw Data Preview**: First 10 records for inspection

## Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd IBM-PRoject
   ```

2. **Create a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Run the Streamlit application**:
   ```bash
   streamlit run app.py
   ```

2. **Open your browser** and navigate to `http://localhost:8501`

3. **Upload your dataset** (CSV format) via the sidebar, or use the built-in synthetic data generator

4. **Navigate between sections** using the sidebar menu

## Dataset Format

The application expects a CSV file with the following columns (flexible matching supported):

| Column | Description | Example |
|--------|-------------|---------|
| `Order_ID` | Unique order identifier | ORD-202345678 |
| `Product` | Product name | Laptop Pro 15 |
| `Category` | Product category | Electronics |
| `Quantity` | Units sold | 3 |
| `Unit_Price` | Price per unit ($) | 1200.00 |
| `Revenue` | Total order revenue ($) | 3600.00 |
| `Cost` | Cost of goods sold ($) | 2400.00 |
| `Profit` | Gross profit ($) | 1200.00 |
| `Profit_Margin` | Profit as % of revenue | 33.3 |
| `Customer_ID` | Unique customer identifier | CUST-12345 |
| `Country` | Country of purchase | United States |
| `Region` | Geographic region | North America |
| `Payment_Method` | Payment method | Credit Card |
| `Order_Date` | Date and time of order | 2023-06-15 14:30:00 |

## Architecture

### Single-File Design
The entire application is contained in a single `app.py` file for portability and ease of deployment:

- **Data Ingestion**: CSV upload with fallback to synthetic data generator
- **Data Cleaning**: Automated handling of missing values, duplicates, and outliers
- **Backend Processing**: Pandas-based data transformation and aggregation
- **Visualization Engine**: Plotly-based interactive charts following design system guidelines
- **ML Component**: Scikit-learn for RFM customer segmentation

### Design System Compliance
All visualizations follow the validated data visualization method:
- Color palette validated for CVD safety (ΔE ≥ 8)
- Thin marks, hairline gridlines, 2px gaps between bars
- 8px+ markers with 2px surface rings
- Legends present for all multi-series charts
- Table views available for all charts
- Crosshair + hover tooltips on all charts

## How It Works

1. **Data Loading**: The system loads CSV data or generates realistic synthetic data for demonstration
2. **Data Cleaning**: Automated handling of missing values, invalid records, and date parsing
3. **KPI Calculation**: Key metrics computed from cleaned data with YoY comparison
4. **Visualization**: Interactive Plotly charts rendered with validated design system parameters
5. **Customer Segmentation**: RFM analysis assigns customers to 5 segments (Champions, Loyal, Potential, At Risk, Lost)
6. **Insights Generation**: Strategic recommendations based on data patterns

## Dependencies

- Python 3.13+
- Streamlit 1.35+ (Web framework)
- Pandas 2.2+ (Data manipulation)
- NumPy 2.0+ (Numerical computing)
- Plotly 6.0+ (Interactive visualizations)
- Scikit-learn 1.5+ (Machine learning)

## Project Structure

```
IBM-PRoject/
├── app.py              # Main dashboard application (single file)
├── requirements.txt    # Python dependencies
├── README.md           # Project documentation
├── PROJECT_REPORT.md   # Business intelligence report (Word document draft)
└── .gitignore          # Git ignore rules
```

## Key Metrics

The dashboard calculates and displays these core KPIs:

1. **Total Revenue**: Sum of all order revenues in the selected period
2. **Total Orders**: Number of unique orders
3. **Total Customers**: Unique customer count
4. **Average Order Value**: Revenue per order
5. **Revenue Growth**: Year-over-year growth percentage
6. **Profit Margin**: Average gross profit percentage

## Business Insights

The dashboard provides actionable intelligence in three categories:

### Risks Identified
- Customer churn indicators (high recency, low frequency)
- Low-margin product categories
- Geographic revenue concentration
- Seasonal demand volatility

### Opportunities
- High-growth product categories
- Loyal customer segments for retention campaigns
- Geographic expansion potential
- Holiday season revenue optimization

### Recommended Actions
- Targeted marketing campaigns for at-risk customers
- Inventory optimization for high-margin categories
- Weekend staffing and flash sale strategies
- Loyalty program development for champions segment

## License

This project is part of the IBM SkillsBuild Academic Internship Capstone Project.

## References

- Data Visualization Method: Validated category palette, mark specifications, anti-patterns
- Streamlit Documentation: https://docs.streamlit.io
- Plotly Documentation: https://plotly.com/python/
- Pandas Documentation: https://pandas.pydata.org/docs/

---

**Generated with [Claude Code](https://claude.com)**
