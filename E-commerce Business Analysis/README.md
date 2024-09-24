# E-commerce Business Analytics

## Project Overview
 This is an e-commerce cohort analysis project focused on converting raw transaction logs into actionable business metrics. My primary task was to create a conversion funnel to analyze how effectively the website transformed product page views into purchases. Additionally, I built acquisition cohorts based on users’ first purchase month and tracked their retention rates month by month, with a significant emphasis on preparing the data for cohort analysis.

![image](https://github.com/user-attachments/assets/580ac793-1015-4529-baad-5ab2305b3e6d)


## Files 
- README.md 
- <a href='https://docs.google.com/spreadsheets/d/1FZjRxQ-1p2nEYt5tsLuV4qldkz2OfiyAIa4R035DDts/edit?usp=sharing' target=_blank><u>E-commerce Business Analysis</u></a>
- <a href='https://docs.google.com/spreadsheets/d/1yuavBZ4OYYUD1opH-dq0d6nejREDy8f0ozumT9-yEuo/edit?gid=0#gid=0' target=_blank><u>Dataset</u></a>
- Reviewer Grade 


## Table of Content
| Tab Title| Description | 
| -------- | ------------|
| Data | Overview of the data source |
| Description | Basic information about the project goals and final deliverables. |
| Assumptions | List of assumptions regarding the provided dataset made based on the task objectives and data. |
| Process | General outline of the steps taken during the analysis. |
| Findings | Insights gathered after the data analysis. |

## Data 
The data contains information about user activity on the e-commerce website.    
The dataset has the following columns:
* `user_id`: unique customer IDs   
* `event_type`: the type of activity by the user   
* `category_code`: category of the product being viewed or purchased   
* `brand`: company that makes the product   
* `price`: price of the product, in USD   
* `event_date`: date of the user activity, in YYYY-MM-DD format   

## Description
- Delivered an 8-page spreadsheet document.    
- In this document, you'll find an organizational tab, raw data, purchase activity, conversion funnels, cohort analysis, and retention rates. 

## Assumptions
- Only data related to the user ID, event type, and transaction date was used. 
- The conversion funnel illustrates the number of unique users at each stage of the conversion funnel, and how the percentage of the same follows a downward trend as we continue through the funnel. 
- Retention rates are based on monthly user cohort percentages and fluctuations in user activity during each cohort year. 

## Process 
1. Explored, cleaned, and filtered the data 
2. Built a conversion funnel (3 stages) to understand how users interact with the website (unique user count). 
3. Created pivot table with total conversion rates and conversion rates to the next step. 
4. Built acquisition cohort based on the month of the users' first purchase by calculating and setting up monthly data. 
5. Group data into cohorts and calculate overall retention rates. 
6. Organize and document the spreadsheet for stakeholder review 

## Findings 
- Conversion funnel: Data suggests that only 1 out of 10 prospects that visit the e-commerce website make a purchase, while roughly 1/3 of the users in each funnel stage continue to the next step. 
- Retention rate: In September, we retained 13% of users after the first month. The retention rate kept dropping, reaching a low of 4% in the 4th month. In our January 2021 cohort, we only retained 7% of users. 
