
# Adventure Works Sales Analysis and Dashboard

## 1. *Project Overview*
This project focuses on analyzing and visualizing sales data from the Adventure Works dataset. By leveraging ETL (Extract, Transform, Load) techniques in Power Query and creating an interactive dashboard in Power BI, the project aims to provide insights into sales performance, targets, product categories, and geographical sales distribution.
## 2. *Tools & Technologies Used*
- Power Query: For data extraction, transformation, and loading (ETL).
- Power BI: For creating an interactive dashboard and visualizing key sales metrics.

## 3. *Key Data Tables*
- **Sales:** Contains information on individual sales transactions.
- **Order Date:** Stores order dates for trend analysis.
- **Customer:** Provides customer demographics for segmentation.
- **Product:** Lists products, enabling performance analysis by product.
- **Sales Territory:** Details geographic sales regions for regional analysis.

## 4. *Project Objectives*
#### 4.1 ETL Using Power Query
- Perform data extraction and transformation using Power Query.
####  4.2 Create a Power BI dashboard with key metrics, including:
- *Total Sales*
- *Sales Targets*
- *Sales Performance over time*
- *Sales by Continent*
- *Margin % by Product Category*

## 5. *Dashboard*
### **--Dashboard (Overview)**
![Dashboard Overview](https://github.com/Nazmul92/power-BI/raw/main/AW-overview.png)

### **--Dashboard (Product Sales Details)**
![Dashboard Overview](https://github.com/Nazmul92/power-BI/raw/main/AW-product-sales-details.png)

### **--Dashboard (DAX Demos)**
![Dashboard Overview](https://github.com/Nazmul92/power-BI/raw/main/AW-DAX-demos.png)

### **--Dashboard (Sales Teritory)**
![Dashboard Overview](https://github.com/Nazmul92/power-BI/raw/main/AW-sales-teritory.png)
## 6. *ETL Process in Power Query*
#### 6.1 Data Extraction: 
- Imported relevant tables from the Adventure Works dataset.
#### 6.2 Data Transformation:
- Cleaned data by removing null values and unnecessary columns.
- Merged tables to form a cohesive dataset for analysis.
- Created calculated columns for metrics like margin and sales targets.
#### 6.3 Data Loading: 
- Loaded the transformed data into Power BI for visualization.
## *7. Dashboard Design in Power BI*
#### 7.1 Overview Page
- A main page displaying total sales, sales targets, and performance metrics.
#### 7.2 Visualizations
- **KPI Card:** Shows total sales and target metrics.
- **Line Chart:** Visualizes sales performance over time.
- **Bar Chart:** Displays margin percentage by product category, highlighting high-margin products.
- **Geographic Chart:** Shows total sales by continent for regional insights.
- **Filters:** Added slicers for "Continent" and "Year" to enable dynamic filtering.

## 8. *Project Insight*
- **Total Sales:** Assessed against targets to measure goal completion.
- **Sales by Region:** Displays contributions of each continent to total sales.
- **Product Margins:** Identifies high-margin products for strategic focus.
---

## 9. *Project Structure*

```plaintext
├── data
│   ├── sales.csv
│   ├── customer.csv
│   ├── product.csv
│   ├── order_date.csv
│   └── territory.csv
├── power_bi_dashboard
│   ├── adventure_works_dashboard.pbix
├── images
│   ├── total_sales_overview.png
│   ├── sales_by_continent.png
│   ├── margin_by_category.png
└── README.md

```
## 10. DAX 
### 10.1 Basic Measure
#### **Total Sales:**
```plaintext
Total Sales = SUM(Sales[SalesAmount])
```
#### **Sales Quantity:**
```plaintext
Total Quantity = SUM(Sales[OrderQuantity])
```
#### **Total Cost:**
```plaintext
Total Cost = SUM(Sales[TotalProductCost])
```
#### **Sales Margin:**
```plaintext
Total Profit = [Total Sales] - [Total Cost]
```
#### **Margin (%):**
```plaintext
Margin % = DIVIDE([Sales Margin], [Total Sales], 0)
```
### 10.2 Time Intelligence Measures
#### **Sales YTD (Year-to-Date):**
```plaintext
Sales YTD = TOTALYTD([Total Sales], 'Date'[Date])
```
#### **Sales MTD (Month-to-Date):**
```plaintext
Sales MTD = TOTALMTD([Total Sales], 'Date'[Date])
```
#### **Sales Last Year:**
```plaintext
Sales Last Year = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
```
#### **Sales Growth YOY (Year-over-Year):**
```plaintext
Sales Growth YOY = DIVIDE([Total Sales] - [Sales Last Year], [Sales Last Year], 0)
```
### 10.3 Sales by Category and Region
#### **Sales by Product Category:**
```plaintext
Sales by Category = CALCULATE([Total Sales], ALL(Product[Category]))
```
#### **Sales by Continent:**
```plaintext
Sales by Continent = CALCULATE([Total Sales], ALL(SalesTerritory[Continent]))
```
#### **Sales Last Year:**
```plaintext
Sales Last Year = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
```
#### **Sales Growth YOY (Year-over-Year):**
```plaintext
Sales Growth YOY = DIVIDE([Total Sales] - [Sales Last Year], [Sales Last Year], 0)
```

## 11. **Insights and Results**
- **Total Sales:** The dashboard allows for easy monitoring of total sales against targets.
- **Sales by Continent:** Provides insights into which regions are leading in sales.
- **Margin Analysis:** Displays product categories with the highest margins, aiding strategic planning.
