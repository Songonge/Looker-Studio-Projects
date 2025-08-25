# Case Study: Sales vs. Cost Analysis for a Small Tech Company
***

## Overview
This case study presents an end-to-end analysis of sales and cost data for a small tech company. The goal was to identify performance trends, evaluate profitability, and recommend actionable strategies for sustainable growth. The analysis was visualized in an interactive dashboard built with **Looker Studio**.

## Problem Statement
While sales have been increasing, the company suspected that profit margins were shrinking. Management needed a data-driven view of sales, costs, and discounts across different regions, product categories, and customer segments to:  
*	Understand revenue drivers.
* Identify profit leakages.
* Optimize pricing and discount strategies.

## Project Objectives
* Analyze Sales, Cost, Profit, Profit Margin, Quantity Sold, and Average Discount.
* Compare Year-over-Year (YoY) performance.
* Identify top-performing and underperforming States, Cities, Sub-Categories, Segments, and Regions.
* Detect seasonal trends and monthly performance variations.
* Provide actionable business recommendations.

## Data & Tools
Data Source:
* The data was generated using **ChatGPT**. Below is the prompt used.
| Figure: Prompt Used to Get the Data |
| :------------: |
```
Please create a downloadable csv file that I am going to clean, analyze, and build a dashboard and answer business questions.
Here is what I want to clean from the data:
1. Removing duplicates
2. Handling missing data
3. Using text functions to fix inconsistent data
4. Fix errors in some entries

The data should have 500 rows and the following columns: Order ID, Order Date, First Name, Last Name, Customer ID, Customer Segment, Country, City,	State, Postal Code, Region, Product ID,	Category, Sub-Category,	Product Name, Quantity, Cost, Sales, and Discount.
```

The file downloaded contained:  
* `510 rows` in total and `20 columns`.
* Transactions dataset 2023 to 2025.
* Fields included: Order ID, Order Date, First Name, Last Name, Customer ID, Customer Segment, Country, City,	State, Postal Code, Region, Product ID,	Category, Sub-Category,	Product Name, Quantity, Cost, Sales, and Discount.

Tools Used:
* **Excel**: Data cleaning & preparation.
* **Looker Studio**: visualization  Dashboard creation  

## Data Cleaning
The data cleaning tasks were completed in **Excel** and consisted of:  
1. Checking and removing duplicates using the "Remove Duplicates" feature: 10 duplicate rows were deleted.
2. Checking and filling empty cells in the City, Postal Code, and Profit columns. 
   * The empty cells in the City and Postal Code columns were replaced with "Unknown" since there was not much information to give appropriate values. 
   * For the Profit column, I filled empty by calculating `Sales - Cost`.
3. Fixing the text for inconsistent formatting and changing the data type where necessary.
4. Removing the Country column since it was only displaying the United States.
5. Creating a column for Full Name, Month, Year, Month No (to sort the Month column by Month No). 

## Data Analysis
Calculated Fields:
```sql
Profit = Sales – Cost
```
Calculated Metrics:
```sql
Total Sales = SUM(Sales)
```
```sql
Total Costs = SUM(Cost)
```
```sql
Total Profit = SUM(Profit)
```
```sql
Total Quantity = SUM(Sales)
```
```sql
Profit Margin (%) = (Profit / Sales) × 100
```
```dax
Average Discount = AVERAGE(Discount)
```

## Data Visualization and Dashboard Design

<!---
5. Analysis & Findings
Overall Performance (Jan–Jun 2024)
Metric	Value	YoY Change	Key Insight
Sales	189.3K	+21.8%	Strong revenue growth.
Cost	173.3K	+22.9%	Costs rising slightly faster than sales.
Profit	16.0K	+10.8%	Positive but slower growth than sales.
Quantity Sold	1,432	+17.7%	Higher volume driving sales.
Profit Margin	8.44%	-9.0%	Margins shrinking due to higher costs/discounts.
Avg. Discount	14.96%	+4.5%	Discounting strategy may be eroding profitability.

Top 3 States by Sales
1.	Maryland – 16K sales, 14.3K cost
2.	Alaska – 15.8K sales, 14.2K cost
3.	Arizona – 14.8K sales, 13.8K cost
Observation: Margins are narrow across states.

Top Sub-Categories
•	High Sales: Binders (53.7K), Tables (46.3K), Labels (45.8K).
•	Lower Margins: Phones, Accessories — small gap between sales and costs.

By Segment
•	Corporate (53.2K) and Small Business (51K) drive the largest share of sales.
•	Home Office is smallest but potentially scalable with targeted offers.

Regional Trends
•	South region leads (51.3K), followed by East (49.7K).
•	West region lags behind.

Seasonality
•	Peak months: Feb (21.3K), Apr (21.3K).
•	Low months: Jun (9.1K), Oct (8.4K).
•	Suggests opportunity to run targeted campaigns in low months.

6. Key Insights
1.	Sales growth is strong, but costs and discounts are eroding margins.
2.	Aggressive discounting may not be sustainable long-term.
3.	Low-margin product categories need cost control or price adjustments.
4.	Certain regions and cities are underperforming despite market potential.
5.	Seasonal patterns can be leveraged for targeted promotions.

7. Recommendations
1.	Revise Discount Policies
o	Reduce blanket discounts; introduce loyalty or referral programs.
2.	Optimize Costs
o	Negotiate supplier contracts for high-cost items.
3.	Expand into Underperforming Regions
o	Target West region with location-specific marketing.
4.	Product Portfolio Strategy
o	Focus on high-margin categories (Binders, Tables).
5.	Seasonal Sales Strategy
o	Boost promotions in slow months (June, October) to smooth revenue.

8. How to Reproduce This Project
If you want to recreate this project and dashboard:
Step 1 — Prepare Your Dataset
Create a CSV file with the following columns:
mathematica
CopyEdit
Order Date, State, City, Region, Segment, Sub-Category, Sales, Cost, Discount, Quantity
Populate with sample or real transactional data for at least one year.
Step 2 — Clean and Prepare Data
•	Convert Order Date to a proper date format.
•	Ensure Sales and Cost are numeric values.
•	Remove duplicates and handle missing values.
Step 3 — Upload to Google Sheets
•	Import your cleaned dataset into Google Sheets for easy integration with Looker Studio.
Step 4 — Build Dashboard in Looker Studio
•	Connect your Google Sheet to Looker Studio.
•	Create Scorecards for Sales, Cost, Profit, Quantity, Profit Margin, and Avg. Discount.
•	Add Bar Charts for:
o	Top States
o	Top Cities
o	Top Sub-Categories
o	Segment and Region analysis
•	Add a Time Series Chart for monthly sales trends.
•	Use YoY comparison in scorecards to show % change from the previous year.
Step 5 — Style Your Dashboard
•	Use distinct colors for Sales and Cost (e.g., teal for sales, gold for cost).
•	Apply clear labels and tooltips for better readability.

9. Conclusion
The analysis shows the company is in a growth phase but must address margin pressure.
By fine-tuning its discount and pricing strategy, optimizing costs, and focusing on underperforming regions, the company can maintain revenue growth while improving profitability.
-->





