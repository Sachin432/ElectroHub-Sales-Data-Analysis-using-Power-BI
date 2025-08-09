# Power BI Sales Analysis Dashboard – ElectroHub

## Project Overview

This project presents a **Power BI Dashboard** for **ElectroHub**, an e-commerce retailer, to analyze sales, profit, discounts, and product performance.
The data model follows a **star schema**, with three dimension tables and one fact table, enabling interactive analysis through slicers, filters, and drill-through capabilities.

---

## Dataset Description

The dataset consists of **4 tables**:

### 1. DimCustomer

Contains customer demographic and contact information.

| Column Name   | Data Type | Description                        |
| ------------- | --------- | ---------------------------------- |
| Customer ID   | Integer   | Unique ID for each customer.       |
| Customer Name | Text      | Full name of the customer.         |
| City          | Text      | Customer's city.                   |
| State         | Text      | Customer's state.                  |
| Pincode       | Integer   | Postal code of customer’s address. |
| EmailID       | Text      | Registered email address.          |
| Phone Number  | Integer   | Contact number.                    |

---

### 2. DimPromotion

Holds promotion and discount-related information.

| Column Name         | Data Type | Description                                  |
| ------------------- | --------- | -------------------------------------------- |
| Promotion ID        | Integer   | Unique ID for each promotion.                |
| Promotion Name      | Text      | Name/description of the promotion.           |
| Discount Category   | Text      | Discount category (e.g., Low, Medium, High). |
| Discount Percentage | Decimal   | Percentage discount applied.                 |

---

### 3. DimProduct

Contains details of products sold.

| Column Name  | Data Type | Description                                               |
| ------------ | --------- | --------------------------------------------------------- |
| Product ID   | Integer   | Unique product identifier.                                |
| Product Name | Text      | Name/description of the product.                          |
| Category     | Text      | Product category (Electronics, Footwear, Clothing, etc.). |
| Sub-Category | Text      | Sub-classification within the category.                   |
| Unit Price   | Decimal   | Selling price per unit.                                   |

---

### 4. FactSales

Stores transactional sales data and connects to all dimension tables.

| Column Name   | Data Type | Description                     |
| ------------- | --------- | ------------------------------- |
| Order ID      | Integer   | Unique order identifier.        |
| Customer ID   | Integer   | Links to DimCustomer.           |
| Product ID    | Integer   | Links to DimProduct.            |
| Promotion ID  | Integer   | Links to DimPromotion.          |
| Order Date    | Date      | Date when the order was placed. |
| Quantity Sold | Integer   | Number of units sold.           |
| Sales Amount  | Decimal   | Total sales revenue.            |
| Profit Amount | Decimal   | Total profit from the sale.     |
| Net Sales     | Decimal   | Sales after discount deduction. |

---

## Dashboard Features & Requirements

1. **Top/Bottom 5 Products**

   * By Sales, Profit, and Quantity Sold.

2. **Sales Trends Over Time**

   * Daily, Monthly, Quarterly, and Annually.

3. **Sales vs. Profit Relationship**

   * Correlation analysis.

4. **Period Comparisons**

   * Sales, Profit, Quantity Sold between two user-selected periods.

5. **Average Discount Analysis**

   * Per discount category.

6. **Total Orders**

   * Count of all orders placed.

7. **Detailed Order View**

   * Sales, Profit, Discount, Net Sales with filters (Product, Date, Customer ID, Promotion Category).

8. **Geographical Insights**

   * Sales breakdown by city.

---

## Data Model

The dashboard uses a **star schema**:

```
           DimCustomer
                |
           FactSales
          /    |     
 DimProduct DimPromotion 
```

* `FactSales` is the central table containing transactional data.
* Dimension tables hold descriptive attributes for filtering and slicing.

---

## Tools & Technologies

* **Power BI Desktop** – Visualization & dashboard creation.
* **DAX** – Calculated measures and KPIs.
* **Excel** – Source data format.
* **Data Modeling** – Star schema relationships.

---

## How to Use

1. Download the `.pbix` and dataset files.
2. Open `.pbix` in **Power BI Desktop**.
3. Ensure dataset paths are correct.
4. Use slicers and drill-through to explore.

---

## Expected Insights

* Identify best and worst-performing products.
* Spot seasonal trends in sales and profit.
* Understand impact of discounts.
* Evaluate city-wise performance.


