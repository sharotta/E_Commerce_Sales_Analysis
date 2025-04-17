# E_Commerce_Sales_Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [E-Commerce Sales Performance](#e-commerce-sales-performance)
- [Customer Insights](#customer-insights)
- [Product Categories Analysis](#product-categories-analysis)
- [Order Insights](#order-insights)
- [Regional Sales Analysis](#regional-sales-analysis)

## Project Overview:
In today’s competitive e-commerce landscape, understanding sales trends, customer behavior, and product performance is crucial for making data-driven decisions. 
This dataset contains missing values, inconsistent formatting, and potential errors that need to be cleaned before analysis. The goal of this project is to identify sales trends, customer insights, product performances, order fulfillment efficiencies, payment preferences, and regional analysis. 

## Data Source:
The dataset used in this analysis represents anonymized e-commerce transactions and was leveraged to uncover customer behavior and sales patterns.

## Tools:

- Microsoft Power BI — for building dashboards and visualizing insights
- Power Query — for data transformation
- DAX — for KPIs and calculated measures

## Dataset Overview:
The e-commerce dataset captures 1,050 online shop transactions, including details such as order dates, product categories, customer purchases, payment methods, and shipping regions.

## Data Cleaning & Preparation:
The following data cleaning processes were carried out for the e-commerce data set using Power Query.

1. I standardized text formatting of product category, payment method, and date to a proper format.

2. Handled Missing Values:
- Customer ID: 52 nulls replaced with **“NO ID”**
- Product Category: 52 nulls filled with the most common category, **Home Kitchen** (221 occurrences). 
- Product Name: 52 nulls mapped using **category context** (e.g., Home Kitchen — Unspecified)
- Payment Method: 51 nulls replaced with **“Not Provided”** due to close frequency between top methods (**PayPal:** 256, **Bank Transfer:** 254)
- Shipping Region: 54 nulls filled with **“Unknown Region”**
- Order Status: 48 nulls dynamically filled using **M language** — if payment, shipping, and date exist, status set to **“Completed,”** else **“Pending**.
3. Removed Duplicates:
- Order ID: Identified 50 duplicate orders with identical details, safely removed.
- Customer ID: 92 duplicates found; further investigated inconsistencies to ensure valid grouping.
4. Carefully checked each column and their data types to ensure accuracy.
5. Measures created:
- Average Order Value
  ![Average Order Value](https://github.com/user-attachments/assets/90106620-344b-4668-9f7c-d5c163495af9)
- Average Price
  ![Avg Price](https://github.com/user-attachments/assets/d95c5759-bb41-4852-83f0-a6184f602998)
- Customer Churn Rate
  ![Customer Churn Rate](https://github.com/user-attachments/assets/d1ad22e6-86ad-4892-8a5e-1a885878ee6a)
- Customer Total Spend
  ![Customer Total Spend](https://github.com/user-attachments/assets/5dd99f74-7398-47aa-b3f8-93809425a471)
- Order fulfillment rate
  ![Order Fulfillment Rate](https://github.com/user-attachments/assets/8999984d-962d-41a7-857d-f13d1071e889)
- Total Quantity
  ![Quantity Sold](https://github.com/user-attachments/assets/6e31ca09-83b4-4561-a373-4b6c5323dd19)
- Total Sales
  ![Total Sales](https://github.com/user-attachments/assets/45e5ad1d-6cc1-457b-9ecd-731e882f9db1)

6. Calculated columns created:
- Customer Revenue Segment
  ![Customer Revenue Segment](https://github.com/user-attachments/assets/e9273edf-a887-471e-b941-f9ba16810cfb)
- Returning Customer Status
7. Customer Segmentation- Customers were segmented into **high-value**, **medium-value**, and **low-value** groups based on their total revenue contribution. A custom measure was created to calculate **customer total spend**, followed by a calculated column to categorize customers using the following thresholds:
- **High-Value**: Spent above $3,000
- **Medium-Value**: Spent between $1,500 and $3,000
- **Low-Value**: Spent less than $1,500

## **Data Analysis & Visualization**
To ensure clarity and ease of interpretation, the analysis was structured into four key dashboard pages: **Customer Insights**, **Product Categories**, **Order Insights**, and **Regional Insights**. Additionally, a **drillthrough feature** was implemented to allow deeper exploration of specific customer and order details.

## **E-Commerce Sales Performance**
![Overview Dashboard](https://github.com/user-attachments/assets/fe6ddf42-34ad-4aba-b612-b52de35d037a)

Key Findings:

1. Customer Behavior: Only **9.8%** of customers are returning, indicating low retention. 
- **High-value customers (192)** represent significant **revenue potential**.
2. Revenue Trends: Sales peaked at **$137,607**, which was in **March**, and were the **lowest $101,992** in **Novembe**r, showing strong seasonal patterns.
- Europe has the highest revenue contribution **($281,386)**, while Africa and the unknown regions trail.
3. Product Performance: The Home-Kitchen product category leads with a total revenue of **$333,867**, while Clothing underperforms **($192,488)** despite high order volume.

## **Customer Insights**

**Focus:** Customer Segmentation | Revenue Analysis | Churn Rate| Regional Trends
![Customer Dashboard](https://github.com/user-attachments/assets/4334e35a-a9ff-4ddf-88eb-b2bdc3a4c153)

**Key Insights**

1. High Customer Churn Rate
- Out of **902** total customers, only **98 (9.8%)** are returning customers, indicating successful acquisition.
- This results in a very high churn rate of **94.46%**, indicating low customer retention and low brand loyalty.
2. Customer Value Distribution
- The majority of customers fall into the **low-value segment (62%) — 559 customers**.
- Only **192** customers **(21%)** are in the ***high-value category***, suggesting a smaller group drives significant revenue. This is an opportunity for targeted loyalty and upsell campaigns.
3. Regional & Payment Insights
Frequent purchases come from all regions, but **Africa, Asia, and Europe dominate high purchase counts***.
**Credit card** is the preferred payment method, especially among high spenders, indicating it’s crucial to maintain seamless card processing.
4. Repeat Purchases Drive Revenue
Top customers made **9–10 purchase**s, each generating **~$4,000–$5,000**.
These few repeat buyers contribute disproportionately to overall revenue, confirming the ***Pareto Principle ***(20% of customers drive 80% of the value). Suggesting frequency directly impacts value.

**Recommendations**
- Introduce retention programs (loyalty rewards, email re-engagement, exclusive offers) to bring back **one-time buyers and reduce churn.**
- Focus marketing efforts on **high- and medium-value** customers by building VIP customer experiences (early access, personal discounts, exclusive content) to retain high-value customers.
- Key drivers behind reduced customer spending could be pricing, engagements, or UX issues.
- Implement customer feedback surveys to gather insights and personalize marketing.
  
## **Product Categories Analysis**
**Focus**: Product Performance |Category Analysis | Sales Breakdown | Revenue Optimization
![Products Dashboard](https://github.com/user-attachments/assets/f3543465-370e-4a47-ac7c-d9545d93b1cc)

**Key Insights**

1. Total Performance Overview
**$1,408,057** in total sales from **5,969** products, with an average selling price of **$265**.
indicates a product mix that is mid-to-high priced and typically consists of home goods, electronics, and health-related items.
2. Least Performing Products:
Products like **Product 15, Product 20**, and multiple **unspecified category (electronics, beauty & health, sports & outdoors, clothing)** items had sales below **$16,000**.
A common pattern is **low total quantity sold (below 90 units)**, suggesting poor visibility, low demand, or inventory issues.
3. Product 47 and Product 29 are top performers, each generating over** $42,000** in sales, driven by high quantities sold and gift card payments.
Payment methods like **gift cards, PayPal, and credit cards** dominate, hinting at user preference for digital convenience.
4. Product Categories by Volume:
**Electronics** and **Home Kitchen** categories lead in product quantity sold, with **1,368** and **1,253 units,** respectively.
**Beauty & Health and Clothing** categories show moderate performance but have potential for growth with the right targeting.
5. Customer Type Split:
New customers account for the bulk of category sales, e.g., **1,368** electronics purchases vs. **100** returning customers.
**Low returning customer interaction** across all product categories shows a significant retention gap.

**Recommendations**
1. Maximize High Performers
Top-selling items like **Product 47 and Product 29** are driving strong revenue. Increase their visibility through promotions, ensure consistent availability, and explore bundling them with underperforming products to boost overall sales.
2. Boost Repeat Purchases
While attracting new customers is great, **repeat purchases are low.** Introduce loyalty programs or send friendly reorder reminders to encourage one-time buyers to return and build long-term relationships.
Targeted email campaigns offering exclusive deals on previously purchased categories can help.
4. Capitalize on Gift Card Demand
Data indicates strong consumer preference for gift cards. To maximize this opportunity:
Increase visibility through homepage placement and targeted email campaigns.
Introduce tiered incentives, such as bonus credits for higher-value purchases (e.g., “Spend $100, get $10 extra”) to stimulate adoption and also increase customer loyalty.
5. Underperforming Product Enhancement
Include high-resolution imagery and optimized product copy to enhance conversion potential.
Introduce promotional bundling strategies to increase **average order value** and inventory turnover

## **Order Insights**
**Focus:** Product Performance |Category Analysis | Sales Breakdown | Revenue Optimization.
![Order Insights](https://github.com/user-attachments/assets/c689363f-37f1-475d-a139-0c6df7e619fe)

**Key Insights**

1. **1,000** orders in total, with an **average order value (AOV) of $1,408.** Nonetheless, the low order fulfillment rate of 34% indicates notable inefficiencies in order fulfillment.
Order Status Breakdown.
2. Only **34%** of orders are **completed**, while **35.7%** are** cancelled** and **30.3%** are pending. This should be considered a red flag for customer satisfaction and logistics.
Cancellations may be linked to issues in inventory, delivery delays, or checkout experience.
3. Product Category Performance
**Home & Kitchen** leads in volume with **254 orders**, followed by **Beauty & Health (199)** and **Sports & Outdoors (196).**
Despite high order volumes, all product categories show fulfillment rates below **40%**, with electronics at **36%,** performing slightly better than others.

 **Recommendations**
- **Investigate supply chain bottlenecks** in lower-performing categories by considering surveying customers and reviewing fulfillment processes (e.g., supplier delays in Sports & Outdoors).
- **Optimize inventory and logistics planning** for high-demand categories like Home-Kitchen and Beauty & Health to improve fulfillment efficiency.
- **Streamline order processing systems** to raise fulfillment rates, potentially automating order handling or reviewing supplier performance.

## **Regional Sales Analysis**
![Regional Sales ](https://github.com/user-attachments/assets/9323669d-7f50-4cd1-9983-6157119a5f01)

**Key Insights**
1. Product Category Performance
- Total Sales: **$1,408,057** across **1,000** orders
- Electronics dominates sales **(748 units)**, showing strong demand across regions. Home & Kitchen** (339 units)** and Sports & Outdoors **(318 unit)** came next.
- Clothes lags **(258 units)**, indicating possible changes to marketing or inventory.
2. Regional Sales & Customer Behavior
- **South America** tops in order quantity ** (1,463)** and is dominated by **gift card payments;** This is a key regional preference.
- **Europe** and **North America** follow closely in total quantity, with **PayPal** being the most preferred payment method.
- **Africa** has the lowest fulfilled quantity among the top regions, indicating a potential distribution gap or logistics barrier.
- **Unknown Region** shows moderate revenue despite **low order volume**, suggesting **higher-value purchases**.
3. Revenue by Region
- **Europe** leads in total revenue, driven by a high volume of returning customers.
Most regions, especially **Asia and Unknown**, show strong performance from returning customers, emphasizing loyalty and repeat purchase potential.

**Recommendations:**
- **Optimize Supply Chain for High-Performance Markets**: Prioritize inventory and logistics enhancements in South America, where sales volume indicates strong demand. Streamlining operations here will maximize revenue potential.
- We need to assess critical factors such as **shipping reliability, localized pricing, and market penetration barriers** to fully understand why Africa is underperforming despite high PayPal adoption.
- **Leverage customer loyalty in Europe and Asia** through targeted retention strategies (e.g., offers for returning customers, personalized offers, subscription incentives).
Expand the availability of gift card and PayPal options across all regions, ensuring a seamless checkout experience that aligns with proven consumer preferences.









