# DATA VISUALIZATION USING POWER BI – SALES TARGET ANALYSIS
1. Introduction
Data visualization plays an important role in converting raw business data into meaningful insights. This project was developed using Microsoft Power BI to analyze sales performance, compare actual sales with sales targets, identify regional sales patterns, and evaluate business performance through interactive dashboards and DAX calculations.
The objective of this project is to transform raw sales data into visual reports that support business decision-making through calculations, analysis, and visualization techniques.

2. Project Objective
The objectives of this project are:
Import and transform sales datasets into Power BI.
Establish relationships between multiple tables.
Create calculated columns and DAX measures.
Build interactive dashboards and visual reports.
Compare actual sales against targets.
Analyze sales performance across categories, locations, and time periods.

3. Dataset Description
Three datasets were used in this project:
List of Orders
Contains order-related information including:
Order ID
Order Date
Customer Name
State
City
Order Details
Contains transaction details:
Order ID
Category
Sub-Category
Amount
Profit
Quantity
Sales Target
Contains target values:
Category
Segment
Sales Target

4. Data Import and Preparation
Steps Performed:
Open Power BI Desktop.
Import CSV files using Get Data.
Open Power Query Editor.
Verify and correct data types.
Remove null values and unnecessary records.
Load transformed data into Power BI.

5. Data Modeling
Relationships were created between datasets to enable analysis.
Relationships:
List of Orders[Order ID] → Order Details[Order ID]
Sales Target[Category] → Order Details[Category]
Relationship Type:
One-to-Many

6. DAX Calculations
Calculated Columns
Category Type
Combines Category and Sub-Category.
DAX:
Category Type =
Category & " - " & Sub-Category

Revenue per Order
Calculates revenue for each order.
DAX:
Revenue per Order =
Amount × Quantity

Sales Category
Classifies orders based on average sales.
DAX:
Sales Category =
IF(
Amount > Average Amount,
"Above Average",
"Below Average"
)

Measures
Order Count
Calculates total number of orders.
DAX:
Order Count =
COUNT(Order ID)

Average Profit in Delhi
Calculates average profit generated in Delhi.
DAX:
Average Profit Delhi =
CALCULATE(
AVERAGE(Profit),
City="Delhi"
)

Year-to-Date Sales
Calculates cumulative sales.
DAX:
YTD Sales =
TOTALYTD(
SUM(Amount),
Order Date
)

7. Data Visualization
1. Sales Target Achievement by Category
Visual: Clustered Column Chart
Purpose:
Compare actual sales and target sales across categories.
Fields:
Axis → Category
Values → Sales Amount
Secondary Values → Target

2. Max Profit Margin by Sub-Category
Visual: Donut Chart
Purpose:
Identify sub-categories generating maximum profit.
Fields:
Legend → Sub-Category
Values → Maximum Profit

3. Monthly Sales Trend
Visual: Line Chart
Purpose:
Analyze sales growth over time.
Fields:
Axis → Month
Values → Sales

4. Comparison of Profit and Quantity
Visual: Scatter Chart
Purpose:
Study relationship between sales quantity and profit.
Fields:
X → Quantity
Y → Profit
Details → Sub-Category

5. Comparison of Total Sales and Target
Visual: Card + Multi-row Card
Purpose:
Display actual sales and targets for comparison.
Cards:
Total Sales
Total Target
Multi-row Card:
Minimum Target by Segment

6. Sales Performance Matrix
Visual: Matrix
Purpose:
Compare actual sales and target values across categories and months.
Fields:
Rows → Category
Columns → Month
Values:
Actual Sales
Target Sales
Conditional formatting was applied to highlight performance.

7. Geographic Sales Analysis
Visual: Map
Purpose:
Analyze total sales across cities.
Fields:
Location → City
Size → Total Sales

8. Sales Distribution by Sub-Category
Visual: Treemap
Purpose:
Understand contribution of each sub-category.
Fields:
Group → Sub-Category
Values → Sales

9. Order Count Analysis by State
Visual: Funnel Chart
Purpose:
Visualize order distribution across states.
Fields:
Group → State
Values → Order Count



8. Key Insights
Sales performance differs across categories.
Certain cities generated higher sales than others.
Some categories exceeded targets while others underperformed.
Monthly trends revealed seasonal sales behavior.
Funnel and map visuals helped identify regional opportunities.

10. Conclusion
This project demonstrates how Power BI can be used to transform raw business data into meaningful visual insights. Through DAX calculations, dashboard creation, and interactive reporting, the project enabled sales monitoring, target comparison, and business performance analysis effectively.
The dashboard supports decision-making by presenting data in a simple, visual, and interactive manner.

