# Zomato - Customer Segmentation Analysis By Demographics

## Project Overview
This analysis aims to understand and group users based on common gender, income, and marital status to identify patterns in customer behavior, such as preferences and purchase habits. 

- Objective: Understand which types of customers contribute the most to the business and how their behaviors vary across different segments to optimize business operations, offerings, positioning.   

## Business Challenges
- Absence of marketing strategies specifically designed for distinct customer segments.
- Insufficient insight into customer demographics and preferences.
- Relationship management efforts need to be optimized.

## Questions Solved
- What is the distribution of gender, income, occupation, and marital status among the customer base?
- What are the segments for Zomato’s customer base?
- How do purchase patterns differ across different segments?

## Files
- Requirements
- Created datasets (power bi)
- Report 

## Table of Content
| Tab Title| Description | 
| -------- | ------------|
| Data | Overview of the data source |
| Description | Basic information about the project goals and final deliverables. |
| Process | General outline of the steps taken during the analysis. |
| Findings | Insights gathered after the data analysis. |
| Recommendations | List of recommended further steps the company should consider to reduce return rate on purchases. |

## Data 
The following tables where provided by TripleTen:
- `orders`: order records for each customer. 
- `users`: demographic data about all customers. 

I created the following tables during the RFM analysis in Power BI:
- `RFM Table`: contains calculated fields for R, F, M values and scores, associated to each individual user ID.
- `Segments Table`: contains index, segments, and score for each group. 

## Description
- A Tableau dashboard including KPIs, customer segments, a purhase frequency analysis to identify seasonality, and a comparison between purchase value and purchase income based on customers' income level.   
- A Power BI dashboard including KPIs, bar graphs comparing R, F, and M values with their corresponding scores, and a RFM Treemap to visualize customer segmentation based on their value to the business. 
- RFM table with user ID, RFM score and segment associated with each customer.  

## Process 
1. Data preparation and cleaning to ensure data is clean and complete, containing relevant information about customers’ demographics and purchase records. Remove missing values, outliers, and inconsistencies to ensure data quality. 
2. Hypotheses formulation.
3. Exploratory Data Analysis (EDA) to understand the data’s characteristics, and identify customer types and relationships, adding the following calculated fields:
    - first order date
    - last order date
    - customer lifetime 
    -  average order value
    - average number of purchases
    - CLTV
    - purchase frequency
4. Customer segmentation based on demographics data with Tableau -> Who are Zomato's customer base? 
5. RFM Customer segmentation analysis.
6. Comparison of customer segmentations with purchase habits. 
7. Gather insights and provide recommendations.
8. Build a dashboard and report based on visualizations.

## Findings
**Demographic Segmentation Analysis** 
- Most customers are students (no income) or middle class  employees with an income between $50k and $25k. 
- The majority of customers (female and male) are students with no income (53k+ total customers).
- More than 57k out of 100k customers are males.
- Zomato’s customer based is made of male students between the ages of 23 and 27. This customer segment counts with more 15k+ customers.
- Their purchase behavior is affected by seasonality, presenting a spike in purchase frequency (26.3 days) in July, and their lowest average purchase frequency happening in December (16.7). 
- Customers with a salary above $50k present a higher purchase size, 3 points above customers with salaries between $25k and $10k. 

**RFM Segmentation Analysis**
- The largest groups are "About to Sleep" (17.98k users)  and "Loyal” (16.18k users)  which may suggest areas for targeted engagement to convert these into higher-value segments like "Champion."
- Only 5.6k customers are part of the “Champions” segment. 
- At-risk customers such as “Cannot Lose Them” (6.38k users) and “At Risk” (1.53k users) represent a lower percentage of Zomato’s total customer base, but a higher percentage of users compared to the user count in the “Champion” segment. 


## Recommendations 
- Offer gender and age group personalized  experiences where these segments are underrepresented, such as discounts, targeted promotions, or gamified engagement experiences.
- Offer premium services, and exclusive product lines for customers with high income in segments like Champion and Loyal customers to enhance their experience and solidify loyalty. 
- Provide high-value customer service and reminders of the brand benefits to ensure customers in the “Cannot Lose Them” segment feel valued. 
- Consider one-time re-engagement offer such as steep discounts or special promotions to bring “At Risk” customers back. 
