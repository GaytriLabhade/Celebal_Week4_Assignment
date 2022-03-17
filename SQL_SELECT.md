# Celebal_Week4_Assignment
# Basic SELECT in SQL
[1] Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

Ans:

SELECT NAME FROM EMPLOYEE
WHERE SALARY>2000 AND MONTHS<10 ORDER BY EMPLOYEE_ID ASC;

# Aggregation in sql
[2] Query the average population of all cities in CITY where District is California.

Ans:

SELECT avg(POPULATION) FROM CITY
WHERE  DISTRICT = 'California' ;
 
[3] Query the average population for all cities in CITY, rounded down to the nearest integer.

Ans:

SELECT ROUND(avg(POPULATION)) 
FROM CITY;

[4] Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

ANS:
SELECT SUM(POPULATION) FROM CITY
WHERE COUNTRYCODE = 'JPN';

[5] Query the difference between the maximum and minimum populations in CITY.

ANS:
SELECT MAX(POPULATION) - MIN(POPULATION) FROM CITY;

[6] Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.:  average monthly salaries), and round it up to the next integer.

ANS:
select ceil(avg(salary) - avg(replace(salary, '0', ''))) from employees;

[7]We define an employee's total earnings to be their monthly  worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as  space-separated integers.

ANS:
select max(months * salary), count(months * salary) 
from Employee where (months * salary) 
= (select max(months * salary) from Employee);
