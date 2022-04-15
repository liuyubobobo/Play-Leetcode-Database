```
Source : https://leetcode.com/problems/find-customer-referee/
Author : liuyubobobo
Time   : 2022-04-14
Updated: 2022-04-15
```

<br/>

## Using OR to deal with NULL

```MySQL
SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS NULL
```

<br/>

## Using IFNULL

```MySQL
SELECT name 
FROM Customer 
WHERE IFNULL(referee_id, -1) != 2
```

<br/>

## Nested Queries

```MySQL
SELECT name 
FROM Customer 
WHERE id NOT IN
(SELECT id FROM Customer WHERE referee_id = 2)
```
