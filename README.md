
# E-Commerce Sales Analytics | ApexPlanet Task 5

### Final Executive Report, Data Automation & Business Intelligence

**ApexPlanet Data Analytics Internship — Task 5**

**Developed by:** Debdut Nandy  
**Project:** Online Retail Sales Analytics  
**Tools:** Python, Pandas, NumPy, Power BI, Excel, GitHub Actions

---

## Project Overview

This repository contains the final deliverables of my ApexPlanet
Data Analytics Internship.

The project analyzes historical e-commerce transactions to identify
sales trends, customer purchasing behavior, product performance and
opportunities for business improvement.

Task 5 brings together the findings from the previous four tasks
into a final executive report and an automated data-processing
pipeline using Python and GitHub Actions.

## Project Objectives

- Prepare a final executive analytics report.
- Consolidate key findings from exploratory data analysis.
- Present business insights through a Power BI dashboard.
- Incorporate customer segmentation and revenue forecasting.
- Automate data cleaning and KPI generation.
- Schedule the analytics pipeline using GitHub Actions.
- Provide actionable recommendations based on the analysis.

---

## Dataset

**Dataset:** UCI Online Retail  
**Source:** https://archive.ics.uci.edu/dataset/352/online+retail

The dataset contains transactional records from a UK-based
online retailer.

**Analysis period:** December 2010 – December 2011

The final month contains only partial data and should not be
compared directly with complete months.

### Data Preparation

The cleaning pipeline performs the following operations:

1. Removes records with missing product descriptions.
2. Removes duplicate transactions.
3. Converts columns to appropriate data types.
4. Excludes canceled transactions.
5. Removes invalid quantities and unit prices.
6. Calculates sales revenue for each transaction line.
7. Applies IQR-based outlier filtering.
8. Exports the cleaned dataset as a CSV file.

The cleaned dataset contains approximately 482,000 records.

---

## Executive Dashboard

The Power BI dashboard consolidates the principal business metrics
and provides an interactive overview of retail performance.

### Key Performance Indicators

| Metric | Result |
|---|---:|
| Total Revenue | £5.08 million |
| Total Orders | 18,088 |
| Units Sold | Approximately 3.02 million |
| Unique Customers | 4,185 |

### Dashboard Features

- Revenue by product
- Monthly revenue trends
- Monthly order trends
- Country-wise revenue distribution
- Quantity versus sales amount
- Customer revenue analysis
- Interactive country and month filters

![E-Commerce Sales Analytics Dashboard](screenshots/power_bi_dashboard.png)

---

## Key Analytical Findings

### 1. Geographic Revenue Concentration

The United Kingdom contributes the largest share of total revenue,
indicating that the business is heavily concentrated in its
domestic market.

### 2. Product Performance

Revenue is concentrated among several high-performing products,
including WHITE HANGING HEART T-LIGHT HOLDER.

Product-level analysis helps identify inventory priorities and
potential promotional opportunities.

### 3. Monthly Sales Patterns

Monthly revenue and order volumes fluctuate throughout the
analysis period, with notable activity toward the later months
of 2011.

December 2011 contains incomplete data and is treated separately
when interpreting monthly trends.

### 4. Customer Segmentation

K-Means clustering was applied to RFM features to identify
four customer segments:

- Recent, lower-spending customers
- Recent, high-frequency, high-spending customers
- Inactive, lower-spending customers
- Occasional customers

These segments provide a basis for differentiated customer
engagement and retention strategies.

### 5. Revenue Forecasting

A linear regression model was developed to predict daily revenue
using historical sales and calendar-based features.

| Evaluation Metric | Result |
|---|---:|
| Mean Absolute Error | £6,333.93 |
| Root Mean Squared Error | £7,868.82 |
| R² Score | 0.5060 |

The model explains approximately 50.6% of the variation in the
evaluation data. Its predictions should be interpreted alongside
the remaining forecasting error.

---

## Business Recommendations

**1. Strengthen customer retention**

Develop targeted retention campaigns for inactive customers and
personalized engagement strategies for high-value customers.

