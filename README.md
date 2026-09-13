# fashion_nova_returns
👗 Fashion Nova Sales & Returns Analytics Pipeline
📌 Project Overview
This end-to-end data analytics project evaluates e-commerce sales performance, financial profitability, and customer return patterns for a Fashion Nova dataset (~500 orders). The primary objective is to clean ambiguous raw transactional data, isolate the root causes of revenue leakage (e.g., sizing discrepancies), and deliver interactive visual insights to optimize inventory and product sizing strategies.

🛠️ Data Pipeline & Architecture
[Raw Excel Dataset] 
       │
       ▼
[SQL Server Management Studio (SSMS)]
   ├── Schema Mapping (`CREATE VIEW`)
   ├── Deduplication (`ROW_NUMBER()`)
   └── Data Cleaning (`REPLACE`, `TRY_CAST`)
       │
       ▼
[Power BI Dashboard]
   ├── Relational Data Modeling
   ├── DAX Measures (Gross/Net Sales, Profit)
   └── Interactive Executive Dashboards
🧹 Data Transformations & Engineering (SQL)
Schema Restoration: Handled default imported column headers (Column1, Column2, etc.) by constructing structured database views (vw_fashion_nova_orders, vw_fashion_nova_returns) to maintain clean reference aliases.

Data Deduplication: Applied ROW_NUMBER() OVER (PARTITION BY ... ORDER BY ...) partitioning windows across order and return logs to eliminate duplicate transactional records.

Currency Sanitization & Casting: Stripped string artifacts (e.g., $, whitespace) using REPLACE() and safely converted string values to DECIMAL(10,2) using TRY_CAST() to enable mathematical aggregations (SUM, AVG).

Relational Joins: Executed LEFT JOIN operations across products, orders, and returns on key identifiers (product_id and order_id).

📊 Key Business & Financial Insights
Overall Revenue Performance:

Gross Sales: $26,809.65 (500 orders)

Total Refunded Amount: $4,434.07 (88 refunded items)

Net Sales: $22,375.58

Net Profit: $11,651.72 (estimating COGS at ~40%)

Primary Drivers of Returns:

Sizing Issues: Fit discrepancies ("Too Small" and "Too Big") serve as the single largest contributor to customer returns, accounting for over $4,500+ in lost revenue.

Product Expectations: "Item Not As Pictured" ($1,645.56) and "Changed Mind" ($1,624.13) form the second largest tier of return causes.

Category Highlights:

Top Net Revenue: Swimwear generated the highest net sales ($4,182.07) with a low average return item price ($49.81).

Highest Refund Risk: Denim ($945.52 refunded) and Dresses ($870.32 refunded) experienced the greatest financial return leakage.

High Ticket Return Item: Shoes logged the highest average price point per returned unit ($79.46).

📈 Power BI Visualization Features
Return Reason Breakdown: Visualized the volume and financial weight of returns grouped by underlying customer feedback.

Category Profitability Matrix: Comparative bar and matrix views tracking Gross Sales, Net Sales, Refunds, and Net Profit across apparel categories.

DAX Metrics: Custom DAX measures developed for Net Revenue, Refund Percentages, and Average Unit Value.

📂 Repository Structure
Plaintext
├── Data/
│   └── Fashion_Nova_Returns_500_Rows_With_Duplicates.xlsx
├── SQL/
│   ├── 01_schema_views_and_cleaning.sql
│   └── 02_financial_aggregations.sql
├── PowerBI/
│   └── Fashion_Nova_Returns_Dashboard.pbix
├── Visu<img width="976" height="490" alt="Screenshot 2026-09-13 132708" src="https://github.com/user-attachments/assets/672be709-44cb-44c0-bb83-11939db4f617" />
<img width="1015" height="529" alt="Screenshot 2026-09-13 131654" src="https://github.com/user-attachments/assets/61449171-b602-4ed1-b11b-0aa8553c7f1a" />
<img width="923" height="563" alt="Screenshot 2026-09-13 131204" src="https://github.com/user-attachments/assets/aadc936b-387f-41ca-a58b-500a38c6713a" />
