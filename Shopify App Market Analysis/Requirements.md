# Project Requirements 

## Part 1 - App Landscape
- Create a KPI card showing the unique number of apps.   
- Build a Line Chart showing the sum of review counts over time (lastmod date on the X-axis).   
- Create a Scatterplot with reviews_count on the X-axis and average rating on the Y-axis, adding a text box for interpretation.  

## Part 2 - Reviews
- Add a new column in the Reviews table for helpful_reviews using a DAX expression.   
- Create a Card displaying the average value of helpful_reviews.   
- Add a column for developer_answered (boolean) using a DAX expression.   
- Build a Scatterplot comparing average rating by developer_answered status.   

## Part 3 - Developer Responsivess
- Establish a relationship between the Reviews and Apps tables using app_id.   
- Create a Bar Chart with developer on the X-axis and the sum of ratings on the Y-axis.   
- Make a second Bar Chart showing developers against the average of helpful_reviews.   
- Build a Bar Chart displaying developers by their responsiveness, filtered for apps with more than 500 reviews.   
