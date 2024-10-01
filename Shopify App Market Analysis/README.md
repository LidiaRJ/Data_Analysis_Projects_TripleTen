 # Shopify App Analysis

 ## Project Overview 
 Using data scraped from publicly available Shopify websites, I reviewed user behavior to identify key factors contributing to the success of Shopify apps. Using insights from data visualization, I proposed strategies to help app developers optimize their app performance and increase adoption rates.

This independent project was part of the TripleTen Business Intelligence Curriculum, where I utilized data storytelling techniques to uncover actionable insights in the e-commerce app ecosystem.

![image](https://github.com/user-attachments/assets/84e147e8-49da-4c43-bad7-a40705b3011a)


 ## Files
- README.md 
- Requirements
- <a href='https://practicum-content.s3.us-west-1.amazonaws.com/data-eng/BIA/Dataset/shopify.xlsx' target=_blank><u>Shopify Dataset</u></a>

## Table of Content
| Tab Title| Description | 
| -------- | ------------|
| Data | Overview of the data source |
| Description | Basic information about the project goals and final deliverables. |
| Data Assumptions | List of assumptions regarding the provided dataset made based on the task objectives and data. |
| Process | General outline of the steps taken during the analysis. |
| Findings | Insights gathered after the data analysis. |


## Data 
The dataset contains public data scraped from the <a href='https://apps.shopify.com/' target=_blank><u>Shopify App Store</u></a>. It includes 4 tables: 
- `apps`: Details of the apps on the Shopify apps marketplace.
- `apps_category`: Join tables to connect apps with categories. 
- `categories`: Categories of the apps. Each app has multiple categories. 
- `reviews`: Each review (row) contains information on user opinions about the related app (rating and comments). Contains the response from the developer if present. 

## Description
- I created a multi-page Power BI report featuring visualizations and insights across 3 sections: app landscape, reviews, and developer responses to user reviews. 

## Data Assumptions
- The data scraped from publicly available Shopify websites is assumed to be up-to-date.
- It is assumed that user reviews are genuine, and the helpful_count is an accurate measure of how useful users find each review.
-The dataset contains all relevant fields (apps, categories, reviews, etc.) needed to analyze app success factors. It is assumed to include a sufficient number of apps and reviews to draw meaningful conclusions.

## Process
1. Found key statistics on the types of apps in the Shopify market based on review count and average ratings using line charts and scatterplots. 
2. Analyzed reviews by creating columns with aggregated data to match ratings with helpful reviews with bar charts.
3. Compared the average ratings with the total developer answers using a scatterplot. 

## Findings
- Apps are mostly rated early on after they have been released.    
- Most apps have a rating above 3.   
- There is no correlation between high ratings and the amount of total review. 
- Only a fourth of the ratings are addressed by developers. 
- The developer under "FireApps" has a total of answered reviews of 6,008, being the top contributor. 
