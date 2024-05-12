# E-commerce Sales Power BI Project

## Overview
This project utilizes Power BI to analyze and visualize year-to-date (YTD) sales data for an E-commerce business. It provides insights into sales performance, quantity sold, profit margins, and more. The analysis is presented through various metrics and visualizations to aid decision-making and identify areas for improvement.

## Steps in the Project
1. **Problem Statement**
2. **Import Data in MS SQL Server**
3. **Connecting Power BI to MS SQL DB**
4. **Data Cleaning**
5. **Data Processing**
6. **Data Modelling**
7. **Creating a Date Table**
8. **Data Visualization**
9. **Creating Dashboards**
10. **Generating Insights**

### Problem Statement
1. Create a KPI showing:
   - YTD(Sales)
   - YTD(Profit)
   - YTD(Quantity sold)
   - YTD(Profit Margin)
2. Find Year on year-on-year growth for each KPI and show a YTD sparkline for each measure in the KPI to understand the monthly trend for each fact.
3. Find YTD Sales, PYTD Sales, and YoY Sales growth for different customer categories. Add a trend icon for each category.
4. Find YTD Sales Performance by Each State.
5. Top 5 and Bottom 5 Products by Sales.
6. YTD Sales by Region to know the best and worst performing regions all over the country.
7. YTD Sales by Shipping Type to get the best shipping type percentage.

## Insights
By analyzing YTD sales, we can pinpoint which regions or states contribute the most to overall revenue. Understanding customer segments allows for tailored marketing campaigns to boost sales. Identifying top and bottom products helps in inventory management and product strategy.

### Some of the DAX Formulas used in this Project:
1. **YTD Sales** = TOTALYTD(SUM(ecommerce_data[sales_per_order]),Calender[Date])
2. **PYTD Sales** = CALCULATE(SUM(ecommerce_data[sales_per_order]), DATESYTD(SAMEPERIODLASTYEAR(Calender[Date])))
3. **YOY Sales** = ([YTD Sales]-[PYTD Sales])/[PYTD Sales]
   - Year-on-Year Growth = (Current year Growth – Previous  Year sales)/Previous Year Sales
4. **Sales Icon** = 
    ```DAX
    var positive_icon = UNICHAR(9650)
    var negative_icon = UNICHAR(9660)
    var result = IF([YOY Sales]>0,positive_icon,negative_icon)
    return result
    ```

## How to Use
1. Clone or download the project repository.
2. Open the Power BI file using Power BI Desktop.
3. Connect the data source to your E-commerce sales database.
4. Refresh data to ensure you have the latest information.
5. Explore different tabs and visualizations to gain insights into your sales performance.

## Technologies Used
- Power BI: Used for data visualization and analysis.
- SQL: Possibly used for data extraction and preparation.
- GitHub: Version control and project hosting.


