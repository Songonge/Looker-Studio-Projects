# Case Study: Sales vs. Cost Analysis for a Small Tech Company
***

## Table of Contents
1. [Overview](#overview)
2. [Problem Statement](#Problem-Statement)
3. [Project Objectives](#Project-Objectives)
4. [Data and Tools](#Data-and-Tools)
5. [Data Cleaning](#Data-Cleaning)
6. [Data Analysis](#Data-Analysis)
7. [Data Visualization and Dashboard Design](#Data-Visualization-and-Dashboard-Design)
   * [A. Overall KPIs](#A-Overall-KPIs)
   * [B. Sales vs. Cost Analysis](#B-Sales-vs-Cost-Analysis)
   * [C. Quantity Analysis](#C-Quantity-Analysis)
   * [D. Customer Analysis](#D-Customer-Analysis)
8. [Key Insights](#key-insights)
9. [Recommendations](#Recommendations)
10. [Why we are Confident the Recommendations will work](#Why-we-are-Confident-the-Recommendations-will-work)
11. [How to Reproduce this Project](#How-to-Reproduce-this-Project)
    * [Step 1: Prepare Your Dataset](#Step-1-Prepare-Your-Dataset)
    * [Step 2: Clean and Prepare Data](#Step-2-Clean-and-Prepare-Data)
    * [Step 3: Upload to Looker Studio](#Step-3-Upload-to-Looker-Studio)
    * [Step 4: Build the Dashboard](#Step-4-Build-the-Dashboard)
    * [Step 5: Style the Dashboard](#Step-5-Style-the-Dashboard)
12. [Conclusion](#conclusion)

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

## Data and Tools
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

The data should have 500 rows and the following columns:
Order ID, Order Date, First Name, Last Name, Customer ID, Customer Segment,
Country, City,	State, Postal Code, Region, Product ID,	Category, Sub-Category,
Product Name, Quantity, Cost, Sales, and Discount.
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
5. Creating a column for Customer Name using the `CONCAT()` function. Then, deleted the First Name and Last Name Columns
6. Created the Month, Year, and Month No columns. The Month No column was used to sort the Month column. 

The cleaned data contained `500` rows and `21` columns.

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
```sql
Average Discount = AVERAGE(Discount)
```

## Data Visualization and Dashboard Design
### A. Overall KPIs
* **Sales**: $189,3 K
* **Costs**: 173.3 K
* **Profit**: $16.0 K
* **Quantity**: 1,432
* **Profit Margin**: 8.44%
* **Average Discount**: 14.96%
* **Total Records**: 500

* **Metric	Value	YoY Change	Key Insight**  
  * Sales	+21.8%	Strong revenue growth.
  * Costs +22.9%	Costs rising slightly faster than sales.
  * Profit	+10.8%	Positive but slower growth than sales.
  * Quantity +17.7%	Higher volume driving sales.
  * Profit Margin	-9.0%	Margins, due to higher costs.
  * Avg. Discount	+4.5%	Discounting strategy may be eroding profitability.

### B. Sales vs. Cost Analysis
| Figure: Sales vs. Cost Analysis Dashboard |
| :------------: |
<figure>
  <img src="https://github.com/Songonge/Looker-Studio-Projects/blob/main/Sales-and-Cost-Analysis/Sales_Costs_Analysis.png" width=100% height=100% alt="alt text">
</figure>

* **Top 3 States**  
  * Maryland: $16K sales, $14.3K cost
  * Alaska: $15.8K sales, $14.2K cost
  * Arizona: $14.8K sales, $13.8K cost  
  * **Observation**: Margins are narrow across states.

* **Top 3 Cities**  
  * South Neil: $2.7K sales, $2.5K cost
  * Brooksland: $2.6K sales, $2.4K cost
  * North Jasmine: $2.5K sales, $2.5K cost  
  * **Observation**: Margins are narrow across cities.

* **Top Category**  
  * Furniture: $125.2K sales, $114,6K cost

* **Top Sub-Categories**  
  * High Sales
    * Binders: $53.7K sales, $48.8K cost
    * Tables: $46.3K sales, $42.5k costs
    * Labels: $45.8K sales, $41.5K cost
  * Lower Margins
    * Phones: $36.3K sales, $32K cost
    * Accessories: $33.8K sales, $30.1K cost
    * Paper: $25.1K sales, $24.9K cost

* **By Segment**  
  * Corporate: $53.2K sales, $48.8K, drives the largest share of sales.
  * Small Business $51K sales, $47K cost
  * Home Office: Smallest in sales but potentially scalable with targeted offers.

* **Regional Trends**  
  * The South region leads in sales ($51.3K), followed by the East ($49.7K).
  * The East region leads in cost ($46.3K), followed by the South ($45.7K).
  * The West region lags behind with $42.5K sales and $39K cost.

* **Seasonality according to sales**  
  * Peak months: Feb (21.3K), Apr (21.3K).
  * Low months: May (9.1K), Oct (8.4K).
  * Suggests opportunity to run targeted campaigns in low months.


### C. Quantity Analysis
| Figure: Quantity Analysis Dashboard |
| :------------: |
<figure>
  <img src="https://github.com/Songonge/Looker-Studio-Projects/blob/main/Sales-and-Cost-Analysis/Quantity_Analysis.png" width=100% height=100% alt="alt text">
</figure>

* **Top 3 States**  
  * Maryland: 114
  * Alaska: 106
  * Arizona: 97  
  * **Observation**: These are also the top three states by Sales.

* **Top 3 Cities**  
  * Johnsonland: 20
  * Brianberg: 20
  * South Neil: 18 

* **Top Category**  
  * Office Supplies: 961

* **Top Sub-Categories**  
  * High Quantity
    * Binders: 402
    * Labels: 362
    * Tables: 346

  * Lower Margins
    * Phones: 260
    * Accessories: 238
    * Paper: 209

* **By Segment**  
  * Corporate: 737, 26.7%
  * Home Office: 711, 25.8%
  * Consumer: 657, 23.8%
  * Small Business 655, 23.7%

* **Regional Trends**  
  * The East region leads in quantity (736), followed by the South (725).
  * The West region lags behind with 643 in quantity.

* **Seasonality**  
  * Peak months: September (289), followed by January (267).
  * Low months: May (191), July (186).
  * Suggests opportunity to run targeted campaigns in low months.

### D. Customer Analysis
| Figure: Customer Analysis Dashboard |
| :------------: |
<figure>
  <img src="https://github.com/Songonge/Looker-Studio-Projects/blob/main/Sales-and-Cost-Analysis/Customers_Analysis.png" width=100% height=100% alt="alt text">
</figure>

* **Top 3 Customers by Sales and Costs**  
  * Corey Walker: $2,741.48 sales, $2,493.72 cost
  * Barbara Adams: $2617.38 sales, $2,414.58 cost
  * Adam Taylor: $248.25 sales, $2,542.07 cost  

* **Top 3 Customers by Profit**  
  * Brian Gutierrez: $693.73
  * Laurie Robinson: $611.24
  * Alexandra Barnes: $591.32
  
* **Top Segment by Sales and Costs**  
  * Consumer

* **Top Segment by Profit**  
  * Corporate

  
## Key Insights
1. Sales growth is strong, but costs and discounts are eroding margins.
2. Increased discounting may not be sustainable long-term.
3. Low-margin product categories need cost control or price adjustments.
4. Certain regions and cities are underperforming despite their market potential.
5. Seasonal patterns can be leveraged for targeted promotions.
6. Higher quantity implies higher sales.
7. Higher sales do not necessarily imply higher profitability.

## Recommendations
1. Revise Discount Policies
   * Reduce discounts on some items to maximize profit
   * Introduce loyalty or referral promotions.

2. Optimize Costs
   * Negotiate supplier contracts for high-cost items.

3. Expand into Underperforming Regions
   * Target the West region with location-specific marketing.

4. Product Portfolio Strategy
   * Focus on high-margin categories (Binders, Tables).

5. Seasonal Sales Strategy
   * Boost promotions in slow months (May, October) to smooth revenue.

## Why we are Confident the Recommendations will work
We are Confident that the Above Recommendations will work for several reasons:  
1. Reducing discounts or shifting to targeted/loyalty-based promotions will likely improve margins without significantly affecting sales, as sales already grew 21.8% despite high discounts.
2. Cost optimization, through supplier negotiations or bulk purchasing, will directly reduce the cost base, which in turn will improve profit margins.
3. Targeted marketing in underperforming regions will unlock new revenue streams, leveraging existing infrastructure without major fixed cost increases.
4. Focusing marketing and inventory on high-margin products will increase overall profitability even if total sales volume remains the same.
5. Targeted promotions during slow months will smooth revenue flow, better utilize operational capacity, and reduce reliance on peak-season sales.

## How to Reproduce This Project
If you want to recreate this project and dashboard:

### Step 1: Prepare Your Dataset
* Create a CSV file. You can use the prompt as given above in the **Data & Tools** section.
* Populate with sample or real transactional data for at least one year.

### Step 2: Clean and Prepare Data
* Convert Order Date to a proper date format.
* Ensure Sales and Cost are numeric values.
* Remove duplicates and handle missing values.
* Delete or create other columns as needed.

### Step 3: Upload to Looker Studio
  * Import your cleaned dataset into Google Looker Studio. You can also import your cleaned data to Google Sheets for easy integration with Looker Studio.

### Step 4: Build the Dashboard
* In case you imported your data to Google Sheets:  
  * Connect your Google Sheet to Looker Studio.
  * Create Scorecards for Sales, Cost, Profit, Quantity, Profit Margin, and Avg. Discount.

* Add Bar Charts for:
  * Top States
  * Top Cities
  * Top Sub-Categories
  *	Segment and Region analysis

* Add a Time Series Chart for monthly sales trends.
* Use YoY comparison in scorecards to show % change from the previous year.

## Step 5: Style the Dashboard
* Use distinct colors for Sales and Cost.
* Apply clear labels and tooltips for better readability.

## Conclusion
The analysis shows the company is in a growth phase but must address margin pressure.
By fine-tuning its discount and pricing strategy, optimizing costs, and focusing on underperforming regions, the company can maintain revenue growth while improving profitability.






