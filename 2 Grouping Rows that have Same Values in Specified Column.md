# `GROUP BY`: Groups rows that have the same values into summary rows.

## Use :-
The `GROUP BY` clause is used to group rows that have the same values in specified columns into aggregated data. It is commonly used with aggregate functions like `COUNT()`, `SUM()`, `AVG()`, `MAX()`, and `MIN()` to perform operations on each group.

## Example Usage :-
`GROUP BY column_name`

## Example Full SQL Query Code:
```sql
SELECT 
    class, 
    COUNT(*) AS num_students
FROM 
    Courses
GROUP BY 
    class
HAVING 
    COUNT(*) >= 5;
```
## Problem Link :-
https://leetcode.com/problems/classes-more-than-5-students/
