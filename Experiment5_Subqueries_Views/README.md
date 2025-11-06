# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--

<img width="1302" height="774" alt="image" src="https://github.com/user-attachments/assets/e60fde5f-6506-4279-8b71-a9d918d98c0c" />

```
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM orders
WHERE salesman_id = (
    SELECT salesman_id
    FROM salesman
    WHERE name = 'Paul Adam'
);
```

**Output:**

<img width="1282" height="407" alt="image" src="https://github.com/user-attachments/assets/507356b6-d13c-4d7d-91fd-e2faf2db2e5a" />

**Question 2**
---
<img width="1297" height="675" alt="image" src="https://github.com/user-attachments/assets/d87df428-3d6d-44f1-ad92-c1858339f8bb" />


```
SELECT student_name, grade
FROM
GRADES g
WHERE grade = (SELECT MAX(grade) FROM GRADES WHERE subject = g.subject);
```

**Output:**
<img width="1301" height="487" alt="image" src="https://github.com/user-attachments/assets/d33e2d2a-5c31-43fb-a59d-3f1b62f55590" />

**Question 3**
---
<img width="1299" height="521" alt="image" src="https://github.com/user-attachments/assets/af6027f8-9964-41e2-8204-f64a4c6e781b" />


```
SELECT medication_id, medication_name, dosage
FROM Medications
WHERE dosage = (SELECT MAX(dosage) FROM Medications);
```

**Output:**

<img width="1290" height="452" alt="image" src="https://github.com/user-attachments/assets/80a60b14-c903-4072-943a-9d754d058a92" />

**Question 4**
---
<img width="1300" height="848" alt="image" src="https://github.com/user-attachments/assets/548d5303-b928-4c81-999b-b4000f6b19ba" />


```
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s 
ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';
```

**Output:**

<img width="1292" height="480" alt="image" src="https://github.com/user-attachments/assets/53ddea1f-7e41-4047-a56a-b60c291bc284" />

**Question 5**
---
<img width="1310" height="709" alt="image" src="https://github.com/user-attachments/assets/e2ef516d-3c93-4032-88d3-8bac59492e1a" />


```
SELECT *
FROM Employee
WHERE age < (SELECT AVG(age) FROM Employee WHERE income > 250000);
```

**Output:**
<img width="1292" height="555" alt="image" src="https://github.com/user-attachments/assets/43453014-8eff-431a-abba-53742e2ae3e6" />


**Question 6**
---
<img width="1312" height="657" alt="image" src="https://github.com/user-attachments/assets/b65f6db7-ce48-4627-8cae-c166102bb61c" />


```
SELECT ID, NAME, AGE, ADDRESS, SALARY
FROM CUSTOMERS
WHERE (ADDRESS = 'Delhi') AND (AGE<30);
```

**Output:**

<img width="1297" height="470" alt="image" src="https://github.com/user-attachments/assets/cb9871ee-c7a7-4954-ac60-0571fa34cb0e" />


**Question 7**
---
<img width="1291" height="557" alt="image" src="https://github.com/user-attachments/assets/49d269a6-5186-4084-a894-784fd05a5512" />


```
SELECT name, city
FROM customer
WHERE city IN (SELECT city FROM customer WHERE id IN (3, 7));
```

**Output:**
<img width="1296" height="491" alt="image" src="https://github.com/user-attachments/assets/edebddf8-cb23-45b2-8705-e3f4547d3172" />


**Question 8**
---
<img width="1296" height="567" alt="image" src="https://github.com/user-attachments/assets/1b33f579-f3e4-4445-b083-49049d5a0005" />


```
SELECT name
FROM customer
WHERE phone IN (SELECT phone FROM customer GROUP BY phone HAVING COUNT(phone) = 1);
```

**Output:**

<img width="1303" height="485" alt="image" src="https://github.com/user-attachments/assets/d6e2728f-e290-4f2d-99e5-3a12481ba7b5" />


**Question 9**
---
<img width="1308" height="664" alt="image" src="https://github.com/user-attachments/assets/c53a5ec3-b354-4264-bacf-14fae4a5ec2e" />


```
SELECT student_name, grade
FROM GRADES AS G1
WHERE G1.grade = (SELECT MIN(G2.grade) FROM GRADES AS G2
WHERE G2.subject = G1.subject);
```

**Output:**

<img width="1302" height="479" alt="image" src="https://github.com/user-attachments/assets/d0c93546-a10f-4eeb-a751-13ce08d504b4" />

**Question 10**
---
<img width="1302" height="624" alt="image" src="https://github.com/user-attachments/assets/49868154-6eaf-4fea-a8cd-abf7b6c2b6e5" />


```
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM ORDERS
WHERE ord_date >= '2012-10-10'
```

**Output:**

<img width="1289" height="458" alt="image" src="https://github.com/user-attachments/assets/e6518632-e276-41a0-b740-cfdd09924927" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
