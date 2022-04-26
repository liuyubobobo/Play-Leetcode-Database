```
Source : https://leetcode.com/problems/biggest-single-number/
Author : liuyubobobo
Time   : 2022-04-26
```

<br/>

## Using Derived Table
 
```MySQL
SELECT MAX(t.num) as num FROM
(
    SELECT num, COUNT(*) as cnt FROM MyNumbers GROUP BY num
) t
WHERE t.cnt = 1
```

<br/>

## Using Derived Table 2

```MySQL
SELECT MAX(t.num) as num FROM
(
    SELECT num FROM MyNumbers GROUP BY num HAVING COUNT(num) = 1
) t
```

<br/>

## Using GROUP BY

```MySQL
SELECT(
    SELECT num
    FROM MyNumbers
    GROUP BY num
    HAVING COUNT(*) = 1
    ORDER BY num DESC LIMIT 1
) AS num;
```