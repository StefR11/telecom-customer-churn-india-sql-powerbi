
The curated data warehouse layer powers an Executive Summary Power BI dashboard used to identify churn drivers, at-risk segments, service weaknesses, and retention opportunities.

---

## 🎯 Project Goals
- Build a complete ETL pipeline from CSV to SQL Server
- Design staging and production layers
- Perform data quality checks and NULL remediation
- Create warehouse-ready analytical tables
- Analyze churn across:
  - demographics
  - geography
  - contracts
  - services
  - tenure
  - churn reasons
- identify churner profiles
- support targeted marketing campaigns
- improve customer retention strategy

---

## 🏗️ Data Architecture
The project follows a **staging → production → reporting** architecture:

### 1) Source
- CSV customer dataset

### 2) Staging Layer
- `stg_Churn`
- raw imported dataset
- initial data exploration
- percentage distribution profiling
- NULL audits

### 3) Production Layer
- `prod_Churn`
- cleansed NULL values
- standardised service fields
- churn-ready analytical model

### 4) Reporting Layer
SQL views created for Power BI:
- `vw_ChurnData`
- `vw_JoinData`

---

## 🛠️ Tools & Technologies
- **CSV File**
- **SQL Server**
- **SSMS Import Wizard**
- **SQL Views**
- **Power Query**
- **Power BI**
- **DAX**
- **TMDL documentation**

---

## 🔎 Data Quality & SQL Engineering
The SQL workflow includes:

### Percentage distribution analysis
Exploratory profiling was performed to validate:
- gender distribution
- contract mix
- state distribution
- revenue contribution
- internet type segmentation

### NULL auditing
A full-column NULL audit was performed across the staging table to identify missing values before production load.

### NULL standardisation
NULL values were replaced using business-friendly defaults:
- `No`
- `None`
- `Others`

Examples:
- missing service fields → `No`
- missing internet type → `None`
- missing churn category → `Others`

### Production table creation
A clean production table was generated using:
- `SELECT INTO`
- `ISNULL()`
- standardized defaults
- reporting-ready column values

### SQL reporting views
Two reporting views were created for Power BI:
- **vw_ChurnData** → Churned + Stayed customers
- **vw_JoinData** → New joiners only

This improves:
- model performance
- reusability
- report refresh simplicity

---

## 📊 Executive Summary Dashboard
### KPI Cards
- Total Number of Customers
- New Joiners
- Total Churn
- Churn Rate

### Dashboard Visuals
- Age group churn analysis
- Payment method churn rate
- Contract churn rate
- Tenure-based churn trend
- Top 5 states by churn
- Churn category analysis
- Internet type churn rate
- Service risk matrix
- Monthly charge slicer
- Married slicer

### Technical Documentation Page
A second page documents:
- DAX measures
- semantic model logic
- AI-generated TMDL descriptions
- measure definitions

---

## 🔍 Key Business Insights
### High-risk demographic
Female customers account for **64% of the customer population**.

Within this segment, **31.5% are aged above 50**, making this the highest-priority retention segment.

### Competitor churn
The strongest churn reason is **competitor activity**:
- 496 churners due to competitors
- 180 left for better devices
- 183 left for better offers

### Service red flags
A **60% churn threshold** is used as a risk alert.

Customers without these services are more likely to churn:
- Device Protection Plan
- Online Backup
- Online Security
- Premium Support
- Streaming Music

### Underperforming subscribed services
Even subscribed customers are churning heavily for:
- Internet Service
- Phone Service
- Unlimited Data
- Paperless Billing

This points to quality and value-delivery issues.

---

## 📈 Business Recommendations
- Build **female 50+ retention campaigns**
- improve **device upgrade offers**
- create **competitor-match bundles**
- strengthen sticky service adoption
- review internet and phone service quality
- reassess unlimited data pricing

---


