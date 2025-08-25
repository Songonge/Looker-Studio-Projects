# Case Study: Sales vs. Cost Analysis for a Small Tech Company
***

## Overview
________________________________________
This case study presents an end-to-end analysis of sales and cost data for a small tech company.
The goal was to identify performance trends, evaluate profitability, and recommend actionable strategies for sustainable growth.
The analysis was visualized in an interactive dashboard built with Looker Studio.

1. Problem Statement
While sales have been increasing, the company suspected that profit margins were shrinking.
Management needed a data-driven view of sales, costs, and discounts across different regions, product categories, and customer segments to:
•	Understand revenue drivers.
•	Identify profit leakages.
•	Optimize pricing and discount strategies.

2. Project Objectives
•	Analyze Sales, Cost, Profit, Profit Margin, Quantity Sold, and Average Discount.
•	Compare performance Year-over-Year (YoY).
•	Identify top-performing and underperforming States, Cities, Sub-Categories, Segments, and Regions.
•	Detect seasonal trends and monthly performance variations.
•	Provide actionable business recommendations.

3. Data & Tools
Data Source:
•	Company’s sales transactions dataset (Jan–Jun 2024).
•	Fields included: Order Date, State, City, Product Sub-Category, Sales Amount, Cost Amount, Discount %, and Quantity Sold.
Tools Used:
•	Excel / Google Sheets – Data cleaning & preparation.
•	Looker Studio – Dashboard creation & visualization.
•	Calculated Fields:
o	Profit = Sales – Cost
o	Profit Margin (%) = (Profit / Sales) × 100
o	YoY % change = ((Current – Previous) / Previous) × 100

4. Dashboard Preview
(Insert image in your GitHub repo and reference it here)

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






