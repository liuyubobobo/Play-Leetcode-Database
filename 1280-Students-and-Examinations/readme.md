```
Source : https://leetcode.com/problems/students-and-examinations/
Author : liuyubobobo
Time   : 2022-04-28
```

---

## Nested Query

```MySQL
SELECT Students.student_id, Students.student_name, Subjects.subject_name, 
    (SELECT COUNT(*) FROM Examinations 
     WHERE Students.student_id = Examinations.student_id AND Subjects.subject_name = Examinations.subject_name) AS attended_exams
FROM (Students, Subjects)
ORDER BY Students.student_id, Subjects.subject_name
```

<br/>

## Using JOIN

```MySQL
SELECT Students.student_id, Students.student_name, Subjects.subject_name, 
COUNT(Examinations.subject_name) AS attended_exams

FROM (Students, Subjects) LEFT JOIN Examinations
ON Students.student_id = Examinations.student_id AND Subjects.subject_name = Examinations.subject_name

GROUP BY Students.student_id, Subjects.subject_name
ORDER BY Students.student_id, Subjects.subject_name
```