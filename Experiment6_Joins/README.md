# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1297" height="770" alt="image" src="https://github.com/user-attachments/assets/147c8a77-6bbe-4093-b0e0-c3e4caa353fe" />
<img width="1288" height="742" alt="image" src="https://github.com/user-attachments/assets/29f194cb-d463-4e4d-8863-e3c01d01c63f" />

```sql
SELECT
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM
    orders o
INNER JOIN
    customer c ON o.customer_id = c.customer_id
INNER JOIN
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1251" height="456" alt="image" src="https://github.com/user-attachments/assets/cf7b73e3-f75d-4366-a260-92560da426c4" />
<img width="1261" height="799" alt="image" src="https://github.com/user-attachments/assets/1d45f2d5-20ca-4ed3-8f2f-65113cee83f4" />

**Question 2**
---
<img width="1296" height="957" alt="image" src="https://github.com/user-attachments/assets/e6252f28-b1d9-4044-914c-f18ac8235da4" />

```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM
    customer c
INNER JOIN
    salesman s ON c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1287" height="925" alt="image" src="https://github.com/user-attachments/assets/fa84e780-03f9-4fe8-98fb-c0918abadbe0" />

**Question 3**

<img width="1293" height="768" alt="image" src="https://github.com/user-attachments/assets/ba6f00b1-739e-47c8-a268-7f89cb5f7e61" />

```sql
SELECT
    n.*,
    d.department_name
FROM
    nurses n
INNER JOIN
    departments d ON n.department_id = d.department_id;
```

**Output:**

<img width="1292" height="586" alt="image" src="https://github.com/user-attachments/assets/18cff1b7-00ed-4b35-9997-4cbc6b8ea83c" />

**Question 4**

<img width="1308" height="760" alt="image" src="https://github.com/user-attachments/assets/5f169a72-2c8b-438a-b88a-336c78894e9d" />
<img width="1297" height="472" alt="image" src="https://github.com/user-attachments/assets/c6bb9959-b10f-43b2-9f02-91666587fa9f" />

```sql
SELECT
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id = o.customer_id
ORDER BY
    o.ord_date ASC;
```

**Output:**

<img width="1265" height="460" alt="image" src="https://github.com/user-attachments/assets/9d4aaa14-4962-4a68-a582-a8396d408e37" />
<img width="1266" height="805" alt="image" src="https://github.com/user-attachments/assets/996bb88e-8f4c-40df-a2cc-a9bcd49d6155" />

**Question 5**
---
<img width="1302" height="916" alt="image" src="https://github.com/user-attachments/assets/c00fbf09-23a3-4dcb-9f90-adb9f590fb9d" />

```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.city AS "city",
    s.commission
FROM
    customer c
INNER JOIN
    salesman s ON c.salesman_id = s.salesman_id
WHERE
    c.city <> s.city
    AND s.commission > 0.12;
```

**Output:**

<img width="1298" height="665" alt="image" src="https://github.com/user-attachments/assets/90d4912f-1f03-4a49-ad79-616977b499f5" />

**Question 6**
---
<img width="1290" height="525" alt="image" src="https://github.com/user-attachments/assets/c40cf95a-b716-42e1-993c-ddd272396dd6" />

```sql
SELECT
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id = o.customer_id
WHERE
    o.purch_amt > 1000;
```

**Output:**

<img width="1301" height="769" alt="image" src="https://github.com/user-attachments/assets/52532f0c-2afc-4c95-a03e-7b4175e70487" />

**Question 7**
---
<img width="1295" height="470" alt="image" src="https://github.com/user-attachments/assets/789f7145-c4e7-403a-8e09-b2fc8193ec61" />


```sql
SELECT
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id = o.customer_id
WHERE
    c.city = 'London';
```

**Output:**

<img width="1302" height="542" alt="image" src="https://github.com/user-attachments/assets/6c6b5d57-3fe3-424b-b6e8-e3758236735a" />

**Question 8**
---
<img width="1299" height="846" alt="image" src="https://github.com/user-attachments/assets/8ca39dda-dc2e-403a-b047-f8b87142d5fe" />

```sql
SELECT
    p.admission_date,
    s.surgery_date
FROM
    patients p
INNER JOIN
    surgeries s ON p.patient_id = s.patient_id;
```

**Output:**

<img width="1300" height="704" alt="image" src="https://github.com/user-attachments/assets/3ff032dd-5672-452d-988e-fb2ee56ad14e" />


**Question 9**
---
<img width="1312" height="703" alt="image" src="https://github.com/user-attachments/assets/06d95b85-3572-4118-ad14-0b95de9c5094" />



```sql
SELECT
    t.*
FROM
    test_results t
INNER JOIN
    patients p ON t.patient_id = p.patient_id
WHERE
    p.first_name = 'Alice';
```

**Output:**

<img width="1291" height="958" alt="image" src="https://github.com/user-attachments/assets/52d50e10-405e-4508-b39d-2cf9869289f2" />

**Question 10**
---
  <img width="1291" height="958" alt="image" src="https://github.com/user-attachments/assets/f696233b-b4a0-48e1-b803-a2646e6f2e04" />


```sql
SELECT
    c.cust_name,
    c.city AS "city",
    c.grade,
    s.name AS "Salesman",
    s.city AS "city"
FROM
    customer c
INNER JOIN
    salesman s ON c.salesman_id = s.salesman_id
ORDER BY
    c.customer_id ASC;

```

**Output:**

<img width="1293" height="926" alt="image" src="https://github.com/user-attachments/assets/cc9b49dd-39d0-4942-b0cb-1dbf6322322f" />

## RESULT:

Thus, the SQL queries to implement different types of joins have been executed successfully.
