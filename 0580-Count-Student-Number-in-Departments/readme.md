```
Source : https://leetcode.com/problems/count-student-number-in-departments/
Author : liuyubobobo
Time   : 2022-04-30
```

<br/>

## Using LEFT JOIN

```MySQL
SELECT Department.dept_name, COUNT(Student.student_id) AS student_number
FROM Department LEFT JOIN Student ON Department.dept_id = Student.dept_id
GROUP BY Department.dept_id
ORDER BY student_number DESC, dept_name ASC
```
