```
Source : https://leetcode.com/problems/find-customer-referee/
Author : liuyubobobo
Time   : 2022-04-14
```

```MySQL
SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS NULL
```