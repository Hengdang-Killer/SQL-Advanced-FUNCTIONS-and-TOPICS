# `DateDIFF()` : To find difference between two dates by the number of days

## Use :-
Calculates the difference in days between two dates.

## Example Usage :-
`DateDIFF(W2.recordDate, W1.recordDate).`

## Example Full SQL Query Code :-
```sql
SELECT W2.id FROM Weather W1, Weather W2 WHERE DateDIFF(W2.recordDate, W1.recordDate) = 1 AND W2.temperature > W1.temperature
```
## Problem Link :- 
https://leetcode.com/problems/rising-temperature/
