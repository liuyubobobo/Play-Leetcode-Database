```
Source : https://leetcode.com/problems/students-with-invalid-departments/
Author : liuyubobobo
Time   : 2021-12-29
```

<br/>

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

