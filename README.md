# Module 9 SQL Challenge

## Data Modeling, Table Creation, and Data Analysis

During the course of this project the object was to successfully complete various crucial stages that encompassed data modeling, the creation of tables, and conducting data analysis through pgAdmin 4.
## Data Modeling
I started by designing an Entity Relationship Diagram (ERD) based on the CSV files we had. This ERD illustrates the relationships and attributes of the various tables
See ![Sql_challenge_erd.png](https://github.com/Alex-WRK/module_9_challenge/blob/main/Ressources/Sql_challenge_erd.png)

ERD was created using https://www.quickdatabasediagrams.com/

## Table Creation
Using the ERD, I wrote SQL statements to create tables for each CSV file. These statements include primary keys and, where needed, foreign keys. For example:
CREATE TABLE employees (
    emp_no INT PRIMARY KEY NOT NULL,
    emp_title_id VARCHAR(10),
    birth_date DATE,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    sex CHAR(1),
    hire_date DATE
);

## Data Analysis
Then I crafted SQL queries to analyze the data. These queries enable us to answer questions such as listing employees hired in 1986, employees in the Sales department, employees in both Sales and Development departments, and frequency counts of employee last names.

For instance, to list employees hired in 1986:

SELECT first_name, last_name, TO_CHAR(hire_date, 'YYYY/MM/DD') AS "Hire Date (YYYY/MM/DD)"
FROM employees
WHERE EXTRACT(YEAR FROM hire_date) = 1986;




