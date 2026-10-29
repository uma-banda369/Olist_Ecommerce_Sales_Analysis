# Olist E-commerce Sales Analysis | Power BI

# Project Overview

This project analyzes the Brazilian Olist e-commerce dataset using Power
BI to explore sales performance, order activity, payment methods,
geographic performance, delivery time, and customer review scores.

The goal is to turn raw e-commerce data into a clear business dashboard
that helps stakeholders monitor performance and identify areas for
further investigation.

# Business Questions

1.Weekday vs Weekend(order_purchase_timestamp) Payment Statistics.
2.No.of orders with a review score of 5 and payment type as a credit card.
3.Average no.of days taken for order_delivered_customer_date for pet_shop
4.Average price and payment values from customers of Sao Paulo City.
5.Relationship between shipping days(order_delivered_customer_date-order_purchase_timestamp) vs review scores.
-   How do sales and order volumes change over time?
-   Which states and cities contribute the most to sales?
-   Which payment methods are used most frequently?
-   How do delivery times vary across orders or product categories?
-   What does the customer review-score distribution look like?
-   Are longer delivery times associated with lower review scores?

# Tools and Skills

-   **Excel** --- To understand data, raw data inspection
-   **Power BI Desktop** --- dashboard development and reporting
-   **Power Query** --- ETL, data cleaning and transformation, custom column creation
-   **DAX** --- measures and KPI calculations
-   **Data modeling** --- relationships across orders, order items,
    customers, products, payments, sellers, and reviews
-   **Business analysis** --- KPI selection, trend analysis, and insight
    communication

# Dataset

The project uses the public Olist Brazilian e-commerce dataset. The data
is distributed across multiple related tables, which can include orders,
order items, customers, products, sellers, payments, reviews, and
geolocation.

Dataset source: [Brazilian E-Commerce Public Dataset by Olist on
Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

# Data Preparation and Modeling

1. Imported the relevant CSV files into Power BI.
2. Checked data types, missing values, duplicates, and key fields.
3. Reviewed order statuses and decided how cancelled or unavailable orders should be
treated.
4. Built relationships between the relevant tables and checked
relationship cardinality.
5. Created measures, custom columns at the appropriate level of detail to avoid double-counting orders or sales.
6. Validated totals and filters against the underlying data.

# KPIs

The dashboard currently includes or is being developed around the
following measures:

  -----------------------------------------------------------------------
  KPI                                 Definition / validation note
  ----------------------------------- -----------------------------------
  Total Sales                         Sum of item prices, if using
                                      `order_items[price]`; state clearly
                                      whether freight is excluded.

  Total Orders                        Distinct count of `order_id`.
                                      Document whether cancelled orders
                                      are included.

  Unique Customers                    Distinct count of
                                      `customer_unique_id`.

  Total Sellers                       Distinct count of `seller_id`.

  Average Order Value                 Total sales divided by distinct
                                      orders, using a consistent
                                      order-status and sales definition.

  Average Delivery Days               Average of actual delivery duration
                                      for eligible delivered orders.

  Average Review Score                Average of available review scores;
                                      document how missing reviews are
                                      handled.

  On-Time Delivery Rate               Orders delivered on or before the
                                      estimated delivery date divided by
                                      eligible delivered orders.

  Profit / Profit Margin              Do not report as actual profit
                                      unless valid cost data and a
                                      documented profit definition are
                                      available. The standard Olist
                                      dataset does not provide product
                                      cost.
  -----------------------------------------------------------------------

## Dashboard Pages and Visuals
<img width="1318" height="727" alt="Screenshot 2026-10-28 123240" src="https://github.com/user-attachments/assets/8f945081-6d3b-43cd-9c44-20be5019a005" />

### Executive Overview

-   KPI cards for sales, orders, customers, and sellers
-   Monthly sales trend
-   State-wise sales
-   Payment method analysis

### Product and Sales Analysis

-   Sales by product category
-   Top-performing states and cities
-   Average order value and order trends

### Delivery and Customer Experience

-   Average delivery days
-   On-time delivery rate
-   Review-score distribution
-   Delivery time versus review-score analysis

## Key Findings

1.  **Sales trend:** \[State the period and direction of the trend,
    supported by a value or comparison.\]
2.  **Geographic performance:** \[Name the top state/city and its share
    or sales value.\]
3.  **Payment behavior:** \[Identify the most-used payment method and
    its share of eligible orders or payment value.\]
4.  **Delivery performance:** \[Report average delivery duration or
    on-time delivery rate and the comparison used.\]
5.  **Customer experience:** \[Report review-score distribution and, if
    tested, the relationship between delivery time and reviews.\]

### Insight-to-Action Examples

Use these only if the data supports them: - If sales are concentrated in
a small number of states, investigate regional concentration and
opportunities in underperforming markets. - If a payment method
dominates, ensure the checkout experience for that method is reliable
while monitoring alternative methods. - If certain regions have longer
delivery times, investigate carrier, seller, distance, and
estimated-delivery factors before recommending operational changes. - If
low review scores are more common among late deliveries, investigate the
association further; do not claim that delays cause low scores without
stronger evidence.

## Limitations

-   Observed relationships are not necessarily causal.
-   Review scores are available only for orders with review records.
-   Delivery analysis should use an appropriate population of delivered
    orders and handle missing dates consistently.
-   Sales can mean item price alone or item price plus freight; the
    chosen definition should be stated.
-   The standard public dataset does not contain product cost, so actual
    profit and profit margin require additional cost data.
-   Results depend on the filters, time period, order statuses, and
    table relationships used in the report.

## How to Use

1.  Download or obtain the dataset from the source above.
2.  Open the `.pbix` file in Power BI Desktop.
3.  Refresh the data after setting the appropriate file paths.
4.  Use the report slicers to explore year, state, product category, or
    other available dimensions.

## Repository Structure

olist-ecommerce-sales-analysis/
├── README.md
├── Olist_Sales_Analysis.pbix
└── images/
    └── olist-dashboard.png

## What I Learned

-   Building a Power BI report from multiple related CSV tables
-   Creating and validating business KPIs with DAX
-   Designing interactive dashboards and slicers
-   Checking aggregation and relationship issues
-   Translating dashboard results into evidence-based business
    recommendations

## Author

**Uma Banda**
Data Analyst | Power BI | SQL | Excel
LinkedIn: https://www.linkedin.com/in/umabanda369/
