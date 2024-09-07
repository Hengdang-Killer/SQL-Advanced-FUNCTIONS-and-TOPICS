# `ORDER BY`: Sorts the result set in ascending or descending order.

## Use :-
The `ORDER BY` clause is used to sort the result set of a query based on one or more columns. By default, it sorts in ascending order (`ASC`), but you can specify descending order (`DESC`) for any column.

## Syntax :-
```sql
SELECT column_name(s)
FROM table_name
ORDER BY column_name [ASC|DESC], ...;
```

## Example SQL Code :-
```sql
SELECT 
    name, 
    salary
FROM 
    Employees
ORDER BY 
    salary ASC;
```
