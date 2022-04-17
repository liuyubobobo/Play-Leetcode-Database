```
Source : https://leetcode.com/problems/patients-with-a-condition/
Author : liuyubobobo
Time   : 2022-04-16
```

<br/>

## Using LIKE

```MySQL
SELECT patient_id, patient_name, conditions
FROM Patients
WHERE conditions LIKE 'DIAB1%' OR conditions LIKE '% DIAB1'
```

<br/>

## Using LOCATE

```MySQL
SELECT patient_id, patient_name, conditions
FROM Patients
WHERE LOCATE("DIAB1", conditions) = 1 OR LOCATE(" DIAB1", conditions) != 0
```

<br/>

## Using REGEXP_LIKE

```MySQL
SELECT patient_id, patient_name, conditions
FROM Patients
WHERE REGEXP_LIKE(conditions, "(^D| D)IAB1")
```
