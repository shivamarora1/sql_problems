#  Most Valuable Customer

Anika has eCom website and she is looking for the most valuable customer. All you need to do is help Anika find the customer and number of orders detail of the most valuable customer who has placed the highest orders.

There's only one most valuable customer

Schema:
Table: orders

|Field|Type|
|---|---|
|id|int|
|number|int|
|date|text|
|status|text|
|customerID|text|

Note: number column denotes the order Id.

Explanation
Sample orders table

|id|number|date|status|customerID|
|---|---|---|---|---|
|1|10268|2007-06-30|Delivered|3|
|2|10269|2007-06-30|Shipped|1|
|3|15477|2015-02-14|Shipped|3|

Output

|customerID|no_of_orders|
|---|---|
|3|2|

## Solution
```
SELECT customerID,COUNT(number) AS 'number_of_orders' 
FROM orders 
GROUP BY customerID 
ORDER BY number_of_orders DESC 
LIMIT 1
```
