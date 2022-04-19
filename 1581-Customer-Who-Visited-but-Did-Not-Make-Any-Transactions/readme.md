```
Source : https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/
Author : liuyubobobo
Time   : 2022-04-18
```

<br/>

## Using LEFT JOIN

```MySQL
SELECT customer_id, COUNT(*) AS count_no_trans
FROM Visits LEFT JOIN Transactions
ON Visits.visit_id = Transactions.visit_id
WHERE Transactions.visit_id IS NULL
GROUP BY customer_id
```
