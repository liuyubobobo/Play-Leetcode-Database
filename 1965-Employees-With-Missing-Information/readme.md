```
Source : https://leetcode.com/problems/employees-with-missing-information/
Author : liuyubobobo
Time   : 2022-04-17
```

<br/>

## Using UNION

```MySQL
SELECT employee_id 
FROM Employees
WHERE employee_id NOT IN (SELECT employee_id FROM Salaries)

UNION

SELECT employee_id 
FROM Salaries
WHERE employee_id NOT IN (SELECT employee_id FROM Employees)

ORDER BY employee_id
```
