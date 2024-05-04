---
title: "Personal Finance Dashboard"
description: "What's the most straightforward way of achieving financial independence? Of course it's knowing how much you spend and save!"
dateString: May 2024
draft: false
tags: ["Python", "Pandas", "PowerBI"]
showToc: false
weight: 201
cover:
    image: "projects/personal-finance-dashboard/cover.jpg"
--- 
### 🔗 [Github](https://github.com/BryanNGYH/Personal-Finance-Dashboard)


# Personal Finance Dashboard
Money management is one of the most important and reliable skills. Aside from Technology, I am also interested in Finance. Hence, I built a dashboard to track my income, expenses, and savings!

## Tools and Resources
Power BI\
Python Version: 3.11\
Packages: Pandas, Numpy\
Dataset: Own dataset downloaded from [Money Manager](https://play.google.com/store/apps/details?id=com.realbyteapps.moneymanagerfree&hl=en&gl=US)

## Data Transformation
Before importing the data, I did some **Pre-Processing** on the dataset so that it could be handled better on Power BI. Here are the steps I took:-
- Removed unused columns
- Performed **feature engineering** to extract the month and quarter information from the date
- Used aggregate function to calculate the sum of income/expenses in a given month 
- Manually manipulated 1 data entry as there was a mistake in the categorization
- Created a pivot table to visualize my income/expenses based on category
 
 ![dashboard](/projects/personal-finance-dashboard/Dashboard.png)
 
## Measure Creation & Visualizations
After cleaning the data in the previous steps, the remaining steps were rather straightforward.

The KPIs for my finance dashboard are as follows:-
- Total Income (¥)
- Total Expense & Expense Breakdown (¥)
- Total Income & Income Breakdown (¥)
- Expense and Savings Percentage (%)
- Detailed Statement

To visualize these KPIs, I transformed the data types of the columns and also created a few measures. Some of them were:- 
- Total Expense
- Total Income  
- Total Savings 
- Target Savings %
- Income Last Month
- Cumulative Net Worth

The main visuals I used were *cards, slicer, matrix, clustered bar chart, line chart, and line & clustered column chart*. By using the **slicer** visuals on time (Year, Quarter, Month), users have more options on the granularity of how they want to visualize the data with respect to the dates. I also adjusted the gradient on the bar charts so that the amount of money for income and expense can be easily visualized.

Furthermore, I created tooltips that appear when the mouse hovers over some of the visuals. In that way, I can visualize how my income/expense of certain categories changes over time.
![tooltip](/projects/personal-finance-dashboard/tooltip.png)

## Conclusion
I was able to visualize my finances very clearly and interactively by using PowerBI. This is one of the most interesting projects I have done and I highly recommend anyone to try building their personal finance dashboard too.
