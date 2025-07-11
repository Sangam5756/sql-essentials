| Column | Type    |
| ------ | ------- |
| A      | INTEGER |
| B      | INTEGER |
| C      | INTEGER |

**Q1. Write a query that identifies the type of each record in the TRIANGLES table based on its side lengths A, B, and C.**

```sql
SELECT 
  CASE
    WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
    WHEN A = B AND B = C THEN 'Equilateral'
    WHEN A = B OR B = C OR A = C THEN 'Isosceles'
    ELSE 'Scalene'
  END AS TriangleType
FROM TRIANGLES;
```

