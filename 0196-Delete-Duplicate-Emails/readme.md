```
Source : https://leetcode.com/problems/delete-duplicate-emails/
Author : liuyubobobo
Time   : 2022-04-15
```

<br/>

## Using Temporary Table

```MySQL
DELETE FROM Person 
WHERE id NOT IN
(
SELECT id FROM 
    (SELECT MIN(id) as id FROM Person GROUP BY email) need_to_keep_id_table
)
```

In MySQL, you can't modify the same table which you use in the SELECT part, 

see here for details: [https://stackoverflow.com/questions/45494/mysql-error-1093-cant-specify-target-table-for-update-in-from-clause](https://stackoverflow.com/questions/45494/mysql-error-1093-cant-specify-target-table-for-update-in-from-clause)

<br/>

## Using SELF JOIN

```MySQL
DELETE p1
FROM Person p1, Person p2
WHERE p1.email = p2.email AND p1.id > p2.id
```