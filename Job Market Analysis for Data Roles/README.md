# Data Job Postings Analysis

## Project Overview 

1[image]

## Files 

## Table of Content
| Tab Title| Description | 
| -------- | ------------|
| Data | Overview of the data source |
| Description | Basic information about the project goals and final deliverables. |
| Assumptions | List of assumptions regarding the provided dataset made based on the task objectives and data. |
| Process | General outline of the steps taken during the analysis. |
| Findings | Insights gathered after the data analysis. |
| Recommendations | List of recommended further steps the company should consider to reduce return rate on purchases. |

## Data
Dataset with information on data related job postings from multiple job boards. The dataset contains information pertaining to 2023.   
* `company_dim`: 
* `job_postings_fact`:
* `skills_dim`:
* `skills_job_dim`:

## Description & Tools
- Created Postgress connections (database) and tables from scracth with SQL queries.
- Created 5 SQL queries of different complexities to analyze the job market for analyst roles, focusing on salary and skills.
- SQL Postgres, Visual Studio Code, pgAdmin4 and GitHub where used for this project.

## Assumptions

## Process 
- Using the job postings dataset, I performed joins and subqueries to identify top paying jobs for data analyst roles in the US for 2023. 
- Analyzed top paying jobs to identify the most in demand skills, and top skills based on salary. 
- I performed a final analyzing utilizig CTEs and subqueries to match previos analysis results, and find the most optimal skills to learn for career advancement in the data field. 

## Findings 
### 1. Top Paying Jobs in Data Analyst Roles 
The goal was to identify the top 10 highest-paying data analyst roles available remotely. 
Only job postings with specified salaries where used on this query (not nulls).   


```
SELECT
    job_id, 
    job_title,
    name AS company_name,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date
FROM
    job_postings_fact
    LEFT JOIN company_dim ON company_dim.company_id = job_postings_fact.company_id
WHERE
    job_title_short = 'Data Analyst' AND
    job_work_from_home = TRUE AND
    salary_year_avg IS NOT NULL
ORDER BY 
    salary_year_avg DESC
LIMIT  10;
```
**Findings:**
- Significan salary variation was found: The highest-paying role, a Data Analyst at Mantys, offers a staggering average salary of $650,000. Other high-paying roles include a Director of Analytics at Meta ($336,500) and an Associate Director - Data Insights at AT&T ($255,829.5).
- Many of the top-paying roles are leadership positions.
- All jobs listed are remote or hybrid, which shows that high-paying positions in data analytics no longer require on-site presence.
- Sectors like Healthcare (Uclahealthcareers), Finance (SmartAsset, Motional), and Marketing (Pinterest) also show a willingness to offer competitive pay for specialized data analyst roles.


![imge]

### 2.Skills Required for top-paying analyist roles
To provide a more detailed look at high-paying jobs, I identified top skills that would help job seekers understand which skills to develop. 

```
WITH top_paying_jobs AS (
    SELECT
        job_id, 
        job_title,
        name AS company_name,
        salary_year_avg
    FROM
        job_postings_fact
        LEFT JOIN company_dim ON company_dim.company_id = job_postings_fact.company_id
    WHERE
        job_title_short IN ('Data Analyst', 'Business Analyst') AND
        job_work_from_home = TRUE AND
        salary_year_avg IS NOT NULL
    ORDER BY 
        salary_year_avg DESC
    LIMIT  10
)

SELECT
    top_paying_jobs.*,
    skills AS skill_name
FROM
    top_paying_jobs
    INNER JOIN skills_job_dim ON skills_job_dim.job_id = top_paying_jobs.job_id
    INNER JOIN skills_dim ON skills_dim.skill_id = skills_job_dim.skill_id
ORDER BY
    salary_year_avg DESC;
```
**Findings:**
-  SQL and Python are non-negotiable skills in high-paying data analyst roles. 
- There is a strong demand for proficiency in data visualization and reporting tools, with Tableau leading, followed by Power BI and Excel.
- Cloud platforms and big data tools are increasingly necessary as companies move to more scalable, cloud-based solutions.
- Proficiency in statistical programming and data engineering skills (such as Hadoop and Databricks) is a significant plus for candidates looking to land top-paying jobs.

