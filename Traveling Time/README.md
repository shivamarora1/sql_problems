#  Travelling Time
Sreeram is into Analytics at makeurtrip.com. One day he wanted to find out the total number of days travelled by active travellers on the platform.

But the data he encountered has negative travel times. He would wish to ignore negative travel time and wants total days of travelled by active travellers served by his application.

Find number of days that is the sum of all the positive travel days done by active users.

Schema
Table: travel

Field	Type
|id|int|
|tripStart|date|
|tripEnd|date|
|active|int|

Note
If tripStart is 2016-06-15 and tripEnd is 2016-06-17
the total travel days would be considered as 2.

-

Note: If active is 1, then the user is an active user, otherwise not.

Explanation
Sample travels Table

|id|tripStart|tripEnd|active
|19|2016-06-15|2016-06-21|1
|20|2016-06-14|2016-06-30|0
|21|2016-06-14|2016-06-16|0
|22|2016-06-15|2016-06-19|1

Output

|travelling_days|
|10|

## Solution
```
SELECT SUM(datediff(tripEnd, tripStart)) 
FROM travel 
WHERE active=1
```
