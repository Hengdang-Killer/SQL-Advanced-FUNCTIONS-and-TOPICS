# DateDIFF() : To find difference between two dates by the number of days

<u>Use</u> : Calculates the difference in days between two dates.

<u>Example Usage</u> : DateDIFF(W2.recordDate, W1.recordDate).

<u>Example Full SQL Query Code</u> : SELECT W2.id FROM Weather W1, Weather W2 WHERE DateDIFF(W2.recordDate, W1.recordDate) = 1 AND W2.temperature > W1.temperature

(<u>Problem Link</u> : https://leetcode.com/problems/rising-temperature/)
