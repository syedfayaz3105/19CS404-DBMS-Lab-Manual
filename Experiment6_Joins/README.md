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
![image](https://github.com/user-attachments/assets/1f978318-0b34-41e1-9f17-170d01ecb799)


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/29a76522-b5f3-4a2b-be87-30e1a919fa3a)


**Question 2**
---
![image](https://github.com/user-attachments/assets/5642cc29-99d7-4a25-b57b-c1cc39e106a6)


```sql
SELECT 
    s.salesman_id,
    s.name,
    s.city,
    s.commission
FROM 
    salesman s
LEFT JOIN 
    customer c ON s.salesman_id = c.salesman_id
WHERE 
    c.cust_name = 'Fabian Johns';

```

**Output:**

![image](https://github.com/user-attachments/assets/cfc31cf8-b7ea-45dd-92c4-4ffb22e8e6ce)


**Question 3**
---
![image](https://github.com/user-attachments/assets/6bce84f2-204d-498c-a154-7c0b8767dba5)


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS Salesman,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/29dc7a75-7890-4b6f-b2e1-b4a70558a1ab)


**Question 4**
---
![image](https://github.com/user-attachments/assets/63fbe220-f1df-47e7-8a84-578145deea6e)


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

![image](https://github.com/user-attachments/assets/7680b9ba-652b-4178-ac42-a3705241c998)

**Question 5**
---
![image](https://github.com/user-attachments/assets/b22d3ad0-2355-4766-828e-0b49da80293f)


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

![image](https://github.com/user-attachments/assets/db75c3cf-6331-4e64-8fc2-3a7a79ebfd68)

**Question 6**
---
![image](https://github.com/user-attachments/assets/716fc324-8a96-4454-93d9-3deeddef4a62)


```sql
SELECT p.*
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'John' AND d.last_name = 'Smith';

```

**Output:**

![image](https://github.com/user-attachments/assets/c9b27c5a-cda7-404e-8c2d-968690c29c00)


**Question 7**
---
![image](https://github.com/user-attachments/assets/58f3d399-81a0-46e4-8bfb-a9d017dd6c02)


```sql
SELECT c.cust_name AS "Customer Name", c.city, s.name AS Salesman, s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/14fc2ba2-577c-42c5-9356-ee4036f11319)


**Question 8**
---
![image](https://github.com/user-attachments/assets/0fc9629c-e0e2-4994-a419-74f64ba02a24)


```sql
select p.first_name,s.* 
from PATIENTS p
inner join SURGERIES s ON p.patient_id=s.patient_id
where discharge_date='2024-03-01' and '2024-03-31'
```

**Output:**

![image](https://github.com/user-attachments/assets/59e42986-113f-44f3-9bda-68b18a1aeeff)


**Question 9**
---
![image](https://github.com/user-attachments/assets/3b82fc87-5a94-4128-8e6d-cc08b3c1e108)

```sql
SELECT p.first_name as 'patient_name',d.first_name as 'doctor_name'
from PATIENTS p
inner join DOCTORS d ON p.doctor_id=d.doctor_id
where p.discharge_date IS NULL
```

**Output:**

![image](https://github.com/user-attachments/assets/9bc2cb2f-1415-41a2-9f0f-1545b8e8550c)


**Question 10**
---
![image](https://github.com/user-attachments/assets/aac7c2e0-d6c3-4273-a9b1-76b79904f654)


```sql
select p.*
from PATIENTS p
inner join DOCTORS d ON p.doctor_id=d.doctor_id
where d.first_name='John' and d.last_name='Smith'
```

**Output:**

![image](https://github.com/user-attachments/assets/6a0e171c-440d-4758-9334-1b5ffbb01b0a)

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
