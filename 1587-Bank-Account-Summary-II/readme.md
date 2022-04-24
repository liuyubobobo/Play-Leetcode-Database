```
Source : https://leetcode.com/problems/bank-account-summary-ii/
Author : liuyubobobo
Time   : 2022-05-23
```

<br/>

## Using JOIN

```MySQL
SELECT Users.name AS name, SUM(amount) AS balance 
FROM Users JOIN Transactions
ON Users.account = Transactions.account
GROUP BY Users.account
HAVING SUM(amount) >= 10000
```
