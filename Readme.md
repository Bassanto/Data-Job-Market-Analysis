
# Data Job Market Analysis
<img width="976" height="548" alt="Screenshot 2026-09-13 013009" src="https://github.com/user-attachments/assets/8205ec54-b053-4443-b259-1a08d627a9fa" />

## Introduction

This is a deep analysis into the Data Job Market , covering roles such 
as Data Analyst, Data Scientist, Data Engineer, Business Analyst, 
Senior Data Analyst, Machine Learning Engineer, Cloud Engineer, 
Software Engineer, Senior Data Scientist, and Senior Data Engineer . It evaluates the requirements for each role and the expected salary, 
both for remote and full-time positions.

The analysis is meant to help newcomers looking to venture into the 
data space, offering an explanation of the career path, what to 
expect, and the requirements for each role.

You can access the interactive dashboard here! 
[Data_market_analysis.pbix](./Data_market_analysis.pbix)

## Data Structure and Cleaning Process
This a job based dataset which comprises of a year (2024) market research. It comprises of 5 main tables which has different table content for proper analysis. The tables are: `skill_dim`,`job_postings_fact`,`skills_job_dim`,`company_dim`,`schedule_dim`.

**i** `skill_dim`:
This table consists of 3 columns , the skill_id, skills and type.The skill_id is a unique id for each skill and the skills colume contains the main skill while the type is the category of the skill.


<img width="232" height="553" alt="Screenshot 2026-09-13 013555" src="https://github.com/user-attachments/assets/328066ba-5555-48f0-b945-08929e695c22" />


### Data Cleaning Process
The table had many inconsistency in the data which I cleaned up using power query.
- I started by changing the data type of the skill_dim column from text to number. 
- At the skill column, I capitalized each first word to prevent ambiguity which will result duplicates in future. I added a conditional column afterward to format some skills. This led to a new column and I removed the old unclean column.

**ii** `job_postings_fact`:
This is the flat table which contains the crucial information about the project. 

<img width="1287" height="539" alt="Screenshot 2026-09-13 013314" src="https://github.com/user-attachments/assets/0dfd9848-f1ff-4c24-a75e-d82ecba11912" />


### Data Cleaning Process
- I extracted date from the normal datetime column I had. This is to improve the relationship connection between the table and calender table. The major reason behind extracting date instead of using datetime is to prevent confusion and ambuguity when analyzing.
- I added a column where I multiplied the hourly salary by 2080(standard of working hours in a year). This is to get the yearly value of salary of those who are paid hourly.

**iii** `skills_job_dim`: This table consists of 2 columns , job_id which is the unique id for each job and job_schedule_type which is contains the job type(s).

### Data Cleaning Process
The data cleaning process in the table is concentrated in the job_schedule_type column where there are multiple schedule_type in some row and inconsistent formatting. 

I splitted the column by delimitter "," so as to get all the schedule_type since there are more than 1 job in some rows. I trimmed the column afterward to remove unnecessary spaces in the column.

## Analysis
- **SALARY** : I used median fuction to analyse both yearly and hourly salary. This is to avoid the impact of outliers in my analysis. 

Columbia has the highest median salary in the job market with $224,000 salary while Pakistan is the least with $20,100. However, there are variation to this in terms of each job. The highest paying country based on each job includes:

    Job                         Country          Median Salary
                           
    Data Engineer                Panama            $288,825
    Data Scientist               Jamaica           $257,500
    Data Analyst                 Albania           $192,000
    Business Analyst             Guyana            $284,000
    Cloud Engineer               Cayman Islands    $207,500
    Software Engineer            Indonesia         $280,000
    Senior Data Analyst          Spain             $160,500
    Senior Data Scientist        France            $213,000
    Senior Data Engineer         Columbia          $224,000
    Machine Learning Engineer    Ukriane           $242,500


This create a great insight to which country one should look forward to while seeking for job based on their respective job. 

The top 3 paying jobs in the market based on yearly salary includes 


1. Senior Data Scientist
2. Machine Learning Engineer
3. Senior Data Engineer


The top 3 paying jobs in the market based on hourly salary includes 


1. Machine Learning Engineer
2. Software Engineer
3. Data Engineer

The reason for variation in the roles is that, there are less job listings in senior data roles in jobs that pays hourly.
Also, the analysis proves that yearly salaries are higher in total even when the hourly salary is adjusted to yearly figure by multiplying by (2080 ; standard measure of multiplying hourly salary).

- **SKILLS**

I performed several analysis on skill such as skill per job. Data job requires an average of 4.8 skills to get a job, this is simply gotten by dividing counts of job by number of skills in the dataset. 

~~~ skill per job = 
DIVIDE([Skill Count], [job count])
~~~
**Top in-demand skills include:**

1. Python
2. SQL
3. AWS
4. Azure
5. Tableau

These are the top in-demand skills in the data market as they are listed in more than 60% of jobs in the dataset. However, this does not mean they are the highest paying skills. 

**Highest paying skills:**

1. Unreal
2. Golang
3. Haskell
4. Node.Js
5. Redis

These skills are  associated to high paying skills and could be a great game changer for data nerds in their career. However, they do not often occur in skill for job listing like python and co. 

- **Skills Vs Salary**

There is a positive correlation between skill and salary. This means that the higher the skills one acquire, the higher the salary expected. 

## Insights and Recommendations
1. Data Engineer, Data Analyst, and Data Scientist are the top 3 most 
in-demand jobs in the market. Data job aspirants should target these roles 
first, before considering other paths, as they offer the highest 
potential to land a job.
2. Python, SQL, AWS, Azure, and Tableau are the top 5 in-demand 
skills, and aspiring data professionals should be proficient in these, 
as they offer the highest potential for landing a job easily. 
Higher-paying but less commonly required skills should be learned 
later in one's career, once the foundational, high-demand skills are 
in place.
3. One should seek yearly-salary jobs instead of hourly-paid jobs, since 
hourly-paid jobs come out lower even when converted to a yearly figure 
using the standard measure (hourly rate × 2,080 working hours per year).

## Conclusion

This project strengthened my ability to translate raw job market data 
into a clear, actionable Power BI dashboard , surfacing which skills, 
roles, and salary structures matter most for anyone entering the data 
space. For newcomers, the findings point to a practical starting path: 
prioritize the most in-demand roles (Data Engineer, Data Analyst, Data 
Scientist), build proficiency in the top in-demand skills first, and 
favor yearly-salary positions over hourly ones for stronger long-term 
earning potential.

