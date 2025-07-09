### `STUDENTS` Table

| Column | Type    |
| ------ | ------- |
| ID     | INT     |
| NAME   | VARCHAR |
| MARKS  | INT     |

**Q1. Query the Name of any student in STUDENTS who scored higher than Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.**

```sql
SELECT NAME
FROM STUDENTS
WHERE MARKS > 75 ORDER BY RIGHT(NAME,3),ID;
```

### `EMPLOYEE` Table

| Column Name | Data Type |
| ----------- | --------- |
| employee_id | INTEGER   |
| name        | STRING    |
| salary      | INTEGER   |
| months      | INTEGER   |
| department  | STRING    |

**Q2. Write a query that prints a list of employee names (i.e., the name attribute) from the Employee table in alphabetical order.**

```sql
SELECT name
FROM Employee
ORDER BY name;
```

**Q3.Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than 2000 per month who have been employees for less than  months. Sort your result by ascending employee_id**
```sql
SELECT NAME FROM Employee
WHERE SALARY > 2000 
AND
months < 10
ORDER BY employee_id;
```