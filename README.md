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

__This step demonstrated advanced technical expertise in text analytics, Python programming, and data enrichment, showcasing an ability to translate raw customer feedback into actionable business intelligence.__