**2. Improve inventory planning**

Use product-level sales performance and historical demand patterns
to guide inventory allocation and replenishment decisions.

**3. Diversify geographic revenue**

Evaluate opportunities in international markets while maintaining
the company's established UK customer base.

---

## Automated Analytics Pipeline

A Python automation script processes the original dataset and
generates updated analytical outputs.

### Pipeline Workflow

Raw Dataset
    |
    v
Data Validation & Cleaning
    |
    v
Sales Amount Calculation
    |
    v
Outlier Filtering
    |
    v
Business KPI Calculation
    |
    v
CSV & Excel Report Generation

### Generated Outputs

**online_retail_cleaned.csv**

Contains the cleaned transaction-level dataset.

**retail_analytics_report.xlsx**

Contains four analytical worksheets:

- KPIs
- Monthly Sales
- Top Products
- Country Sales

---

## GitHub Actions Automation

GitHub Actions is used to execute the analytics pipeline
automatically without requiring a locally installed Python
environment.

The workflow:

1. Checks out the GitHub repository.
2. Configures the Python environment.
3. Installs the required dependencies.
4. Executes the Python automation script.
5. Verifies the generated CSV and Excel files.
6. Uploads the results as downloadable workflow artifacts.

### Execution Schedule

The workflow is configured to run every Monday at
03:30 UTC (09:00 IST).

It can also be executed manually using the
`workflow_dispatch` trigger.

### Workflow Status

The GitHub Actions workflow was successfully tested.

[View GitHub Actions Workflow](https://github.com/Deb124-source/ApexPlanet-Task5-Debdut-Nandy/actions)

### Downloading Generated Reports

1. Open the repository's Actions tab.
2. Select Retail Analytics Automation.
3. Open a successful workflow run.
4. Locate the Artifacts section.
5. Download the retail-analytics-results artifact.

---

## Repository Structure

```text
ApexPlanet-Task5-Debdut-Nandy/
|
|-- .github/
|   |-- workflows/
|       |-- retail_automation.yml
|
|-- data/
|   |-- Online Retail.xlsx
|
|-- scripts/
|   |-- retail_automation.py
|
|-- reports/
|   |-- ApexPlanet_Final_Executive_Analytics_Report.pdf
|
|-- requirements.txt
|-- README.md
```

Generated CSV and Excel reports are available through
GitHub Actions artifacts.

---

## Running the Pipeline

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Run the automation script:

```bash
python scripts/retail_automation.py \
  --input "data/Online Retail.xlsx" \
  --output "outputs"
```

The pipeline creates the `outputs` directory and generates
the cleaned dataset and Excel analytics report.

Alternatively, run the pipeline directly from GitHub Actions.

---

## Final Executive Report

The two-page executive report consolidates the main findings
from the complete internship project.

It includes:

- Executive summary and business KPIs
- Power BI dashboard
- Five key analytical insights
- Customer segmentation
- Revenue forecasting results
- Three actionable business recommendations
- Automated analytics pipeline overview

[View Final Executive Report](reports/ApexPlanet_Final_Executive_Analytics_Report.pdf)

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Data processing and automation |
| Pandas | Data cleaning and aggregation |
| NumPy | Numerical operations |
| OpenPyXL | Excel report generation |
| Power BI | Interactive dashboard |
| Scikit-learn | Customer segmentation and forecasting |
| GitHub Actions | Scheduled pipeline execution |
| GitHub | Version control and project documentation |

---

## Internship

**Organization:** ApexPlanet  
**Domain:** Data Analytics  
**Task:** 5 — Final Report, Automation & Presentation

This repository represents the final stage of the internship,
combining exploratory analysis, SQL, data visualization,
advanced analytics and workflow automation into a complete
end-to-end analytics project.

---

## Author

**Debdut Nandy**

B.Tech in Computer Science and Engineering (AI & ML)  
Brainware University

**GitHub:** https://github.com/Deb124-source  
**LinkedIn:** https://www.linkedin.com/in/debdut-nandy-4b0a88321/
