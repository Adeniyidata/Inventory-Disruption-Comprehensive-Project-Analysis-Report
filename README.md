Inventory-Disruption-Comprehensive-Project-Analysis-Report
Project Title: Inventory Disruption Analysis Dashboard– Power Query & Excel Project
Client: Inventory Manager
 Tools, Technologies& Techniques Used:
•	Excel, Power Query ETL – Data cleaning (Extraction, transformation, and Loading) .
•	DAX (Excel) – Custom customs & measures.
•	Excel– Data visualization

Project Overview
 This project investigates patterns of inventory instability—specifically manual adjustments              
 and stockouts—to support inventory managers in optimizing operations, improving stock           
 control and enhancing supplier reliability. I conducted using Power Query and Excel Pivot       
  Tables, it transforms raw supply chain datasets into actionable insights.
      
  Problem Statement
  “We suspect that some products are frequently going out of stock or being adjusted             
   manually, but we don’t know which ones or why.”
 Business Goal
 We need to identify which products are frequently going out of stock or adjusted   
manually, and understand why, to improve inventory planning.

Project Objectives
1.	Analyze inventory logs
2.	Spot patterns in stockouts and manual adjustments
3.	Highlight the products most affected
   Therefore, the analysis focused on deriving insights from key performance indicators (KPIs), including:
  	
o	Total Adjustments Manual
o	Total Stockouts
o	Most Disrupted Category
o	Most Disrupted Supplier

Key Measures:
o	Top 5 products by manual Adjustment
o	Top 5 products by stockouts
o	Stockouts share by supplier Name
o	Inventory Disruption by Category
o	Inventory Manual Adjustment by supplier Name

  Datasets Used
•	inventory_logs.csv – Time-stamped inventory change records
•	products.csv – Product metadata including category, brand, and stock quantity
•	suppliers.csv – Supplier info per product
•	product_reviews.csv – Customer reviews with ratings and feedback
•	Meta Data Dictionary .pdf

Steps Taken:
1.	Loaded all the datasets by connecting each one 
•	Connecting every dataset and loading them directly to Power Query Edition
   2.   Data Cleaning Process: I used Excel, Power Query ETL – Data cleaning ( Extraction,   transformation, and Loading)
Using Excel Power Query, Generally, I
✅ Removed nulls and corrected inconsistent values
✅ Parsed date formats and standardized columns
✅ Cleaned strings like “units” from numeric fields
✅ Handled mixed-type columns like verified_purchase and review_date
✅ Removed irrelevant columns to optimize model performance
✅ Replaced missing values with placeholder values where necessary like missing date, none
✅ Changed some formats to lowercase, capitalization and proper case.

3. Dataset Integration:
I merged the cleaned tables based on product_id to enrich the context:
•	Added product_name, category, brand_name, and supplier_name
•	Joined review sentiment and ratings where needed
•	Ensured relationships were clean and ready for analysis

4.	Created Custom Columns for Insight:
   I created flag columns to track:
•	is_manual_adjustment: if change_type = "manual_adjustment" → 1
•	is_stockout: if stock_after_change = 0 → 1
5. Using Power Query’s Group By function, I calculated:
•	manual_adjustments_count   and stockout_count
Per product, giving a clear disruption score
6.	Group By: Summarize disruptions per product_id
7.	Merging Tables: Products + Inventory Logs + Supplier Info
8.	Exploratory Data Analysis (EDA):
•	Pivot Tables & Visuals: Analysed Insights by Category, Supplier, and Product etc
•	Conditional Formatting: Visual cueing of most disrupted areas

9.	Key Insights:
•	Some SKUs consistently showed manual adjustments, especially those linked to specific suppliers
•	Products in Office Supplies experienced the highest disruptions
•	 A few suppliers dominated like Washington Thomas & Sons and Anderson-Wagner Group had excessive manual adjustments both stockouts and adjustments, indicating potential upstream issues
•	Some products had both high adjustments and poor review ratings — showing both operational and customer dissatisfaction

10.	Patterns in Stockouts and Manual Adjustments:
•	 Li Evans Yarn Skein and Nelson Doll Score 210 also appeared in both top 5 manual adjustments and stockouts, indicating repeated disruptions in stock handling or forecasting.
•	SKUs experience frequent stockouts (e.g., Anderson-Wagner Organizer, Li Evans Yarn Skeim, Nelson Doll score 210), suggesting they are either understocked or over-demanded. These disruptions may indicate poor demand forecasting or inadequate reorder levels.
•	Suppliers like Anderson-Wagner Group (22%) and Washington Thomas & Sons (37%) account for the largest share of manual inventory corrections.
This implies potential supply chain inconsistencies or data entry errors tied to specific vendors.


11.	Recommendations:
•	Implement minimum stock thresholds with alerts for high-risk products
•	Audit and retrain warehouse staff on stock entry SOPs
•	Improve supplier accountability and performance tracking
•	Create inventory buffers for high-disruption categories
•	Use visual dashboards to track disruptions over time and act proactively
•	Set minimum stock thresholds for disrupted products
•	Audit Top 5 SKUs for stock inaccuracies

12.	 Conclusion
This project showcases how everyday tools like Excel can deliver inventory intelligence when combined with structured data transformation techniques.
It also helped the inventory team spot recurring issues but also laid the groundwork for smarter planning and supplier management.

