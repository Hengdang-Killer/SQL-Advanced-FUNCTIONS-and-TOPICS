## LAG : To find the previous row

## Use :-
A window function that provides access to a row at a specified physical offset that comes before the current row within a result set.

## Example usage :-
LAG(temperature) OVER (ORDER BY recordDate).

## Example SQL Code :-
SELECT id 

FROM (

    SELECT 

        id, 

        recordDate, 

        temperature, 

        LAG(temperature) OVER (ORDER BY recordDate) AS prev_temperature, 

        LAG(recordDate) OVER (ORDER BY recordDate) AS prev_date

    FROM Weather

) AS subquery

WHERE DateDIFF(recordDate, prev_date) = 1 AND temperature > prev_temperature;

## Problem Link :-
https://leetcode.com/problems/rising-temperature/
