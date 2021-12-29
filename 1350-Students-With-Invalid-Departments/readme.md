## Using Nested Query

```MySQL
SELECT id, name FROM Students
 
WHERE department_id NOT IN 

(SELECT id FROM Departments);
```

<br/>

## Using JOIN

```MySQL
SELECT Students.id, Students.name

FROM Students LEFT JOIN Departments

ON Students.department_id = Departments.id 

WHERE Departments.name IS NULL;
```
