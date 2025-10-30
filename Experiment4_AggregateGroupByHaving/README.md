# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
<img width="1237" height="511" alt="image" src="https://github.com/user-attachments/assets/e22f5051-8eb6-4f57-9ac3-a05f6340d61d" />

```
SELECT strftime('%Y-%m', Date) AS Month, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY strftime('%Y-%m', Date)
ORDER BY Month;
```

**Output:**
<img width="1236" height="502" alt="image" src="https://github.com/user-attachments/assets/4501e0e9-b127-4057-a2e1-d62d16709ca2" />


**Question 2**
<img width="1235" height="635" alt="image" src="https://github.com/user-attachments/assets/caa741ac-b6a3-4089-822b-f97b0ce8097a" />


```
SELECT InsuranceCompany, COUNT(DISTINCT PatientID) AS TotalPatients
FROM Insurance
GROUP BY InsuranceCompany
ORDER BY InsuranceCompany;
```

**Output:**

<img width="1222" height="733" alt="image" src="https://github.com/user-attachments/assets/00cc3cb2-3e90-44c4-9d80-4562b653acaa" />


**Question 3**
<img width="1231" height="598" alt="image" src="https://github.com/user-attachments/assets/b292a911-adf4-4042-ac74-053e41568fd1" />


```
SELECT Specialty, COUNT(DoctorID) AS TotalDoctors
FROM Doctors 
GROUP BY Specialty;
```

**Output:**
<img width="1240" height="726" alt="image" src="https://github.com/user-attachments/assets/8c942df5-f43d-4ce8-b1b3-20ff386270d8" />




**Question 4**
<img width="1253" height="527" alt="image" src="https://github.com/user-attachments/assets/b1867323-3c38-4f7c-bde5-9fb5f46ff0f7" />


```
SELECT name AS Employee_Name, Age AS Age
FROM employee
ORDER BY Age ASC
LIMIT 1;
```

**Output:**

<img width="1233" height="368" alt="image" src="https://github.com/user-attachments/assets/dd78bdee-c868-45ee-b59f-fec89c8d655f" />


**Question 5**
<img width="1233" height="516" alt="image" src="https://github.com/user-attachments/assets/5afdcaea-9248-4d8a-a6ce-e5c194ffc4f8" />

```
SELECT COUNT()
FROM (SELECT DISTINCT age FROM employee) AS UniqueAges;
```

**Output:**

<img width="1252" height="447" alt="image" src="https://github.com/user-attachments/assets/594e0510-46a6-435a-a619-17d481b5e0c7" />


**Question 6**
<img width="1241" height="499" alt="image" src="https://github.com/user-attachments/assets/286f3bfe-be45-4de5-8a61-20afda72d032" />


```
SELECT name, email,LENGTH(email) AS min_email_length
FROM customer
ORDER BY LENGTH(email) ASC
LIMIT 1;
```

**Output:**


<img width="1241" height="340" alt="image" src="https://github.com/user-attachments/assets/c6409471-5910-4e28-a39c-383c62d3fa4f" />


**Question 7**

<img width="1231" height="543" alt="image" src="https://github.com/user-attachments/assets/ad1a265f-5a71-405a-bbfe-0f57e07cb890" />

```
SELECT MAX(price) - MIN(price) AS price_diff
FROM fruits;
```

**Output:**


<img width="1231" height="414" alt="image" src="https://github.com/user-attachments/assets/323af9c3-bf87-49d6-8572-03ee783f9760" />

**Question 8**

<img width="1232" height="497" alt="image" src="https://github.com/user-attachments/assets/09d9dd81-616a-45a6-86e5-6d3ff0881e23" />

```
SELECT category_id, AVG(Price) 
FROM products
GROUP BY category_id
HAVING AVG(Price) BETWEEN 10 AND 15;
```

**Output:**


<img width="1291" height="459" alt="image" src="https://github.com/user-attachments/assets/3c5178f8-412e-4974-ac23-045fbdb3a977" />


**Question 9**

<img width="1250" height="534" alt="image" src="https://github.com/user-attachments/assets/3eecc425-ce12-4deb-99d9-975b3dc16754" />


```
SELECT age, MIN(income) 
FROM employee
GROUP BY age
HAVING MIN(income) < 400000;
```

**Output:**


<img width="1230" height="452" alt="image" src="https://github.com/user-attachments/assets/27f10f2f-87a0-4786-9434-d58f2410d17e" />


**Question 10**

<img width="1222" height="487" alt="image" src="https://github.com/user-attachments/assets/bbd29eac-953a-445e-b646-72d71f66a737" />


```
SELECT category_id, Min(price) as Price
FROM products
GROUP BY category_id
HAVING MIN(price) < 10;
```

**Output:**

<img width="1229" height="411" alt="image" src="https://github.com/user-attachments/assets/3efa9b95-8d82-4173-bae5-fcb330c1197d" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
