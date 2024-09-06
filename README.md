# HR Data Analysis
## Table of Content 
- [project overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning/ Preparation](#data-cleaning/-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Result/Findings](#results/findings)
- [Limitations](#limitation)


### Project Overview
This data analysis project analyzes the demographics, employment patterns, and turnover rates within the company. It explores the gender, race/ethnicity, and age breakdowns of employees, as well as their distribution across different departments, job titles, and locations. The Key focus areas includes the comparison of employees working at headquarters versus remote locations, the tenure of terminated employees, and the overall employee count changes over time. 

### Data Source
The data for this project was sourced from a "Human Resources CSV file", containing detailed information on employee demographics, job roles, departments, hire and termination dates, and other relevant employment details.

### Tools 

- Excel - Data Cleaning 
- SQL Server - Data Analysis
- Power BI - Creating reports

### Data Cleaning/ Preparation 

In the initial data preparation phase, we performed the following tasks;
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and formatting

### Exploratory Data Analysis 

The EDA involved exploring the human resources data to answer key questions such as;
-  What is the gender breakdown of employees in the company?
-  What is the race/ethnicity breakdown of employees in the company?
-  What is the age distribution of employees in the company?
-  How many employees work at headquarters versus remote locations?
-  What is the average length of employment for employees who have been terminated?
-  How does the gender distribution vary across departments and job titles?
-  What is the distribution of job titles across the company?
-  Which department has the highest turnover rate?
-  What is the distribution of employees across locations by state?
-  How has the company's employee count changed over time based on hire and term dates?
-  What is the tenure distribution for each department?


### Data Analysis 
Includes some interesting codes and features worked with 

```Sql
UPDATE hr
SET hire_date = CASE
	WHEN hire_date LIKE '%/%' THEN date_format(str_to_date(hire_date, '%m/%d/%Y'), '%Y-%m-%d')
    WHEN hire_date LIKE '%-%' THEN date_format(str_to_date(hire_date, '%m-%d-%Y'), '%Y-%m-%d')
    ELSE NULL
END;
```

### Result/Findings 
The Analysis results are summarized as follows; 

1. There are more male employees
2. White race is the most dominant while Native Hawaiian and American Indian are the least dominant.
3. The youngest employee is 20 years old and the oldest is 57 years old
4. 5 age groups were created (18-24, 25-34, 35-44, 45-54, 55-64). A large number of employees were between 25-34 followed by 35-44 while the smallest group was 55-64.
5. A large number of employees work at the headquarters versus remotely.
6. The average length of employment for terminated employees is around 7 years.
7. The gender distribution across departments is fairly balanced but there are generally more male than female employees.
8. The Marketing department has the highest turnover rate followed by Training. The least turn over rate are in the Research and development, Support and Legal departments.
9. A large number of employees come from the state of Ohio.
10. The net change in employees has increased over the years.
11. The average tenure for each department is about 8 years with Legal and Auditing having the highest and Services, Sales and Marketing having the lowest.

### Limitations 
- Some records had negative ages and these were excluded during querying(967 records). Ages used were 18 years and above.
- Some termdates were far into the future and were not included in the analysis(1599 records). The only term dates used were those less than or equal to the current date.



