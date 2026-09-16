<img width="1210" height="473" alt="Screenshot 2026-09-13 190908" src="https://github.com/user-attachments/assets/cbe4c448-f40f-4d5c-a5<img width="965" height="538" alt="Screenshot 2026-09-16 151653" src="https://github.com/user-attachments/assets/0ebe28dc-98ca-4027-a0f9-7ff8b92e44f7" />
<img width="950" height="529" alt="Screenshot 2026-09-16 151730" src="https://github.com/user-attachments/assets/eecc943a-3153-4708-8b39-61bf4f149e00" />
<img width="940" height="548" alt="Screenshot 2026-09-16 151812" src="https://github.com/user-attachments/assets/5ed3b12e-3c27-4d80-a7a0-2b130c663bd7" />
<img width="925" height="305" alt="Screenshot 2026-09-16 152013" src="https://github.com/user-attachments/assets/56aba8ba-231c-42e4-9840-326afeb707ca" />

[Fashion_nova_products_cleaned.csv](https://github.com/user-attachments/files/32173693/Fashion_nova_products_cleaned.csv)
[fashion_nova_returns_cleaned.csv](https://github.com/user-attachments/files/32173690/fashion_nova_returns_cleaned.csv)
[Fashion_nova_orders_cleaned.csv](https://github.com/user-attachments/files/32173658/Fashion_nova_orders_cleaned.csv)



***👗 Fashion Nova Sales & Returns Analytics Pipeline***


***📌 Project Overview***
This end-to-end data analytics project evaluates e-commerce sales performance, financial profitability, and customer return patterns for a Fashion Nova dataset (~500 orders). The primary objective is to clean ambiguous raw transactional data, isolate the root causes of revenue leakage (e.g., sizing discrepancies), and deliver interactive visual insights to optimize inventory and product sizing strategies.

***🛠️ Data Pipeline & Architecture ***
[Raw Excel Dataset] 
       │
       ▼
[SQL Server Management Studio (SSMS)]
    Schema Mapping (`CREATE VIEW`)
   Deduplication (`ROW_NUMBER()`)
    Data Cleaning (`REPLACE`, `TRY_CAST`)
       │
       ▼
[Power BI Dashboard]
    Relational Data Modeling
    DAX Measures (Gross/Net Sales, Profit)
   Interactive Executive Dashboards
🧹 Data Transformations & Engineering (SQL)
Schema Restoration: Handled default imported column headers (Column1, Column2, etc.) by constructing structured database views (vw_fashion_nova_orders, vw_fashion_nova_returns) to maintain clean reference aliases.

Data Deduplication: Applied ROW_NUMBER() OVER (PARTITION BY ... ORDER BY ...) partitioning windows across order and return logs to eliminate duplicate transactional records.

Currency Sanitization & Casting: Stripped string artifacts (e.g., $, whitespace) using REPLACE() and safely converted string values to DECIMAL(10,2) using TRY_CAST() to enable mathematical aggregations (SUM, AVG).

Relational Joins: Executed LEFT JOIN operations across products, orders, and returns on key identifiers (product_id and order_id).

***📊 Key Business & Financial Insights***
Overall Revenue Performance:

Gross Sales: $34,481.83 (500 orders)

Total Refunded 5,288.14 (88 refunded items)

Net Sales: $29,193.69

Top category swimwear $6950.28

Primary Drivers of Returns:

Sizing Issues: Fit discrepancies ("Too Small" and "Too Big") serve as the single largest contributor to customer returns, accounting for over $5288+ in lost revenue.

Product Expectations: "too small" ($2936.23) and "not as pictured" ($1,645.56) form the second largest tier of return causes.

Category Highlights:

Top Net Revenue: Swimwear generated the highest net sales ($6950.28) with a low average return item price ($49.81).

Highest Refund Risk: Denim ($945.52 refunded) and Dresses ($870.32 refunded) experienced the greatest financial return leakage.

High Ticket Return Item: Shoes logged the highest average price point per returned unit ($79.46).

***📈 Power BI Visualization Features**
Return Reason Breakdown: Visualized the volume and financial weight of returns grouped by underlying customer feedback.

Category Profitability Matrix: Comparative bar and matrix views tracking Gross Sales, Net Sales, Refunds, and Net Profit across apparel categories.This chart compares sales generation against refund impact across our key product categories:

Primary Revenue Driver: Swimwear leads overall category performance with $6.95k in Gross Sales and over $6.16k in Net Sales.

Highest Financial Leakage: Denim ($945.52) and Dresses ($870.32) represent our largest dollar losses due to returns.

High-Ticket Return Risk: Shoes carries our highest average return item price ($79.46), making sizing accuracy in footwear critical to protecting margins.

Recommendation: Focus sizing guidance and fit optimizations primarily on Denim and Dresses to protect high-margin net sales."

***📂 Repository Structure**
Plaintext
Data/
 Fashion_Nova_Returns_500_Rows_With_Duplicates
 SQL/
 01_schema_views_and_cleaning.sql
 02_financial_aggregations.sql
 PowerBI/
Fashion_Nova_Returns_Dashboard.pbi
