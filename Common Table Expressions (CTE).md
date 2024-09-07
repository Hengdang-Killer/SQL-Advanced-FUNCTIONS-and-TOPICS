# Common Table Expressions (CTEs)

## What is a CTE ?
A Common Table Expression (CTE) is a temporary result set that you can reference within a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement. CTEs make complex queries easier to read and maintain by breaking them into smaller, modular parts.

## Syntax :-
```sql
WITH cte_name AS (
    SELECT column_name(s)
    FROM table_name
    WHERE condition
)
SELECT column_name(s)
FROM cte_name;
```
 - cte_name: The name of the CTE.

 - The CTE is defined using a WITH clause followed by a subquery.

 - The main query references the CTE like a regular table.

## Example 1 :- Basic CTE Usage
### Problem : Find the average salary for each department from an Employees table.

### SQL Code :-
```sql
WITH DepartmentSalaries AS (
    SELECT 
        department, 
        AVG(salary) AS avg_salary
    FROM 
        Employees
    GROUP BY 
        department
)
SELECT 
    department, 
    avg_salary
FROM 
    DepartmentSalaries;
```
### Explanation :-

- The CTE DepartmentSalaries calculates the average salary for each department.

- The main query selects data from the CTE, providing a clean and readable way to access the aggregated data.

## Example 2 : Using CTE for Recursive Queries
### Problem : Generate a sequence of numbers from 1 to 10.

### SQL Code :-
```sql
WITH RECURSIVE Numbers AS (
    SELECT 1 AS number
    UNION ALL
    SELECT number + 1
    FROM Numbers
    WHERE number < 10
)
SELECT 
    number
FROM 
    Numbers;
```
### Explanation :-

- The WITH RECURSIVE clause allows the CTE to call itself, creating a loop.

- The CTE starts with 1 and increments by 1 until the number reaches 10.

- The result is a sequence of numbers from 1 to 10.

## Example 3 : CTE for Simplifying Complex Queries
### Problem : Find the customer with the highest number of orders from the Orders table.

### SQL Code :-
```sql
WITH OrderCounts AS (
    SELECT 
        customer_number, 
        COUNT(*) AS order_count
    FROM 
        Orders
    GROUP BY 
        customer_number
)
SELECT 
    customer_number
FROM 
    OrderCounts
ORDER BY 
    order_count DESC
LIMIT 1;
```
### Explanation :

- The CTE OrderCounts calculates the number of orders for each customer.

- The main query selects the customer with the highest order count, simplifying what would otherwise be a more complex query.

## Advantages of CTEs :-
1. Readability : Breaks down complex queries into simpler, more manageable parts.

2. Reusability : Allows the same CTE to be referenced multiple times within the main query.

3. Organization : Helps structure and organize queries, making them easier to maintain and debug.

## When to Use CTEs :-
1. When you need to reference the result of a subquery multiple times.
2. For recursive queries like hierarchical or sequence data.
3. To improve the readability of complex queries.

## Notes :-
- CTEs are temporary and only exist during the execution of the query.

- Multiple CTEs can be defined and referenced by separating them with commas.
