# `ROW_NUMBER()`: To assign a unique sequential integer to rows within a partition of a result set, starting at 1 for the first row in each partition.

## Use:
Generates a unique row number for each row within a partition of a result set. The numbering is reset for each partition.

## Example Usage:
`ROW_NUMBER() OVER (PARTITION BY column_name ORDER BY another_column_name)`

## Example Full SQL Query Code:
```sql
DELETE FROM Person 
WHERE id IN (
    SELECT a.id
    FROM (
        SELECT id, email, ROW_NUMBER() OVER (PARTITION BY email ORDER BY id) AS rn
        FROM Person
    ) a 
    WHERE a.rn > 1
);
