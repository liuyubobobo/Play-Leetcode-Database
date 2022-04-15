```
Source : https://leetcode.com/problems/duplicate-emails/
Author : liuyubobobo
Time   : 2021-12-29
```

<br/>

## Self Join

```MySQL
SELECT DISTINCT a.email AS Email

FROM Person AS a, Person AS b

WHERE a.email = b.email AND a.id != b.id;
```

<br/>

## Using GROUP BY

```MySQL
SELECT email AS Email

FROM Person

GROUP BY email 

HAVING COUNT(*) > 1;
```