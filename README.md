# Retail Store Sales Performance Analysis

## Table of Content
- [Project_Overview](#project-overview)
- [Objectives](#objectives)
- [Tools_Used](#tools-used)
- [Exploratory_Data_Analysis](#exploratory-data-analysis)
- [Findings](#findings)
- [Dashboard](#dashboard)
- [Recommendations](#recommendations)
- [Conclusion](#conclusion)

---

### Project Overview
- **Order ID**: Unique identifier for each sales transaction, used to track individual orders.
- **Customer Id**: Unique ID representing each customer, for customer behavior analysis.
- **Product**: Name of the product sold (Shoes, Shirt, Hat, Gloves, Jacket, Socks).
- **Region**: Geographic region where the sale occurred (South, East, North, West).
- **Order Date**: Full date of the order (e.g., 2024-01-15), for time-based analysis.
- **Quantity**: Number of units sold per order, indicating order volume.
- **Unit_Price**: Price per unit of the product (e.g., ₦309), for pricing insights.
- **Total Sales**: Total revenue per item (Quantity × Unit_Price).
- **Month**: Month extracted from order date (e.g., January), for seasonal patterns.
- **Transaction Patterns**: Includes single and multiple product purchases.
- **Product Categories**: Six categories including Shoes, Shirt, Hat, Gloves, Jacket, Socks.

---

### Objectives
The aim is to analyze retail store sales data to identify:
- **Product Performance** - Total sales and revenue contribution by product category.
- **Regional Analysis** - Sales by transaction count and share of total sales across regions.
- **Top Products** - Highest-selling product based on total sales value.
- **Revenue Drivers** - Revenue per product and overall revenue contribution.
- **Seasonal Trends** - Monthly sales trends for the current year.
- **Customer Insights** - Top customers based on total purchase amounts.
- **Inventory Analysis** - Products with no sales in the last quarter for slow-moving items.

---

### Tools Used
The analysis tool used to evaluate and analyze the dataset is **Power BI** for interactive dashboard creation and data visualization, with **Excel** used for initial data validation and quick calculations.

**Power BI Features Used:**
- Data modeling and relationships
- DAX measures for KPI calculations
- Interactive slicers and filters
- Custom visualizations
- Drill-through capabilities
- Dynamic tooltips
- Bookmark navigation
- Report page tooltips

---

### Exploratory Data Analysis
1. **Total Sales by Product Category:**
   - Created a matrix visual in Power BI with Product as rows and Sum of Total Sales as values to identify top-performing segments.

2. **Regional Sales Analysis:**
   - Used a table visual with Region and Total Sales, adding a percentage calculation using DAX to determine market share distribution.

3. **Highest-Selling Product:**
   - Implemented a card visual with a DAX measure to dynamically display the top product by total sales value.

4. **Revenue per Product:**
   - Built a detailed matrix showing Total Revenue, Quantity, Transaction Count, and Average Unit Price per product.

5. **Monthly Sales Trends:**
   - Created a line chart with Month on the x-axis and Total Sales on y-axis, using a slicer to filter for current year.

6. **Top 5 Customers:**
   - Used a table visual with Customer ID and Total Sales, applying Top N filter to display top 5 customers.

7. **Sales Contribution by Region:**
   - Created a donut chart with Region and Total Sales, adding a DAX measure for percentage calculation.

8. **Products with No Sales in Last Quarter:**
   - Used a card visual with a DAX measure to count products with zero sales in the last 3 months.

---

### Findings
- **Total Sales by Product Category:** Shoes generated the highest sales (₦3,100,000) while socks had the lowest (₦900,000).
- **Sales Transactions by Region:** The South contributed the most to total sales (₦2,545,400; 23.14%), followed by the East, North, and West.
- **Highest-Selling Product:** Shoes had the highest total sales value at ₦3,100,000.
- **Revenue per Product:** Revenue was unevenly distributed, with shoes, shirts, and hats leading the total revenue.
- **Monthly Sales Totals:** February recorded the peak sales (₦2,750,000), while September had the lowest (₦175,000), indicating seasonal variation.
- **Top 5 Customers:** The top five customers contributed significantly, with Cus1488 leading at ₦2,800,000 (25.45% of total revenue).
- **Sales Contribution by Region (%):** The South accounted for the largest share of total sales (23.14%), while the West contributed the least (14.29%).
- **Products with No Sales in Last Quarter:** All products recorded sales in the last quarter, showing no inactive items.

---

### Dashboard

<div align="center">
  <img width="775" height="489" alt="Retail Store Dashboard" src="https://github.com/user-attachments/assets/f6ea54b2-86fc-4b4d-b664-1cf0f16d2809">
  <br>
  <em>Retail Store Sales Performance Dashboard</em>
</div>


**Power BI Dashboard Components:**

**Executive Summary Page:**
- **KPIs:** Total Sales (₦11M), Total Customers (500), Average Sales (₦212)
- **Total Sales by Product:** Bar chart showing Shoes (₦3.1M), Shirt (₦2.5M), Hat (₦1.6M), Gloves (₦1.5M), Jacket (₦1.1M), Socks (₦0.9M)
- **Sales by Region:** Donut chart with South (23.14%), East (23.14%), North (18.42%), West (14.29%)
- **Average Sales by Product:** Column chart displaying Shirt (₦327), Shoes (₦309), Gloves (₦200), Hat (₦159), Jacket (₦140), Socks (₦122)
- **Top 5 Customers:** Table showing Cus1488 (₦2.8M), Cus1375 (₦1.4M), Cus1023 (₦1.3M), Cus1059 (₦0.7M), Cus1367 (₦0.5M)

**Interactive Features:**
- **Slicers:** Region, Month, Product Category
- **Drill-through:** Click on any product to view detailed analysis
- **Tooltips:** Hover for additional metrics
- **Bookmarks:** Navigate between dashboard pages
- **Export:** Download as PDF or PowerPoint

**Power BI DAX Measures Used:**
```dax
// Total Sales
Total Sales = SUM(sales_data[Total_Sales])

// Total Customers
Total Customers = DISTINCTCOUNT(sales_data[Customer_Id])

// Average Order Value
Avg Order Value = AVERAGE(sales_data[Total_Sales])

// Sales by Region Percentage
Region % = 
DIVIDE(
    SUM(sales_data[Total_Sales]),
    CALCULATE(SUM(sales_data[Total_Sales]), ALL(sales_data[Region]))
) * 100

```                       
                          
---                       

### Recommendations

- **Product Strategy:** Expand shoes product line as the top performer with 28.18% revenue share. Bundle socks with shoes to increase sales of low-performing socks. Create seasonal bundles to leverage product combinations and increase average order value by 5-10%.

- **Regional Strategy:** Increase marketing investment in South and East regions by 10% to maintain leadership. Conduct urgent market audit in West region which underperforms by 38% compared to top regions. Implement region-specific promotions and local marketing campaigns.

- **Customer Retention:** Develop VIP program for top customer Cus1488 who contributes 25.45% of total revenue to reduce concentration risk. Launch loyalty points program for mid-tier customers to improve retention by 15%. Implement referral programs to acquire new high-value customers.

- **Pricing Optimization:** Maintain premium positioning for Shirts at ₦327. Increase Shoes price by 5% to ₦325. Raise Jacket price by 14% from ₦140 to ₦160. Offer volume discounts for Hats (buy 2 get 10% off) to increase volume by 20%.

- **Inventory Management:** Ensure efficient production and stock levels for shoes and shirts to meet high demand. Plan inventory buildup before February peak season. Implement just-in-time inventory for slow-moving items.

- **Marketing Campaigns:** Launch targeted marketing campaigns in January to sustain peak sales and revenue. Analyze factors contributing to September sales dip and develop strategies such as promotions or limited-time offers during this period.

---

### Conclusion

The retail store sales analysis offers valuable insights into product performance, regional distribution, customer behavior, and seasonal patterns. Shoes emerge as the top-performing product category with 28.18% revenue share, while the South and East regions dominate sales with 23.14% each. The top customer concentration risk (25.45% from a single customer) requires immediate attention through VIP programs and customer diversification strategies.

Key findings reveal strong February peak sales (₦2.75M) and September lows (₦175,000), highlighting the need for seasonal planning. The West region's underperformance (14.29% share) presents a growth opportunity through targeted marketing and local promotions. All products remain active with no slow-moving items, indicating healthy inventory turnover.

By implementing targeted strategies to optimize product mix, address regional imbalances, diversify customer base, and manage seasonal fluctuations, the retail store can enhance customer satisfaction, drive revenue growth by 15-20%, and achieve long-term success.

---

**Report Prepared By**: Elizabeth Ben  
**Role**: Data Analyst  
**Tools Used**: Power BI  
**Date**: December 2025  
**Data Source**: Techrative Technology Limited Retail Store Sales Database (Confidential)
