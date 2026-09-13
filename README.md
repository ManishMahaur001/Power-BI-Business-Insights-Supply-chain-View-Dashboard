# Supply-chain-View-Dashboard

Overview

The Supply Chain View dashboard tracks forecast accuracy and error metrics across customers and product segments to support inventory and demand-planning decisions.

Filters & Slicers

Located at the top of the page:

Region, Market — dropdown (default: All)
Customer — dropdown (default: All)
Segment, Category — dropdown (default: All)
Year selector — 2019, 2020, 2021 (selected), 2022…
Quarter selector — Q1, Q2, Q3, Q4
Period toggle — YTD / YTG (Year-to-Date / Year-to-Go)
Key KPI Cards
Metric	Current	Last Year (LY)	YoY Change
Forecast Accuracy %	80.21%	72.99%	+9.88%
Net Error	-0.75M	0.49M	+252.91%
ABS Error	9.78M	5.74M	-70.3%
Visuals
Accuracy / Net Error Trend

Combo chart (bar + line) spanning Sep 2020 – Aug 2021, showing:

Net Error (bar, primary axis, in millions)
Forecast Accuracy % (line, secondary axis)
Forecast Accuracy % LY (line, secondary axis, for year-over-year comparison)
Key Metrics by Customers (table)

Row-level detail by customer (e.g., Amazon, BestBuy, Costco, Circuit City, etc.) with columns:

Forecast Accuracy %
Forecast Accuracy % LY
Net Error
Net Error %
Risk flag — "Out Of Stock" or "Excess Inventory"
Key Metrics by Products (table)

Same metric structure, broken down by product segment (Storage, Networking, Desktop, Notebook, Peripherals, Accessories), each expandable for further detail.

Data Model (fields panel)

Key tables/fields feeding this report:

dim_market, dim_product, dim_customer, dim_date
fact_forecast_monthly — core forecast/actuals fact table
freight_cost, manufacturing_cost, post_invoice_deduction..., Operational Expance
Fact_Actuals_Estimates
P&L Column, P&L Rows
fiscal_year, Last sales month
Key Mesures (measures folder — likely houses DAX calculations for Forecast Accuracy %, Net Error, ABS Error, etc.)
Purpose / How to Use

This view is intended for supply chain and demand planning teams to:

Monitor forecast accuracy and error trends over time at an aggregate and granular (customer/product) level.
Identify at-risk accounts or segments — flagged as "Out of Stock" (under-forecasted/short supply) or "Excess Inventory" (over-forecasted/oversupply).
Compare current performance against prior year (LY) to track improvement or degradation in forecasting accuracy.
Drill down by region, customer, or product segment/category using the top filters, and by year/quarter/YTD-YTG for time-based analysis.
Notes for Maintainers
"Risk" classification appears to be derived from the sign/magnitude of Net Error % (positive → Excess Inventory, negative → Out of Stock) — confirm exact threshold logic in the underlying DAX measure.
The "Add data fields here" placeholder in the Values pane suggests the currently selected visual has an incomplete/unbound field — worth checking before publishing.
Report is built for Power BI Desktop and uses Copilot/Sensitivity labeling features (visible in ribbon), so confirm sensitivity classification before external sharing.
