Avg Order to Ship Days = AVERAGE(FactShipments[Order to Ship Days])

Avg Total Lead Time = 
    AVERAGE(FactShipments[Total Lead Time Days])

Avg Transit Days = 
    AVERAGE(FactShipments[Transit Days])

Cost Per Unit = 
    DIVIDE(
        [Total Spend],
        [Total Quantity]
    )

Late Shipments = 
CALCULATE(
    [Shipments],
    FactShipments[On Time Flag] = 0
)

Late Spend = 
SUM(FactShipments[Late Spend])

Late Spend % = 
    DIVIDE(
        [Late Spend],
        [Total Spend]
    )

Media Total Lead Time Days = 
    MEDIAN(FactShipments[Total Lead Time Days])

Media Transit Days = 
    MEDIAN(FactShipments[Transit Days])

On Time Shipments = 
CALCULATE(
    [Shipments],
    FactShipments[On Time Flag]
)


OTD% = 
DIVIDE(
    [On Time Shipments],
    [Shipments]
)


P90 Transit Days = 
PERCENTILEX.INC(
    VALUES(FactShipments[Shipment ID]),
    CALCULATE(MAX(FactShipments[Transit Days])),
    0.90
)


Priority Exceptions = 
CALCULATE(
    DISTINCTCOUNT(
        DimSupplier[Supplier Name]
    ),
    FILTER(
        VALUES(DimSupplier[Supplier Name]),
        [Supplier Exception] = "Priority Exception"
    )
)


Shipments = DISTINCTCOUNT(FactShipments[Shipment ID])



Supplier Cumulative Spend % = 
VAR CurrentSpend =
    [Total Spend]

VAR SupplierTable =
    ADDCOLUMNS(
        ALLSELECTED(DimSupplier[Supplier Name]),
        "@Spend", [Total Spend]
    )

VAR CumulativeSpend =
    SUMX(
        FILTER(
            SupplierTable,
            [@Spend] >= CurrentSpend
        ),
        [@Spend]
    )

RETURN
DIVIDE(
    CumulativeSpend,
    CALCULATE(
        [Total Spend],
        ALLSELECTED(DimSupplier[Supplier Name])
    )
)


Supplier Exception = 
VAR OTD = [OTD%]
VAR Spend = [Total Spend]
VAR P90 = [P90 Transit Days]

RETURN
SWITCH(
    TRUE(),
    OTD < 0.75 && Spend > 500000 && P90 > 20,
        "Priority Exception",

    OTD < 0.80 || P90 > 20,
        "Watch",

    "Normal"
)


Supplier Spend % = 
DIVIDE(
    [Total Spend],
    CALCULATE(
        [Total Spend],
        ALLSELECTED(DimSupplier[Supplier Name])
    )
)



Titulo Categoria = 
VAR Seleccion = SELECTEDVALUE(DimProduct[Product Category], "All Categories")
RETURN
"Category: " & Seleccion


Titulo Supplier = 
VAR Seleccion = SELECTEDVALUE(DimSupplier[Supplier Name], "All Suppliers")
RETURN
"Supplier: " & Seleccion


Total Quantity = sum(FactShipments[Quantity])


Total Spend = SUM(FactShipments[Total Cost])


Watch Exceptions = 
CALCULATE(
    DISTINCTCOUNT(
        DimSupplier[Supplier Name]
    ),
    FILTER(
        VALUES(DimSupplier[Supplier Name]),
        [Supplier Exception] = "Watch"
    )
)


Metric Selectors = {
    ("Total Spend", NAMEOF('_Measures'[Total Spend]), 0),
    ("OTD%", NAMEOF('_Measures'[OTD%]), 1),
    ("Late Spend", NAMEOF('_Measures'[Late Spend]), 2),
    ("Avg Transit Days", NAMEOF('_Measures'[Avg Transit Days]), 3),
    ("Total Quantity", NAMEOF('_Measures'[Total Quantity]), 4)
}