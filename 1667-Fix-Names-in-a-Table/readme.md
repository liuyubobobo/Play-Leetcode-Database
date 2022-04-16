```
Source : https://leetcode.com/problems/fix-names-in-a-table/
Author : liuyubobobo
Time   : 2022-04-16
```

<br/>

## Using UPPER, LOWER, SUBSTRING, CONCAT

```MySQL
SELECT 
user_id, 
CONCAT(UPPER(SUBSTRING(name, 1, 1)), LOWER(SUBSTRING(name, 2, LENGTH(name) - 1))) AS name
FROM Users
ORDER BY user_id
```

In MYSQL, The start index of a string is 1 
(See SUBSTRING usage for details)