![image]

### 3. Most demanded skills
Zooming out, I analyzed the top 5 skills by demand in remote jobs for Data and Business Analyst roles, regardless of salary or role seniority. 

```
SELECT 
    skills,
    COUNT(skills_job_dim.job_id) AS demand_count
FROM
    job_postings_fact
    INNER JOIN skills_job_dim ON job_postings_fact.job_id = skills_job_dim.job_id
    INNER JOIN skills_dim ON skills_job_dim.skill_id = skills_dim.skill_id
WHERE
    job_title_short IN ('Data Analyst', 'Business Analyst')
GROUP BY 
    skills
ORDER BY demand_count DESC
LIMIT 5
``` 
**Findings**
- SQL leads the demand with 110,000 job postings mentioning it, making it the most sought-after skill.
- Excel remains highly relevant, with 84,165 job postings highlighting its importance.
- Python, a key programming language for data analysis, machine learning, and automation, ranks third with 65,423 job postings.
- Tableau and Power BI, two leading data visualization tools, are in high demand, with 55,878 and 48,719 job postings, respectively.

### 4. Most optimal skills to learn
Lastly, I combined data on skills in high demand associated with high average yearly salaries for Data and Business Analytics roles. 
Focusing on remote positions, with specified salaries, the objective was to highlight skills that offer job security (high demand) and financial benefits. 

```
WITH skills_demand AS (
    SELECT 
        skills_dim.skill_id,
        skills_dim.skills,
        COUNT(skills_job_dim.job_id) AS demand_count
    FROM
        job_postings_fact
        INNER JOIN skills_job_dim ON job_postings_fact.job_id = skills_job_dim.job_id
        INNER JOIN skills_dim ON skills_job_dim.skill_id = skills_dim.skill_id
    WHERE
        job_title_short IN ('Data Analyst', 'Business Analyst') AND
        salary_year_avg IS NOT NULL
        AND job_work_from_home = TRUE
    GROUP BY 
        skills_dim.skill_id
),  highest_payed_skills AS (
    SELECT
        skills_job_dim.skill_id, 
        ROUND(AVG(job_postings_fact.salary_year_avg), 2) AS avg_salary
    FROM
        job_postings_fact
        INNER JOIN skills_job_dim ON skills_job_dim.job_id = job_postings_fact.job_id
        INNER JOIN skills_dim ON skills_dim.skill_id = skills_job_dim.skill_id
    WHERE
        job_title_short IN ('Data Analyst', 'Business Analyst') AND
        job_work_from_home = TRUE AND
        salary_year_avg IS NOT NULL
    GROUP BY
        skills_job_dim.skill_id
)

SELECT
    skills_demand.skill_id, 
    skills_demand.skills,
    demand_count, 
    avg_salary
FROM
    skills_demand
    INNER JOIN highest_payed_skills ON skills_demand.skill_id = highest_payed_skills.skill_id
WHERE
    demand_count > 10 
ORDER BY
    demand_count DESC,
    avg_salary DESC
LIMIT 25
```
**Findings:**
- SQL is the most in-demand skill, appearing in 440 job postings with an average salary of $97,416.89.
- Python offers the highest average salary of $102,578.39 with 256 job postings, making it a highly rewarding skill.
- Tableau commands a strong average salary of $99,807.24 with 257 job postings.
- Cloud platforms such as AWS (32 postings, $108,317.30) and Azure showcase high earning potential. 
- Alongside Tableau and Power BI (122 postings, $96,744.37), tools like Looker offer competitive salaries ($106,258.69) with moderate demand (54 postings).

![image]
