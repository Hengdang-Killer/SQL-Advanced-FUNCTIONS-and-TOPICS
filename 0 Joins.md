# SQL Joins Explained

Joins are used to combine rows from two or more tables based on a related column between them. Understanding the different types of joins is crucial for querying relational databases effectively.

## Types of Joins in SQL :-

### 1. **INNER JOIN**

**Description :-**
- Returns only the rows that have matching values in both tables.

**Syntax :-**
```sql
SELECT
  column_names
FROM
  table1
  INNER JOIN table2 ON table1.column = table2.column;
```

**Example :-**
```sql
SELECT
  Employees.name, Departments.department_name
FROM
  Employees
  INNER JOIN Departments ON Employees.department_id = Departments.department_id;
```

**Output :-**
- This query returns only employees who are associated with a department.

### 2. **LEFT JOIN (LEFT OUTER JOIN)**

**Description :-**
- Returns all rows from the left table, and the matched rows from the right table. If no match is found, NULLs are returned for columns from the right table.

**Syntax :-**
```sql
SELECT
  column_names
FROM
  table1
  LEFT JOIN table2 ON table1.column = table2.column;
```

**Example :-**
```sql
SELECT
  Employees.name, Departments.department_name
FROM
  Employees
  LEFT JOIN Departments ON Employees.department_id = Departments.department_id;
```

***Output :-***
- This query returns all employees, including those who are not assigned to any department (departments will show as NULL).

### 3. RIGHT JOIN (RIGHT OUTER JOIN)

**Description :-**
- Returns all rows from the right table, and the matched rows from the left table. If no match is found, NULLs are returned for columns from the left table.
 
**Syntax :-**
```sql
SELECT
  column_names
FROM
  table1
  RIGHT JOIN table2 ON table1.column = table2.column;
```

**Example :-**
```sql
SELECT
  Employees.name, Departments.department_name
FROM
  Employees
  RIGHT JOIN Departments ON Employees.department_id = Departments.department_id;
```

**Output :-**
- This query returns all departments, including those that have no employees (employees will show as NULL).

### 4. FULL JOIN (FULL OUTER JOIN)

**Description :-**
- Returns all rows when there is a match in either the left or right table records. If there is no match, NULLs are returned for columns from the table without a match.

**Syntax :-**
```sql
SELECT
  column_names
FROM
  table1
  FULL JOIN table2 ON table1.column = table2.column;
```

**Example :-**
```sql
SELECT
  Employees.name, Departments.department_name
FROM
  Employees
  FULL JOIN Departments ON Employees.department_id = Departments.department_id;
```

**Output :-**
- This query returns all employees and all departments, matching where possible. Where there is no match, NULLs are filled in for unmatched columns.

### 5. CROSS JOIN

**Description :-**
- Returns the Cartesian product of the two tables. It combines each row of the first table with all rows of the second table.

**Syntax :-**
```sql
SELECT
  column_names
FROM
  table1
  CROSS JOIN table2;
```

**Example :-**
```sql
SELECT
  Employees.name, Departments.department_name
FROM
  Employees
  CROSS JOIN Departments;
```

**Output :-**
- This query returns all possible combinations of employees and departments.

### 6. SELF JOIN

**Description :-**
- A join where a table is joined with itself. It's useful for hierarchical data or comparing rows within the same table.

**Syntax :-**
```sql
SELECT
  a.column_name, b.column_name
FROM
  table a
  JOIN table b ON a.common_column = b.common_column;
````

**Example :-**
```sql
SELECT
  e1.name AS Employee, e2.name AS Manager
FROM
  Employees e1
  JOIN Employees e2 ON e1.manager_id = e2.employee_id;
```

**Output :-** 
- This query returns a list of employees and their managers by joining the Employees table with itself.

## Summary :- 

1. `INNER JOIN` : Matches rows in both tables.

2. `LEFT JOIN` : Matches all rows from the left table; unmatched rows from the right are NULL.

3. `RIGHT JOIN` : Matches all rows from the right table; unmatched rows from the left are NULL.

4. `FULL JOIN` : Matches all rows from both tables; unmatched rows from both sides are NULL.

5. `CROSS JOIN` : Returns all combinations of rows from the two tables.

6. `SELF JOIN` : Joins a table to itself for hierarchical or comparative queries.

These join types provide a powerful way to combine data across related tables, allowing for complex and meaningful queries in SQL.
