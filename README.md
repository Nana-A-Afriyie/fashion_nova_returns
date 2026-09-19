***👗 Fashion Nova Sales & Returns Analytics Pipeline***


<img width="967" height="490" alt="Screenshot 2026-09-19 152012" src="https://github.com/user-attachments/assets/7f49a7a2-dffb-4f29-88e2-e858bafc9373" />
<img width="948" height="468" alt="Screenshot 2026-09-19 152038" src="https://github.com/user-attachments/assets/de70dedd-724b-4887-afb4-a8e2676c46f1" />
<img width="931" height="483" alt="Screenshot 2026-09-19 152104" src="https://github.com/user-attachments/assets/9bff65d3-57fa-41f6-858a-cfa769529052" />
<img width="981" height="460" alt="Screenshot 2026-09-19 152146" src="https://github.com/user-attachments/assets/699bdb8f-d0d4-4098-ba34-591ad068c6e6" />
<img width="975" height="292" alt="Screenshot 2026-09-19 152222" src="https://github.com/user-attachments/assets/edc42507-484c-4e64-ad30-6c00b80d8d02" />
📌 Project Overview
This end-to-end data analytics project evaluates e-commerce sales performance, financial profitability, and customer return patterns for a Fashion Nova dataset (~500 orders). The primary objective is to clean ambiguous raw transactional data, isolate the root causes of revenue leakage (e.g., sizing discrepancies), and deliver interactive visual insights to optimize inventory and product sizing strategies.

🛠️ Data Pipeline & Architecture
Raw Excel Dataset
[JOINED_FN_ORDER_FN_FN_RETURNS.csv](https://github.com/user-attachments/files/32422153/JOINED_FN_ORDER_FN_FN_RETURNS.csv)
SQL Server Management Studio
   Deduplication (`ROW_NUMBER()`)
    Data Cleaning (`REPLACE`, `TRY_CAST`)

[Power BI Dashboard]
Relational Data Modeling
 DAX Measures (Gross/Net Sales, Profit)
Interactive Executive Dashboards
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
 Data/
Fashion_Nova_Returns_500_Rows_With_Duplicates.xlsx
SQL/ 01_schema_views_and_cleaning.sql
 02_financial_aggregations.sql
PowerBI/
 Fashion_Nova_Returns_Dashboard.pbix
Visuals/
 dashboard_preview.png[Fashion_nova_products_cleaned.csv](https://github.com/user-attachments/files/32422143/Fashion_nova_products_cleaned.csv)
[Fashion_nova_products_cleaned.csv](https://github.com/user-attachments/files/32422141/Fashion_nova_products_cleaned.csv)
[Fashion_nova_orders_cleaned.csv](https://github.com/user-attachments/files/32422133/Fashion_nova_orders_cleaned.csv)
[fashion nova products.csv](https://github.com/user-attachments/files/32422037/fashion.nova.products.csv)
[Fashion nova orders.csv](https://github.com/user-attachments/files/32422030/Fashion.nova.orders.csv)
[fashion nova returns.csv](https://github.com/user-attachments/files/32422028/fashion.nova.returns.csv)

