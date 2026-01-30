# Introduction 
📊 This project explores the Data Analyst job market using real job posting data to answer 3 big questions:

1. 💰 Which Data Analyst roles pay the most?
→ Identify top-paying job titles and salary ranges.
2. 🔥 What skills are employers asking for the most?
-> Find the most common tools/skills (e.g., SQL, Excel, Python, Power BI).
3. 	📈 Which skills are both high-demand and high-paying?
→ Discover the “sweet spot” skills that maximize both salary potential and job opportunities.

✅ By the end, you’ll have a clear view of what to learn and what to target to improve your chances in the data analytics job market.

🔍 SQL queries: [project_sql](/project_sql/)

# Background
🎯 To navigate the Data Analyst job market more effectively, I built this project to identify top-paying roles and in-demand skills—helping streamline the job search and highlight what to learn to land better opportunities.

🗂️ The dataset comes from my SQL course and includes key information such as: [SQL Course](https://drive.google.com/drive/folders/1moeWYoUtUklJO6NJdWo9OV8zWjRn0rjN)
- 🧑‍💼 Job titles
- 💰 Salary
- 📍 Locations
- 🧰 Essential skills

### ❓ Key Questions

Using SQL queries, I aimed to answer:
1. What are the top-paying Data Analyst jobs?
2. What skills are required for these top-paying jobs?
3. Which skills are most in demand for Data Analysts?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn? 

# Tools I Used
For this project, I used a focused set of tools to query, manage, and share the analysis:
- **SQL:** Core language for querying the dataset and extracting insights.
- **PostgreSQL:** Database system used to store and manage job posting data.
- **Visual Studio Code:** Development environment for running SQL queries and organizing scripts.
- **Git & GitHub:** Version control and project sharing to track changes and publish the work.

# The Analysis
Each query for this project aimed at investigating specific aspects of the data analyst job market. Here’s how I approached each question:

### 1. Top Paying Data Analyst Jobs
To identify the highest-paying roles, I filtered data analyst positions by average yearly salary and location, focusing on remote jobs. This query highlights the high paying opportunities in the field.

```sql
SELECT
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    name AS company_name
FROM 
    job_postings_fact
LEFT JOIN company_dim 
    ON job_postings_fact.company_id = company_dim.company_id
WHERE 
    job_title_short = 'Data Analyst'
    AND job_location = 'Anywhere'
    AND salary_year_avg IS NOT NULL
ORDER BY 
    salary_year_avg DESC 
LIMIT 10;
```
Here's the breakdown of the top data analyst jobs in 2023:

- **Wide Salary Range:** The top-paying remote/“Anywhere” data analyst roles in this extract range from $184,000 to $255,829.5, showing a meaningful pay spread even within a small top list.
- **Diverse Employers:** High salaries come from multiple employers across different types of organizations, not just one company—indicating broad demand for analytics talent at higher pay levels.
- **Job Title Variety:** The titles vary widely—from Data Analyst roles to Principal/Director/Associate Director positions—suggesting compensation increases with seniority and scope (strategy, ownership, leadership).

![Top paying Roles](assets/Top_in-demand_skillsinthehighest-payingremote_Data_Analyst_roles(Anywhere).png)


# What I Learned

Throughout this adventure, I've turbocharged my SQL toolkit with some serious firepower:

- 🧩 Complex Query Crafting: Mastered the art of advanced SQL, merging tables like a pro and wielding WITH clauses for ninja-level temp table maneuvers.
- 📊 Data Aggregation: Got cozy with GROUP BY and turned aggregate functions like COUNT() and AVG() into my data-summarizing sidekicks.
- 💡 Analytical Wizardry: Leveled up my real-world puzzle-solving skills, turning questions into actionable, insightful SQL queries.

# Conclusions

