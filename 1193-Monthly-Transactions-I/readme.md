```
Source : https://leetcode.com/problems/monthly-transactions-i/
Author : liuyubobobo
Time   : 2022-04-25
```

## Using CASE

```MySQL
SELECT DATE_FORMAT(trans_date, "%Y-%m") AS month, 
       country, 
       COUNT(id) AS trans_count, 
       SUM(CASE WHEN state = 'approved' THEN 1 ELSE 0 END) AS approved_count,
       SUM(amount) AS trans_total_amount, 
       SUM(CASE WHEN state = 'approved' THEN amount ELSE 0 END) AS approved_total_amount

FROM Transactions
GROUP BY country, YEAR(trans_date), MONTH(trans_date)
```

More about DATE_FORMAT, see here : [https://www.w3schools.com/sql/func_mysql_date_format.asp](https://www.w3schools.com/sql/func_mysql_date_format.asp)

<br/>

## Using IF

```MySQL
SELECT DATE_FORMAT(trans_date, "%Y-%m") AS month, 
       country, 
       COUNT(id) AS trans_count, 
       SUM(IF(state = 'approved', 1, 0)) AS approved_count,
       SUM(amount) AS trans_total_amount, 
       SUM(IF(state = 'approved', amount, 0)) AS approved_total_amount

FROM Transactions
GROUP BY country, YEAR(trans_date), MONTH(trans_date)
```
