## Temporary Table

```MySQL
SELECT

(SELECT DISTINCT salary 

 FROM Employee ORDER BY salary DESC

 LIMIT 1 OFFSET 1) AS SecondHighestSalary;
```

Using ``LIMIT 1 OFFSET 1`` won't return ``NULL`` if there's no solution

<br/>

## Using IFNULL

```MySQL
SELECT

IFNULL((SELECT DISTINCT salary 

        FROM Employee ORDER BY salary DESC

        LIMIT 1 OFFSET 1), NULL) 
        
AS SecondHighestSalary;
```

<br/>

## Using MAX

```MySQL
SELECT MAX(salary) AS SecondHighestSalary

FROM Employee 
 
WHERE salary != (SELECT MAX(salary) FROM Employee);
```