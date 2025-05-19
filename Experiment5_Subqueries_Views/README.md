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
![image](https://github.com/user-attachments/assets/eb028d1b-b115-43b0-b314-20eecba0319d)


```sql
SELECT 
    g.student_name,
    g.grade
FROM 
    GRADES g
WHERE 
    g.grade = (
        SELECT MAX(g2.grade)
        FROM GRADES g2
        WHERE g2.subject = g.subject
    );

```

**Output:**

![image](https://github.com/user-attachments/assets/ba1a6bd7-4d2a-4fa7-8eeb-a7e6caa1b03e)


**Question 2**
---
![image](https://github.com/user-attachments/assets/efc8e12e-e5dd-4e37-b01c-dec4cd3554c8)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.customer_id,
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s ON o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';

```

**Output:**

![image](https://github.com/user-attachments/assets/c04dbd6b-1c7e-4e0e-a6ed-17e36d1d0afe)


**Question 3**
---
![image](https://github.com/user-attachments/assets/d7872dcf-19bc-4f55-b65d-7ae2eb0ec924)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**

![image](https://github.com/user-attachments/assets/3040e351-5d22-4042-9549-ff314a9f2935)


**Question 4**
---
![image](https://github.com/user-attachments/assets/aa217b20-ba3c-4fba-8699-903bda8b43a6)


```sql
SELECT 
    medication_id AS medic,
    medication_name,
    dosage
FROM 
    Medications
WHERE 
    dosage = (
        SELECT MIN(dosage)
        FROM Medications
    );

```

**Output:**

![image](https://github.com/user-attachments/assets/fc253880-cc7b-4997-a28c-c8185e77f464)


**Question 5**
---
![image](https://github.com/user-attachments/assets/14685b45-3097-40e9-bdda-cc4be738f5c8)


```sql
SELECT 
    student_id,
    student_name,
    subject,
    grade
FROM 
    GRADES g
WHERE 
    grade = (
        SELECT MIN(g2.grade)
        FROM GRADES g2
        WHERE g2.subject = g.subject
    );


```

**Output:**

![image](https://github.com/user-attachments/assets/9fab27e7-6657-4fbb-a830-0da7f479a93f)


**Question 6**
---
![image](https://github.com/user-attachments/assets/e6fd2262-9e7f-4d5a-82b4-a26a3ed57584)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM ORDERS o
JOIN SALESMAN s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/101bab0d-9d69-48fa-a181-7cfdeeabb3b0)


**Question 7**
---
![image](https://github.com/user-attachments/assets/ba4b68e1-6b2a-45e0-a0ee-db823c3c05ec)


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';

```

**Output:**

![image](https://github.com/user-attachments/assets/80d203ce-7255-47a5-ae89-238bbf5861e3)

**Question 8**
---
![image](https://github.com/user-attachments/assets/5af92152-878f-4a94-8263-63dab1e663c4)

```sql
SELECT 
    medication_id AS medic,
    medication_name,
    dosage
FROM 
    Medications
WHERE 
    dosage = (
        SELECT MAX(dosage)
        FROM Medications
    );

```

**Output:**

![image](https://github.com/user-attachments/assets/176f8112-51fa-450d-881c-9cf2504f134b)


**Question 9**
---
![image](https://github.com/user-attachments/assets/c9aaf654-42cd-4302-ae84-bb83ef4055df)


```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);

```

**Output:**

![image](https://github.com/user-attachments/assets/002ca575-f039-4c29-addf-ccfcb3133b83)


**Question 10**
---
![image](https://github.com/user-attachments/assets/f16d7812-cbae-4de4-afde-87d6c7110ed5)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**

![image](https://github.com/user-attachments/assets/2f282e34-33e8-49f8-9e82-522d99a251c4)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
