```
Source : https://leetcode.com/problems/calculate-special-bonus/
Author : liuyubobobo
Time   : 2022-04-15
```

<br/>

## Using UNION

```MySQL
(
    SELECT employee_id, salary as bonus 
    FROM Employees
    WHERE employee_id % 2 = 1 AND name NOT LIKE 'M%'
)
UNION
(
    SELECT employee_id, 0 as bonus 
    FROM Employees
    WHERE employee_id % 2 = 0 OR name LIKE 'M%'
)
ORDER BY employee_id
```

<br/>

## Using IF

```MySQL
SELECT employee_id, 
IF(employee_id % 2 = 1 AND name NOT LIKE 'M%' , salary, 0) as bonus 
FROM Employees
ORDER BY employee_id
```

<br/>

## Using CASE

```MySQL
SELECT employee_id, 
CASE 
    WHEN employee_id % 2 = 1 AND name NOT LIKE 'M%' THEN salary
    ELSE 0
END as bonus 
FROM Employees
ORDER BY employee_id
```

