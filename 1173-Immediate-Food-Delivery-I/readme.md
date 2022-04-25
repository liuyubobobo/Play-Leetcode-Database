```
Source : https://leetcode.com/problems/immediate-food-delivery-i/
Author : liuyubobobo
Time   : 2022-04-25
```

---

## Using Nested Query

```MySQL
SELECT 
ROUND(
    (SELECT COUNT(*) FROM Delivery WHERE order_date = customer_pref_delivery_date) / 
    (SELECT COUNT(*) FROM Delivery) * 100.0, 2) AS immediate_percentage
FROM Delivery LIMIT 1
```

<br/>

## Using SUM for bool result (NOT COUNT)

```MySQL
SELECT ROUND(SUM(order_date = customer_pref_delivery_date) * 100.0 / COUNT(delivery_id), 2) AS immediate_percentage
FROM Delivery
```

<br/>

## Using AVG

```MySQL
SELECT ROUND(AVG(order_date = customer_pref_delivery_date) * 100.0, 2) AS immediate_percentage
FROM Delivery
```

