# E-Commerce Sales Analysis

# Project Overview
This Project aims to provide actionable insights that will help improve sales ,customer retention,and operational efficiency over the past season.By analyzing the various aspect of the sales data,we seek uncover trends,analyze historical data and make data driven recommendations for strategic improvements.
# Tools
**Power Bi**-Data Cleaning using Power Query & Creating Reports
# Objectives
This repository serves as a comprehensive documentation resource to analyze sales ,trends,customer retention & loyalty,Geographical performance,delivery and sales relationship and Customer Segmentation.
# Data Cleaning & Preparation 
- Step 1: Load data into Power BI Desktop ,dataset is an excel file
- Step 2: Open power query & in view tab under Data Preview section,check "column distribution","column quality" & "column profile" options.
- Step 3: I noticed inconsistencies in the product category names, where “Furniture” was sometimes labeled as “Furniture(s).” To ensure uniformity, I standardized the category by replacing all instances of “Furniture” with “Furniture(s).” Similarly, “Tech” was renamed to “Technology” for consistency and clarity.
- Step 4: The data type for Order_Item_Discount, Sales_Per_Order, and Profit_Per_Order was changed to a fixed decimal number to ensure accuracy in calculations.
- Step 5: A Calendar Table was created using DAX for time intelligence analysis, and additional fields such as Month, MonthNum, Season, and Year were extracted for enhanced time-based reporting.
- Step 6: A relationship was established between the Calendar Table and the Fact Table to enable accurate and consistent reporting.
- Step 7: Visual filters (slicers) were added to the report for the fields Customer Region, Customer Segment, and Product Category, allowing for interactive filtering of data.
- Step 8: Five card visuals were added to the canvas to display key performance indicators (KPIs), including Total Sales, Quantity, Profit, Profit Margin, and Retention Rate.
- Step 9: Two bar charts were included in the report design:
1. The first chart represents Delivery Status by Shipping Type.
2. The second chart displays Customer Region by Total Sales, with Delivery Status added to the legend axis for better segmentation.
- Step 10: A line chart was created to visualize Sales by Month and Sales by Season, providing insights into sales trends over time.
- Step 11: A matrix visual was added to identify which customer segment shows the most interest in specific product categories, offering a detailed breakdown of customer preferences.
for creating new column following DAX expression was written;
Calendar
= CALENDAR(min(ecommerce_cleaned_data[order_date]),max(ecommerce_cleaned_data[order_date]))
year
 = year('Calendar'[Date])
Month
= format('Calendar'[Date],"mmmm")
Season
= switch(true(),[Monthnum] IN {12,1,2},"Winter",
                        [Monthnum] IN {3,4,5}, "Spring",
                        [Monthnum] IN {6,7,8}, "Summer",
                        [Monthnum] IN {9,10,11}, "Fall",
                        blank())
  Monthnum = month('Calendar'[Date])
**Snap of new calculated column**
  
  


  # Type of Analysis used
**Exploratory Data Analysis**
 It involved exploring data to discover trends and answer key question such as Total Sales,what Product Categories are Top Seller and overall Sales Trends.
 # Modelling Data
 A logical drag model defining relationship between Fact Table with Calendar Table to ensure accurate reporting 



