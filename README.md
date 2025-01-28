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



### Step 2: Incorporating Sentiment Analysis to Enhance Customer Feedback Insights

In this step deeper insights were derived from customer feedback by performing sentiment analysis. This process involved integrating advanced text analytics techniques with structured data, ensuring a comprehensive understanding of customer sentiments.
Below are the key steps undertaken:

#### 1. Data Retrieval from SQL Database:

Connected to the Microsoft SQL Server database and executed a query to extract relevant fields from the customer reviews dataset, including ReviewID, CustomerID, ProductID, ReviewDate, Rating, and ReviewText. The extracted data was loaded into a pandas DataFrame for further processing.

#### 2. Implementing VADER Sentiment Analysis:

Leveraged the VADER (Valence Aware Dictionary and sEntiment Reasoner) sentiment analysis tool from Python’s nltk library. VADER was chosen for its effectiveness in analyzing sentiment intensity in text, especially for short reviews. Sentiment scores were calculated for each review, providing a normalized value between -1 (most negative) and 1 (most positive).

#### 3. Categorizing Sentiments:

To refine the sentiment insights, we combined VADER sentiment scores with customer ratings. A custom Python function was developed to classify feedback into categories:

- Positive: Strong alignment between positive scores and high ratings.
- Negative: Strong alignment between negative scores and low ratings.
- Neutral: Indicating a balanced or indifferent sentiment.
- Mixed Positive/Mixed Negative: For cases where scores and ratings were not aligned.
  
This dual-layer categorization ensured that both text-based sentiment and numerical feedback were captured.

#### 4. Creating Sentiment Buckets:
The sentiment scores were further segmented into predefined ranges:

- Strongly Positive (0.5 to 1.0)
- Mildly Positive (0.0 to 0.49)
- Mildly Negative (-0.49 to 0.0)
- Strongly Negative (-1.0 to -0.5)
  
This step enabled easier visualization of sentiment trends and the distribution of customer emotions.

#### 5. Data Export for Visualization:

The enriched dataset, now including the sentiment scores, categories, and buckets, was exported to a CSV file (fact_customer_reviews_with_sentiment.csv). This prepared data was later integrated into Power BI dashboards for detailed visualizations and actionable insights.

#### Outcome and Value Addition:

The sentiment analysis revealed key customer pain points and areas of satisfaction, allowing for targeted marketing strategies and product enhancements. By combining text analysis with structured data, this step provided a holistic view of customer opinions, significantly boosting the depth of our insights.

_This step demonstrated advanced technical expertise in text analytics, Python programming, and data enrichment, showcasing an ability to translate raw customer feedback into actionable business intelligence._

### Step 3.  Building an interactive marketing analytics dashboard using Power BI.

In this step we brought our marketing data to life by building an interactive marketing analytics dashboard using Power BI, it involved integrating data from SQL Server into Power BI for analysis, followed by extensive data cleaning, transformation, and modeling to derive actionable insights. 
The steps included:

#### 1. Data Import and Query Execution

- Data was imported into Power BI using the "Get Data" feature, specifically from SQL Server. This provided access to multiple tables, including customer reviews, customer engagement, and journey data.
- SQL queries executed directly in SQL Server were reused within Power BI to maintain data integrity and consistency. This ensured that data cleaning and transformation were performed in a controlled manner
- Additionally, the fact_customer_reviews_with_sentiment.csv file was imported into Power BI to complement the data and provide sentiment insights for the analysis.

#### 2. Data Modeling

- A one-to-many relationship was established between the customer and product tables with the fact_customer_journey, fact_engagement_data, fact_customer_reviews, fact_customer_reviews_with_sentiment tables.
- The relationship was created based on CustomerID and ProductID, ensuring that each fact table could be properly linked to the customer and product information for detailed analysis.
- A Calendar table was created using DAX to provide a time dimension for the dataset. This table contained date-related columns like Year, Month, DayOfWeek, Quarter, etc., to support time-based analysis.
- A relationship was established between the Calendar table and the fact tables (fact_customer_journey, fact_engagement_data, fact_customer_reviews, and fact_customer_reviews_with_sentiment) based on the Date field.
- This relationship allowed for efficient time-series analysis across various metrics, enabling the analysis of campaign performance and engagement trends over time.

#### 3. DAX Calculations

- Several key performance indicators (KPIs) were calculated using DAX measures to assess campaign performance:
           - Number of Campaigns: The total count of campaigns being analyzed.
           - Number Customer Reviews: Count of reviews from customers for each campaign.
           - Number of Customer Journey: Total number of customer journeys tracked through the campaign lifecycle.
           - Average Rating: The average rating of products/campaigns based on customer reviews.
           - Engagement Metrics: Total views, clicks, and likes related to the campaign, derived from customer engagement data.
           - Conversion Rate: The percentage of customers users who take a desired action, such as making a purchase.

#### 4. Visualizations and Insights:

- Created multiple visualizations in Power BI to identify patterns, trends, and key insights aligned with business goals.
- Time-series analysis was conducted using the Calendar table to evaluate trends over time, especially for campaign performance metrics like views, clicks, and conversion rates.
- Data analysis focused on customer sentiment, engagement metrics, and campaign performance, leading to actionable recommendations for strategic decisions

### Results
