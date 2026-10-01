# Methodology & Data Quality

## Data Preparation
The source shipment data was prepared for analysis in Power Query.
Date and numeric fields were reviewed, and derived duration and
cost-per-unit fields were created where applicable.

## Data Quality Checks
Initial validation covered:
- Missing values in source columns
- Duplicate Shipment IDs
- Date interval consistency
- Data types and field interpretation

## KPI Rules
OTD is based on the source On-Time Delivery field.
Transit Days = Delivery Date - Ship Date.
Total Lead Time Days = Delivery Date - Order Date.
Cost per Unit = Total Cost / Quantity.

## Limitations
The dataset does not include promised delivery dates,
ordered-versus-received quantities, inventory balances,
demand forecasts, or separate freight costs.
See the README for the full list of analytical limitations.