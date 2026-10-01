# Data Model

## Fact Table
FactShipments is the central shipment-level table.
Its intended grain is one row per Shipment ID.

## Dimensions
- DimDate: calendar attributes for time analysis.
- DimSupplier: supplier attributes.
- DimProduct: product category attributes.
- DimTransportation: shipping mode and carrier attributes.

## Relationships
Dimension tables filter the shipment fact table through their
corresponding keys. The model is intended to support analysis
by date, supplier, product category, shipping mode, and carrier.

## Validation
Review the PBIX model view for the exact relationships,
cardinality, and filter direction used in the final report.