# 🛒 Blinkit Business Analytics Dashboard (Power BI)

## Project Overview :

This project focuses on analyzing business performance for **Blinkit** using Power BI.

The dataset contains sales, product, and outlet-related information. The data had missing values, inconsistent labels, and required proper structuring before analysis. Using Power Query and DAX, the raw data was cleaned, transformed, and converted into meaningful business insights.

The final output is a single-page interactive dashboard designed to help management understand sales trends, product performance, and operational efficiency.

## Tools & Technologies Used :

* **Microsoft Power BI Desktop**
* Power Query (Data Cleaning & Transformation)
* DAX (Business Measures & KPIs)
* Excel / CSV Dataset

## Data Cleaning & Transformation (Power Query):

The following data preparation steps were performed:

* Corrected data types (Sales, Rating → Decimal | Weight → Numeric)
* Standardized fat content values (LF, low fat → Low Fat | reg → Regular)
* Handled missing values in Item Weight, Sales, and Fat Content
* Removed duplicate records based on Item Identifier + Outlet
* Cleaned and formatted categorical fields

### Created business logic columns:

* Sales per Kg = Sales ÷ Item Weight
* Years of Operation = Current Year – Outlet Establishment Year

## Data Modeling :

* Built a **Star Schema** for better performance and clarity

### Tables Created:

* Fact Table → Sales Data

* Dimension Tables → Items, Outlet, Fat Content

* Established relationships (Many-to-One) between dimension tables and fact table


## DAX Measures Created :

The following dynamic measures were implemented:

* Total Sales = SUM('Data'[Sales])
* Avg Sales per Outlet = Total Sales / DISTINCTCOUNT(Outlet Identifier)
* Avg Rating = AVERAGE('Data'[Rating])
* Sales per Kg = SUM(Sales) / SUM(Item Weight)
* Total Outlets = DISTINCTCOUNT(Outlet Identifier)
* Avg Years of Operation = AVERAGE(Years of Operation)
* Rank Items = RANKX(ALL(Item Identifier), Total Sales, , DESC)

These measures allow dynamic filtering and real-time updates across visuals.


## Dashboard Features :

The dashboard includes:

* KPI Cards (Total Sales, Avg Sales per Outlet, Rating, Sales per Kg)
* Sales by Item Category (Bar Chart)
* Sales by Fat Content (Donut Chart)
* Sales by Outlet Type and Tier (Column Chart)
* Top 10 Items by Sales
* Visibility vs Sales Analysis (Scatter Plot)

### Interactive Features:

* Slicers for:

  * Tier
  * Outlet Type
  * Item Category
  * Fat Content

## Key Insights :

* Tier 1 outlets generate higher sales compared to others
* Low Fat products perform better in multiple categories
* Some products have high visibility but low sales (underperforming items)
* Certain outlet types contribute more to overall revenue

## Recommendations :

* Improve placement and promotion of underperforming products
* Focus on high-performing outlet types for expansion
* Optimize product visibility strategies
* Improve product labeling clarity for better customer understanding

## Final Outcome :

 - This project demonstrates how raw business data can be transformed into meaningful insights using Power BI.
 - It highlights skills in data cleaning, data modeling, DAX, and dashboard design, while also focusing on solving real-world business problems.
