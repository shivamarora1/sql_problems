#  R^2 and Triangles

Rohit wants to build chimney on top of his house, so he consulted his friend Rahul, who happens to be an architect for possible designs. Rahul suggested him to build a triangular-shaped chimney. He provided him with the following data:

Table: triangle
|Field|Type|
|---|---|
|id|int|
|side1|text|
|side2|text|
|side3|text|


where side1, side2, side3 are the sides of a triangle. Rahul has given him more than one type of triangle, with sides of different lengths. Rahul suggested that the best chimney would be which has the maximum area. Your task is to pick the maximum side from each of the columns and calculate the corresponding area of the triangle.

## Solution
```
SET @a=(SELECT MAX(side1) FROM triangle);
SET @b=(SELECT MAX(side2) FROM triangle);
SET @c= (SELECT MAX(side3) FROM triangle);
SET @s = (@a+@b+@c)/2.0;
SET @area = SQRT(@s*(@s-@a)*(@s-@b)*(@s-@c));
SELECT ROUND(@area,2) as 'area';
```
