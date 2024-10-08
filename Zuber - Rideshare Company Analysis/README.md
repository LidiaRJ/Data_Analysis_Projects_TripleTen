# Rideshare-analysis   

## Project Overview 
During this project, I analyzed patterns in the duration of rides from Loop to the O'Hare International Airport based on weather records and day of the week. The objective was to find patterns in competitors' data to understand passenger preferences and the impact of external factors on ride frequency.

![image](https://github.com/LidiaRJ/Data_Analysis_Projects_TripleTen/blob/main/Zuber%20-%20Rideshare%20Company%20Analysis/bar%20graph.png)


## Files 
README.md   
<a href= 'https://github.com/LidiaRJ/Data_Analysis_Projects_TripleTen/blob/main/Zuber%20-%20Rideshare%20Company%20Analysis/Zuber%20-%20SQL%20Data%20collection%20and%20processing.pdf' target=_blank><u>SQL_query_code.pdf</u></a>   
<a href='https://github.com/LidiaRJ/Rideshare-analysis/blob/main/Requirements.txt' target=_blank><u>Requirements.txt</u></a>

## Table of Content
| Tab Title| Description | 
| -------- | ------------|
| Data | Overview of the data source. |
| Table Scheme | Relationship between the tables in the Zuber dataset |
| Description | Basic information about the project goals and final deliverables. |
| Assumptions | List of assumptions regarding the provided dataset made based on the task objectives and data. |
| Process | General outline of the steps taken during the analysis. |
| Results | Insights gathered after the data analysis. |

## Data 
A database with information on taxi rides in Chicago: 
`neighborhoods` table: data on city neighborhoods   
* `name`: name of the neighborhood   
* `neighborhood_id`: neighborhood code   

`cabs` table: data on taxis 
* `cab_id`: vehicle code   
* `vehicle_id`: the vehicle's technical ID   
* `company_name`: the company that owns the vehicle   

`trips` table: data on rides   
* `trip_id`: ride code   
* `cab_id`: code of the vehicle operating the ride   
* `start_ts`: date and time of the beginning of the ride (time rounded to the hour)   
* `end_ts`: date and time of the end of the ride (time rounded to the hour)   
* `duration_seconds`: ride duration in seconds   
* `distance_miles`: ride distance in miles   
* `pickup_location_id`: pickup neighborhood code   
* `dropoff_location_id`: dropoff neighborhood code   

`weather_records` table: data on weather   
* `record_id`: weather record code   
* `ts`: record date and time (time rounded to the hour)   
* `temperature`: temperature when the record was taken   
* `description`: a brief description of weather conditions, e.g. "light rain" or "scattered clouds"

## Table Scheme
![image](https://github.com/LidiaRJ/Data_Analysis_Projects_TripleTen/blob/main/Zuber%20-%20Rideshare%20Company%20Analysis/scheme.png)

## Description
* A 6-step SQL query 
* Exploratory data analysis to explore how the duration of rides varies on rainy Saturdays from Point A to Point B.

## Assumptions 
* There is no direct connection between  the tables `trip` and `weather records` in the database. 
* The `neighborhood_id` is the Primary Key for the `neighborhood` table.
* The `cab_id` is the Primary Key for the `cabs` table. 
* The `trip_id` is the Primary Key for the `trips` table. 
* The `record_id` is the Primary Key for the `weather_records` table. 

## Process 
* Analyzed taxi rides for each company for specific dates, sorting by trip amount. 
* Analyzed rides for companies containing specific keywords, and grouped the results by company name. 
* Retrieved identifiers of specific neighborhoods. 
* Retrieved weather condition records using the CASE operator, grouped by weather condition: good or bad.
* Retrieved rides for a specific route, on a specific weekday, as well as the weather conditions, and duration for each ride. 

## Results 
1. The taxi companies with the highest number of rides are Flash Cab and Taxi Affiliation Services, with 19,558 and 11,422 rides respectively between 11-15-2017 and 11-16-2017. 
2. When searching by the keywords 'Yellow' and 'Blue' in the SQL query, the companies Blue Diamond presented the highest amount of rides between 11-01-2017 and 11-07-2017. 
3. The weather conditions for rides that happened during 11-01-2017 fall under the 'Good' weather category. 
4. Retrieved the duration of rides that started at `pick_up_location_id`: 50 and `drop_off_location_id`:63, with the longest ride being 1380 seconds.

## Conclusions
This analysis provides insights into market leaders in the taxi space, patterns based on weather, and ride duration behaviors for specific routes.
The high number of rides from Flash Cab and Taxi Affiliation Services (19,558 and 11,422 rides respectively) indicates that these companies dominate the rideshare market within the specified period (11/15/2017 - 11/16/2017), suggesting strong customer loyalty or a large fleet of available cars compared to others.
  
Good weather typically leads to less disruption (fewer delays due to traffic or hazardous conditions), potentially explaining steady or higher ride volume. It could also suggest that users prefer to use rideshares even when weather conditions are favorable, indicating consistent demand regardless of weather.
On the other hand, trips with longer ride duration (20+ minutes) were recorded under bad weather conditions, suggesting traffic congestion and slower driving speeds as the main factors affecting these rides.

Further investigation could compare how bad weather impacts duration or explore trends by day and week to optimize operations.

