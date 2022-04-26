```
Source : https://leetcode.com/problems/highest-grade-for-each-student/
Author : liuyubobobo
Time   : 2022-04-26
```

<br/>

## Using JOIN

```MySQL
SELECT Enrollments.student_id, MIN(Enrollments.course_id) AS course_id, t.max_grade AS grade 

FROM

Enrollments JOIN
(
SELECT student_id, MAX(grade) AS max_grade
FROM Enrollments
GROUP BY student_id
) t
ON Enrollments.student_id = t.student_id AND Enrollments.grade = t.max_grade

GROUP BY Enrollments.student_id

ORDER BY student_id ASC
```

<br/>

## Using Nested Query, check two field in the query

```MySQL
SELECT student_id, MIN(course_id) AS course_id, grade
FROM Enrollments 
WHERE (student_id, grade) IN
(
    SELECT student_id, MAX(grade) AS grade
    FROM Enrollments
    GROUP BY student_id
)
GROUP BY student_id
ORDER BY student_id ASC
```