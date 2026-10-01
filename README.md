# Supply Chain Performance & Procurement Analytics

**Interactive Power BI Dashboard | Procurement | Supplier Performance | Logistics | Cost Analysis**

An end-to-end analytics project exploring procurement spending, supplier delivery performance, transportation modes, and lead-time variability using a shipment-level dataset of 1,000 records.

---

## Dashboard Preview

![Supply Chain Executive Overview](screenshots/01_executive_overview.png)

*Executive overview of procurement spend, delivery performance, and supply chain indicators.*

---

## 1. Business Problem

Procurement and supply chain teams need visibility into spending patterns, supplier reliability, transportation performance, and delivery lead times to support operational decisions.

This project analyzes shipment data to identify performance gaps, spending concentration, and operational risk signals.

### Business Questions

- How is procurement spend distributed across suppliers and product categories?
- Which suppliers show lower on-time delivery performance?
- How do transportation modes relate to transit time and delivery performance?
- How much spending is associated with late shipments?
- What operational patterns deserve further investigation?

---

## 2. Dashboard Features

The Power BI report is organized into the following analytical sections:

1. **Executive Overview** — Main KPIs and overall supply chain performance.
2. **Supplier Performance & Spend Exposure** — Supplier-level delivery performance and spending concentration.
3. **Transportation & Lead Time Analysis** — Transit time and delivery performance by shipping mode.
4. **Procurement Spend & Cost Analysis** — Spending patterns across categories and suppliers.
5. **Operational Exceptions & Risk Signals** — Areas requiring further review.
6. **Data Methodology & Quality** — Data preparation, definitions, and analytical limitations.

---

## 3. Key Findings & Business Insights

The analysis covers 1,000 shipment records from January 2024 to December 2025.

### 1. Overall Delivery Performance

- On-time delivery (OTD): 79.7%
- Late shipments: 203 out of 1,000
- Average transit time: 9.5 days
- Average order-to-delivery lead time: 11.6 days

**Business Insight:**

Approximately one in five shipments was classified as late. This indicates an opportunity to investigate delivery reliability, lead-time variability, and supplier performance.

### 2. Supplier Performance Differences

Observed on-time delivery rates vary across suppliers:

- Atlas Manufacturing: 66.1%
- Global Parts Inc: 72.0%
- Midwest Industrial: 85.5%
- Pacific Supply Co: 87.1%

**Business Insight:**

The difference between supplier delivery rates suggests that supplier performance should be monitored individually rather than relying only on an overall OTD metric.

Suppliers with lower observed OTD may warrant a closer review of delivery patterns, lead times, and operational constraints before making sourcing decisions.

### 3. Procurement Spend Exposure

- Total procurement spend: approximately $8.28M
- Spend associated with late shipments: approximately $1.57M
- Late spend as a share of total spend: 19.0%

**Business Insight:**

A meaningful share of procurement spend is associated with shipments classified as late. This creates a useful monitoring indicator for procurement teams, although it does not measure financial loss or the cost of delays.

Further analysis would be needed to estimate the actual business impact of late deliveries.

### 4. Transportation & Transit Time

Observed performance by transportation mode:

- Air: 100% OTD; 2.9 average transit days
- Road: 80.8% OTD; 5.8 average transit days
- Rail: 69.6% OTD; 10.3 average transit days
- Sea: 61.4% OTD; 28.4 average transit days

**Business Insight:**

Transportation modes show different delivery outcomes and transit times in this dataset. These results can support discussions about shipping requirements, but they should be interpreted alongside shipment characteristics, routes, costs, and service expectations.

### 5. Supplier Spend Concentration

- Top 5 suppliers account for approximately 43.2% of total spend.
- Top 10 suppliers account for approximately 76.1% of total spend.

**Business Insight:**

Procurement spend is concentrated among a relatively small group of suppliers. This makes supplier-level monitoring and continuity planning relevant areas for further analysis.

Spend concentration alone does not establish supply risk; dependency, substitutability, contract terms, and criticality would also need to be assessed.

### 6. Recommended Areas for Further Investigation

Based on the observed patterns, the next analytical steps could include:

- Reviewing delivery performance trends over time.
- Investigating the causes of late shipments by supplier and transportation mode.
- Comparing supplier performance with purchasing volume and product category.
- Adding promised delivery dates to enable more meaningful delivery compliance measures.
- Incorporating inventory and demand data to evaluate stockout exposure and replenishment performance.

For additional detail, see [Key Findings](documentation/Key_Findings.md).

---

## 4. Tools & Methodology

**Tools**
- Microsoft Power BI
- Power Query
- DAX
- Microsoft Excel

**Analytical workflow**
1. Reviewed the shipment dataset and its structure.
2. Checked data quality, including missing values, duplicate shipment IDs, and date consistency.
3. Prepared and transformed fields for analysis.
4. Created calculated indicators for delivery performance, lead time, and cost.
5. Designed KPI views and report pages.
6. Analyzed supplier, category, and transportation patterns.

Only tools and steps actually used in the final project should be considered part of the completed workflow.

---

## 5. Data Model & KPIs

The project uses shipment-level records and calculated measures to summarize procurement and delivery performance.

**Main KPIs**
- Total Spend
- Total Quantity
- On-Time Delivery (OTD)
- Late Shipments
- Late Spend
- Average Transit Days
- Average Order-to-Delivery Lead Time

**Calculated fields**
- Order-to-Ship Days
- Transit Days
- Total Lead Time
- Cost per Unit
- On-Time Flag
- Late Flag
- Late Spend

See the project documentation:
- [Data Model](documentation/Data_Model.md)
- [DAX Measures](documentation/dax_measures.md)
- [Methodology](documentation/Methodology.md)

---

## 6. Data Quality & Limitations

The dataset contains 1,000 shipment records covering January 2024 through December 2025. The initial quality review found no missing source values, no duplicate shipment IDs, and no negative date intervals.

**Important limitations**

The available data does not include:
- Promised delivery dates.
- Ordered versus received quantities.
- Inventory balances.
- Demand forecasts.
- Safety stock or reorder points.
- Historical purchase prices.
- Separately identified freight costs.

Therefore, this project does not calculate true OTIF, fill rate, inventory turns, stockout rate, forecast accuracy, purchase-price variance, or realized savings.

Late spend represents the procurement cost associated with late shipments. It is not a measure of financial loss or savings.

---

## 7. How to Explore the Project

1. Review the dashboard preview in the `screenshots` folder.
2. Explore the Power BI report in the `powerbi` folder, if the PBIX file is available.
3. Read the detailed findings and methodology in the `documentation` folder.
4. Review the KPI definitions and data model to understand how the analysis was built.

---

## 8. About the Author

**Dionner Hernandez**  
Computer Science Engineer | Business Operations | Procurement | Supply Chain Analytics

Business operations professional with 12+ years of hands-on experience managing B2B industrial services, procurement, supplier relationships, inventory, logistics, pricing, and cost analysis.

Currently developing data analytics capabilities with Excel, SQL, and Power BI to support business performance monitoring and data-driven decision-making.

**Areas of interest**
- Business Operations & Business Analysis
- Procurement & Supplier Performance
- Supply Chain Analytics
- Cost & Pricing Analysis
- Process Improvement

---
