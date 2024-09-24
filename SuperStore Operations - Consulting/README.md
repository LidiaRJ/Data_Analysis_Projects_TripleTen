# SuperStore Operations Analysis with Tableau

## Project Overview
Data analysis of an e-commerce superstore to review their operations, and provide recommendations to increase their profitability, and discover strategies that avert the risk of bankruptcy. 
This was an independent project I completed consisting of a comprehensive Tableau Workbook, comprising data analysis, data visualization, and a dashboard.<br>
The data was provided as an Excel document with sheets on Order, and Returns data.    

![image](https://github.com/user-attachments/assets/9f3d6992-8e2c-4be4-b1e3-5a2c8b486ec4)




<a href='https://public.tableau.com/views/2023_11_19_Project4_TB/ProfitLossCenters?:language=en-US&:display_count=n&:origin=viz_share_link' target=_blank><u>Tableau Public project link </u></a>



    
## Files  
- [Dataset - SuperStore.xls](https://github.com/LidiaRJ/SuperStore-operations-analysis---Trableau/blob/main/Superstore.xls)
- Readme.md


## Table of Content
| Tab Title| Description | 
| -------- | ------------|
| Profit & Losses by Product | Overview of the profits by product subcategory and region. |
| Product Analysis | Analysis of profit and losses by product subcategory regardless of geographical location. |
| Loss-makers Products | Analysis of the top ten products generating the highest losses. |
| Profit per Month | Overview of the most profitable month per state. |
| Profit per State | Analysis of the top three states with the highest average profit. |
| Advertising Dashboard | Combination of top most profitable months and states for advertising, including advertising budget recommendations. | 
| Returned Items | Analysis of returns ratio based on product subcategory. |
| Customer Returns | Analysis of the top ten customers with the highest product return requests. |
| Returns vs Profit | Prdoduc types the store should focus on based on profit vs returns rate to increase revenue and minimize loss. | 
| Customer Returns & Profit Dashboard | Overview of the product returns related to product type, segment, and profit. |    

## Assumptions
- Profit from sales is reaching negative values, generating losses.
- Losses have several root causes and are directly related to orders and returns.
- Not all products are generating revenue.
- Sales fluctuate based on the time of the year. 
- The advertising department needs guidance on a new strategy to increase sales.

## Process
The project workflow was divided into the following stages: 
- Consolidating the orders and return data with a left join using the primary key: order ID.
- Identifying profit and loss centers among different dimensions (product sub-category and region). 
- Identifying the combination of the top 3 states and months in which the company should increase its advertising efforts, and determining the appropriate advertising budget per month.
- Identifying the product sub-categories with the highest returns by customers, and providing recommendations regarding products the company should stop selling based on data.

## Findings
__Profit & Losses__
- The two biggest profit centers are copiers in the West region and chairs in the East region. 
- The two loss centers are binders in the Central region and Tables in the East region.
  
__Advertising__    
Advertising efforts should focus on the following combination of months and states, as they present the current highest profit values:
  - Vermont - November
  - Rhode Island - December
  - Indiana - October.
The fourth quarter of the year presents a higher opportunity for revenue growth for the states mentioned above.

__Product Returns & Profit__
- Copiers are the most successful product among customers, presenting the highest profit value and lowest total returns. 
- Tables present a negative profit value and the highest total return number. This product should be discontinued to avoid an increase in losses. 
