## Marketing Analytics Project: Optimizing ShopEasy's Customer Engagement and Conversion Rates Using SQL, Python, Power BI

### Objective:
The primary objective of this project was to analyze and optimize ShopEasy's marketing strategies to address declining customer engagement, reduced conversion rates, and high marketing expenses. By leveraging data from customer reviews, social media interactions, and campaign performance metrics, the project aimed to uncover actionable insights that could enhance marketing efficiency and overall customer satisfaction.

### Goals:

#### 1. Increase Conversion Rates:
Identify factors contributing to drop-offs in the conversion funnel and recommend strategies to improve customer conversion rates.

#### 2. Enhance Customer Engagement:
Analyze interaction levels with various marketing content types to inform content creation strategies that maximize engagement.

#### 3. Improve Customer Feedback Scores:
Understand recurring themes in customer reviews to identify customer pain points and areas for service improvement.

This project demonstrated expertise in integrating data analysis with real-world business problems, delivering impactful recommendations that align with horizontal goals.

### Steps Undertaken:

### Step 1: Data Cleaning and Transformation for Actionable Insights using SQL.

#### 1. Data Extraction and Preparation:
The dataset, consisting of five key tables—Customer, Product, Customer Review, Customer Engagement, and Customer Journey—was extracted from a .bak file using Microsoft SQL Server. The raw data was cleaned, and SQL transformations were applied to ensure consistency and readiness for analysis.

#### 2. Customer Data Enrichment:
A SQL query joined the Customer table with the Geography table, enriching customer profiles with geographic details such as country and city. This step provided deeper insights into customer demographics.

#### 3. Product Categorization:
Products in the Product table were categorized into price segments—Low, Medium, and High—using a CASE statement. This segmentation allowed for better analysis of product performance across price ranges.

#### 4. Customer Review Standardization:
Review text from the Customer Review table was cleaned by standardizing whitespace, ensuring consistent and readable feedback data for sentiment analysis.

#### 5. Engagement Data Normalization:
The Customer Engagement table was normalized by:

- Cleaning content types (e.g., replacing "Socialmedia" with "Social Media").
- Extracting Views and Clicks from combined fields using string functions.
- Converting dates to a standard format (dd.MM.yyyy) for consistency.

#### 6. Customer Journey Optimization:
Duplicate records in the Customer Journey table were identified and handled using a Common Table Expression (CTE) with ROW_NUMBER(). Missing durations were imputed with the average duration for the corresponding visit date using the COALESCE function, ensuring data completeness and reliability.

