```
Source : https://leetcode.com/problems/evaluate-boolean-expression/
Author : liuyubobobo
Time   : 2022-04-27
```

<br/>

## JOIN Three Tables

```MySQL
SELECT e.left_operand, e.operator, e.right_operand,
  (CASE WHEN e.operator = '>' AND v1.value > v2.value THEN 'true'
        WHEN e.operator = '=' AND v1.value = v2.value THEN 'true' 
        WHEN e.operator = '<' AND v1.value < v2.value THEN 'true'
        ELSE 'false'
   END) AS value
FROM Expressions AS e
JOIN Variables AS v1 ON e.left_operand = v1.name
JOIN Variables AS v2 ON e.right_operand = v2.name
```