# `COALESCE()` : Returns the first non-NULL expression among its arguments.

## Use :-
The `COALESCE()` function is used to handle `NULL` values by returning the first non-NULL value from a list of expressions. It is useful for replacing `NULL` values with a default value.

## Example Usage :-
`COALESCE(expression1, expression2, ..., default_value)`

## Example Full SQL Query Code :-
```sql
SELECT 
    cs.name
FROM 
    Customer cs
WHERE 
    COALESCE(cs.referee_id, 0) != 2;SCE(cs.referee_id, 0) != 2;
```
## Problem Link :-
https://leetcode.com/problems/customer-placing-the-largest-number-of-orders/
