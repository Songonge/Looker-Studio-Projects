# Project: Employee Analysis Report
***

## Table of Content
1. [Introduction](#introduction)
2. [Project Description](#project-description)
3. [About the Dataset](#About-the-dataset)
4. [Data Visualization in Looker Studio](#Data-Visualization-in-Looker-Studio)
5. [Uncovering Insights](#Uncovering-Insights)
6. [KPIs](#kpis)
7. [Conclusion](#conclusion)

## Introduction
This project focuses on analyzing employee data from different countries and providing insights regarding leadership roles, years of experience, industries, and leadership positions.

## Project Description
In this project, the following were addressed:  
1. Providing KPIs from the analysis
2. Creating Visuals to uncover insights from the data.
3. Building a dashboard to showcase everything in one place.

## About the Dataset
The dataset was created in **ChatGPT**. I wrote a prompt and asked **ChatGPT** to provide a table with the specific details I mentioned. The columns in the table are described as follows:  
* _Employee ID_: Unique identifier for each employee  
* _Employee Name_: Employee's name
* _Leadership Role_: Various leadership roles
* _Industry_: The industry the employee worked in
* _Start Date_: The date when the employee started the leadership role
* _End Date_: Date when the employee ended the leadership role
* _Gender_: Male or Female
* _Age_: Employee's age
* _Years in Role_: Number of years the employee held the leadership position before changing roles
* _Years of Experience_: Total years of professional experience
* _Previous Role_: The previous role held by the employee before promotion
* _New Role_: The new leadership role the employee transitioned into
* _Reason for Promotion/Transfer_: The reason for the role change
* _Country_: The country where the employee works
* _State_: State/region of the employee's workplace
* _Degree_: Highest academic qualification

## Data Visualization in Looker Studio
In Looker Studio, Several visuals were created.  
1. Cards for KPIs
2. Donut charts For the Number of males and females, Employee degrees, Reasons for transfer, and Number of countries
3. Bar charts for The total years of experience by country and the number of industries by country
4. Heat map for the total years of experience by leadership position
5. Combo chart for total years of experience and total years in the role by year
6. Slicers to filter data on each visual

The figure below shows the dashboard.

<figure>
  <img src="https://github.com/Songonge/Looker-Studio-Projects/blob/main/Employee_Analysis_Dashboard.png" width=100% height=100% alt="alt text">
  <figcaption>Figure: Employee Analysis Dashboard</figcaption>
</figure>
<br/><br/>

Here is the link to the [Interactive Dashboard](https://lookerstudio.google.com/reporting/c54e569e-1831-43e9-88af-fc572804fe6c). You can play around with the dashboard.


## Uncovering Insights
Analyzing the data provided the following insights:  
1. India is the top country with the maximum years of experience followed by the USA and Germany
2. The USA is the country with more industries followed by Germany and India
3. The CFO leadership position is the one with the maximum years of experience.
4. The majority of employees hold an MSc degree while fewer hold a BSc
5. The factor "Restructuring" was the major reason for employees to transfer to another role while the factor "family reasons" was the least one.

## KPIs
1. Number of employees: 108
2. Average age of employee: 43
3. Number of distinct countries analyzed: 7
4. Number of distinct states: 10


## Conclusion
This project provided a comprehensive analysis of the employee data using **Looker Studio**. By leveraging data cleaning, analysis, and visualization techniques, key insights about leadership roles, years of experience, reasons for transfer from one role to another, and the number of industries by country were uncovered. 


<br/>
   
**Thank you for taking the time to read this report!**

**Please reach out for any updates.**

### Author
[Edwige Songong](https://github.com/Songonge)
