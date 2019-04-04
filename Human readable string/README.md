#  Human readable string

Sheryl Sandberg, COO of Facebook is doing research and trying to display appealing human readable user details to end users.

For an experiment, she is looking for a set of users whose middle name starts from K. and Sheryl also wants to strip output of middle name to just initial. According to Sheryl, human readable format should be fName M lName is from xLocation area.

Table: users

|Field|Type|
|id|int|
|firstName|text|
|middleName	text|
|lastName|text|
|location|text|

## Solution
```
SELECT CONCAT(firstName,' ',LEFT(middleName,1),'. ',lastName,' is from ',location,' area.') AS '' 
FROM users 
WHERE middleName 
LIKE 'K%'
```
