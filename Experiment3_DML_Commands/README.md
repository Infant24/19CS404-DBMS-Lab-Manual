# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**

<img width="1228" height="534" alt="image" src="https://github.com/user-attachments/assets/58753662-695f-4c40-930b-4df1c5f05465" />
```
UPDATE suppliers
SET address = '58 Lakeview, Magnolia'
WHERE supplier_id =5;
```

**Output:**
<img width="1247" height="495" alt="image" src="https://github.com/user-attachments/assets/515c7b54-a61a-478c-82c1-e066cfe36753" />

**Question 2**
<img width="1240" height="583" alt="image" src="https://github.com/user-attachments/assets/a7b9b3d8-8e77-413c-82d2-aa0ea803539b" />


```
UPDATE products
SET sell_price = sell_price*1.15
WHERE quantity<50 and supplier_id = 10;
```

**Output:**
<img width="1247" height="580" alt="image" src="https://github.com/user-attachments/assets/3eab0050-2c94-4580-b2df-eea9d7aa3881" />


**Question 3**
<img width="1242" height="343" alt="image" src="https://github.com/user-attachments/assets/b877dbb0-a5f4-4418-8866-16f74e6d954a" />

```
UPDATE products 
SET product_name = 'Premium Bread'
WHERE product_id = 5;
```

**Output:**
<img width="1245" height="527" alt="image" src="https://github.com/user-attachments/assets/1934f328-68b7-401f-94a5-c7dcf52012f3" />

**Question 4**
<img width="1240" height="271" alt="image" src="https://github.com/user-attachments/assets/5f59bd0b-3193-45f1-8e94-11723992b6e4" />

```
UPDATE products
SET availability = availability*2
WHERE product_id = 1;
```

**Output:**
<img width="1248" height="307" alt="image" src="https://github.com/user-attachments/assets/34148677-01f2-408e-84d5-aaead7b0b4a3" />

**Question 5**
<img width="1236" height="554" alt="image" src="https://github.com/user-attachments/assets/991a8347-9436-44f7-91fa-f19d4f0271c7" />

```
<img width="1236" height="554" alt="image" src="https://github.com/user-attachments/assets/140b2b84-6426-4755-b96e-e26041588bf6" />
```

**Output:**
<img width="1247" height="489" alt="image" src="https://github.com/user-attachments/assets/d5e75c4a-cf6f-4d14-a20f-b01e8bd23473" />

**Question 6**
<img width="1243" height="504" alt="image" src="https://github.com/user-attachments/assets/230ba8e1-d3ac-4c88-87b0-0b495aa36c02" />

```
DELETE FROM customer
WHERE CUST_COUNTRY = 'UK' and ( WORKING_AREA = 'LONDON' or GRADE < 3);
```

**Output:**
<img width="1242" height="545" alt="image" src="https://github.com/user-attachments/assets/591249a0-0619-4042-9591-ca5aa11efc37" />

**Question 7**
<img width="1240" height="526" alt="image" src="https://github.com/user-attachments/assets/89e6aecd-5a4d-464d-acb4-1994bd3d5ecc" />


```
DELETE FROM surgeries
WHERE surgery_id = 3;
```

**Output:**

<img width="1235" height="452" alt="image" src="https://github.com/user-attachments/assets/daf42a88-484b-47ea-bea4-ad9607770671" />


**Question 8**
<img width="1249" height="737" alt="image" src="https://github.com/user-attachments/assets/8e1d5e9e-f87b-4628-874c-e17fdce7abeb" />

```
DELETE FROM customer
WHERE grade < 2;
```

**Output:**

<img width="1228" height="579" alt="image" src="https://github.com/user-attachments/assets/4c466df0-784a-4e04-8c4c-7935d6885b5e" />


**Question 9**
<img width="1246" height="558" alt="image" src="https://github.com/user-attachments/assets/c7489807-6bff-4c40-a543-17bb952509bf" />

```
DELETE FROM customer
WHERE (grade > 2 and PAYMENT_AMT < (SELECT AVG(PAYMENT_AMT) FROM Customer))  or OUTSTANDING_AMT > 8000;
```

**Output:**
<img width="1207" height="725" alt="image" src="https://github.com/user-attachments/assets/fea96f0d-a0c6-41ab-8659-a20d6578f11c" />


**Question 10**
<img width="1239" height="942" alt="image" src="https://github.com/user-attachments/assets/a1b6a42c-420f-409b-be15-962cdf31bd0e" />


```
<img width="1239" height="942" alt="image" src="https://github.com/user-attachments/assets/1694a0f5-6e2f-4a83-9951-bc4cee3d5c18" />

```

**Output:**

<img width="1248" height="905" alt="image" src="https://github.com/user-attachments/assets/04e552fe-e007-48c5-8bb5-e9b890a26495" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
