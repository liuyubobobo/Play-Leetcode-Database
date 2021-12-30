```
Source : https://leetcode.com/problems/combine-two-tables/
Author : liuyubobobo
Time   : 2021-12-29
```

## Using LEFT JOIN

```MySQL
SELECT firstName, lastName, city, state 

FROM Person LEFT JOIN Address

ON Person.personId = Address.personId;
```