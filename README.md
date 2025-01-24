# E-Commerce Sales Analysis

# Project Overview
This Project aims to provide actionable insights that will help improve sales ,customer retention,and operational efficiency over the past season.By analyzing the various aspect of the sales data,we seek uncover trends,analyze historical data and make data driven recommendations for strategic improvements.
# Tools
**Power Bi**-Data Cleaning using Power Query & Creating Reports
# Objectives
This repository serves as a comprehensive documentation resource to analyze sales ,trends,customer retention & loyalty,Geographical performance,delivery and sales relationship and Customer Segmentation.
 # Type of Analysis used
**Exploratory Data Analysis**
 It involved exploring data to discover trends and answer key question such as Total Sales,what Product Categories are Top Seller and overall Sales Trends.
# Data Cleaning & Preparation 
- Step 1: Load data into Power BI Desktop ,dataset is an excel file
- Step 2: Open power query & in view tab under Data Preview section,check "column distribution","column quality" & "column profile" options.
- Step 3: I noticed inconsistencies in the product category names, where “Furniture” was sometimes labeled as “Furniture(s).” To ensure uniformity, I standardized the category by replacing all instances of “Furniture” with “Furniture(s).” Similarly, “Tech” was renamed to “Technology” for consistency and clarity.
- Step 4: The data type for Order_Item_Discount, Sales_Per_Order, and Profit_Per_Order was changed to a fixed decimal number to ensure accuracy in calculations.
- Step 5: A Calendar Table was created using DAX for time intelligence analysis, and additional fields such as Month, MonthNum, Season, and Year were extracted for enhanced time-based reporting.
- Step 6: A relationship was established between the Calendar Table and the Fact Table to enable accurate and consistent reporting.
- Step 7: Visual filters (slicers) were added to the report for the fields Customer Region, Customer Segment, and Product Category, allowing for interactive filtering of data.
- Step 8: New Measures was created to find Total Sales,Quantity,Profit,Profit Margin,Retention Rate

  Total Sales
   = sum(ecommerce_cleaned_data[sales_per_order])

  Total Quantity
   = sum(ecommerce_cleaned_data[order_quantity])

  Total Profit
  = sum(ecommerce_cleaned_data[profit_per_order])

  Profit Margin
   = divide([Total Profit],[Total Sales],0)*100

  Retention Rate
   = divide([Returning Customers],[Total Customers],0)

  
  Five card visuals were added to the canvas to display key performance indicators (KPIs), including Total Sales, Quantity, Profit, Profit Margin, and Retention Rate.
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
  
  Monthnum 
  = month('Calendar'[Date])

**Snap of new calculated column**
  ![image](https://github.com/user-attachments/assets/32b9d541-230a-4419-b0f6-c4d1f8f51991)

  # Insights
  1. Top Product Category

   -Office Supplies is the highest-performing product category, generating the largest sales across all customer segments.  



2. Customer Retention

   - Overall, 42.83% of customers are returning buyers.  

   - The South region has the lowest sales performance and the lowest retention rate at 14.24%

   - The West region leads in sales performance and has the highest retention rate at 21.40%



3. Customer Segments Performance

   - The Consumer segment is the best-performing segment, dominating sales in office supplies with total sales of $4.6M

   - The Corporate segment also focuses heavily on office supplies, contributing $2.7M in sales.  

   - The Home Office segment has the lowest performance, generating $1.5M in sales.  



4. Regional Performance

   - The West region has the highest sales in office supplies and shows strong performance overall.  

   - Both the West and East regions experience higher sales under all shipping scenarios, including late delivery, on-time delivery, advance shipping, and canceled shipping.  



5. Shipping Insights

   Standard shipping is the most commonly used option, especially for late deliveries, advance shipping, on-time deliveries, and canceled orders.  

 # Recommendation Reports
  Boosting Retention in Low-Performing Regions Retention rates in the South region remain significantly lower compared to other regions, with a retention rate of only 14.24%. Improving customer experience in this region is critical to enhancing overall performance. Addressing factors such as late deliveries and limited product availability should be prioritized. Implementing loyalty programs or providing targeted discounts for customers in this region can encourage repeat purchases and build stronger customer relationships over time. 

Enhancing Shipping Efficiency Shipping performance plays a critical role in influencing customer satisfaction and retention. Since standard shipping is the most widely used method, efforts should be made to optimize its efficiency by minimizing late deliveries and cancellations. Furthermore, advanced and expedited shipping options should be expanded, particularly in high-performing regions such as the West and East. These regions already demonstrate strong sales performance, and improving shipping options can further increase customer satisfaction and drive higher sales. 

 Focusing on High-Performing Segments The Consumer segment is the top-performing customer segment, generating $4.6M in sales, primarily from the office supplies category. Continued focus on this segment is recommended, with tailored marketing strategies and personalized promotions to maintain strong engagement. Additionally, the Corporate segment, which contributed $2.7M in sales, should be further cultivated by promoting bulk purchase discounts and offering reliable shipping options to meet their operational needs. Strengthening these relationships can drive sustained growth and loyalty in these segments. 

 Improving the Home Office Segment The Home Office segment currently underperforms compared to other customer segments, contributing only $1.5M in sales. To enhance performance, it is important to understand the specific needs and preferences of this segment. Developing targeted campaigns such as promotions for small office setups, discounted bundles, or curated product packages tailored for home office users can drive greater engagement and sales. 

Leveraging Regional Strengths The West region leads in sales performance and retention, particularly in the office supplies category. To maintain and expand this success, it is advisable to invest in promoting high-demand office supplies while offering loyalty rewards to retain existing customers. The East region, which also shows strong shipping performance, offers opportunities for growth. Exploring targeted marketing strategies in this region can further capitalize on its potential, ensuring sustained growth and profitability.




  
  


 
  




