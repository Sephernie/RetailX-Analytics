# RetailX Analytics
# Data Requirements

---

# Purpose

This document defines the data required to answer the business questions and calculate the KPIs identified during the planning phase.

The requirements outlined here will guide dataset selection, database design, and future SQL development.

---

# Data Sources

The project requires transactional retail data containing information about:

- Customers
- Orders
- Products
- Product Categories
- Order Items

---

# Customer Data

## Purpose

Customer information is required for customer analytics, segmentation, repeat purchase analysis, and customer lifetime value calculations.

### Required Fields

| Field | Description |
|---------|-------------|
| CustomerID | Unique customer identifier |
| FirstName | Customer first name |
| LastName | Customer last name |
| Gender | Customer gender |
| Age | Customer age |
| City | Customer city |
| State | Customer state or province |
| Country | Customer country |
| PostalCode | Postal code |
| SignupDate | Customer registration date |

### Used For

- Customer segmentation
- Geographic analysis
- Customer lifetime value
- Repeat purchase analysis

---

# Product Data

## Purpose

Product information is required to evaluate product and category performance.

### Required Fields

| Field | Description |
|---------|-------------|
| ProductID | Unique product identifier |
| ProductName | Product name |
| CategoryID | Product category |
| Brand | Brand name |
| UnitCost | Product cost |
| UnitPrice | Selling price |

### Used For

- Revenue analysis
- Profit calculation
- Product performance
- Category analysis

---

# Category Data

## Purpose

Organizes products into logical business categories.

### Required Fields

| Field | Description |
|---------|-------------|
| CategoryID | Unique category identifier |
| CategoryName | Category name |

### Used For

- Category revenue
- Category profitability
- Dashboard filters

---

# Order Data

## Purpose

Represents customer purchases.

### Required Fields

| Field | Description |
|---------|-------------|
| OrderID | Unique order identifier |
| CustomerID | Customer placing the order |
| OrderDate | Date order was placed |
| ShipDate | Shipping date |
| ShipMode | Shipping method |
| OrderStatus | Completed, Cancelled, Returned |
| PaymentMethod | Payment type |

### Used For

- Sales trends
- Order volume
- Shipping analysis
- Time series analysis

---

# Order Item Data

## Purpose

Stores the individual products within each order.

### Required Fields

| Field | Description |
|---------|-------------|
| OrderItemID | Unique order line |
| OrderID | Parent order |
| ProductID | Purchased product |
| Quantity | Units sold |
| UnitPrice | Selling price |
| Discount | Discount applied |

### Used For

- Revenue
- Profit
- Product sales
- Basket analysis

---

# Relationships

The following relationships are required:

Customers
│
└── Orders
│
└── OrderItems
│
└── Products
│
└── Categories

---

# Required Calculated Fields

The following values may not exist directly in the dataset and will need to be calculated.

| Field | Formula |
|--------|---------|
| Revenue | Quantity × UnitPrice |
| Profit | Revenue − Cost |
| Profit Margin | Profit ÷ Revenue |
| Average Order Value | Revenue ÷ Orders |
| Customer Lifetime Value | Revenue per Customer |
| Monthly Revenue | Sum of Revenue by Month |

---

# Data Quality Requirements

The dataset should satisfy the following conditions:

- Unique primary keys
- Minimal missing values
- Consistent date formats
- Numeric sales values
- No duplicate orders
- Valid relationships between tables
- Consistent product identifiers

---

# Dataset Evaluation Criteria

When selecting a dataset in Phase 3, preference will be given to datasets that include:

✓ Customer information

✓ Product information

✓ Categories

✓ Order history

✓ Dates

✓ Geographic information

✓ Pricing information

✓ Product costs (preferred)

✓ Discounts

✓ Shipping information

---

# Summary

The selected dataset must provide sufficient information to:

- Answer all business questions
- Calculate all defined KPIs
- Build a normalized SQL database
- Perform SQL analysis
- Support Python EDA
- Build Power BI dashboards
- Enable future machine learning models