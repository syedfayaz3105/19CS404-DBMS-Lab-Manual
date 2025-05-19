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
--
![image](https://github.com/user-attachments/assets/023d49eb-b94c-4c96-8153-11ce83f77898)


```sql
SELECT PatientID, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID 
;

```

**Output:**

![image](https://github.com/user-attachments/assets/493ce7f6-f7bd-46a7-9c78-e73795b46d7f)



**Question 2**
---
![image](https://github.com/user-attachments/assets/9bc14327-9237-4a57-b8d2-18cb79875ec4)



```sql
SELECT DATE(AppointmentDateTime) AS AppointmentDate, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DATE(AppointmentDateTime)
;
```

**Output:**

![image](https://github.com/user-attachments/assets/ad873b73-eef5-49be-84ae-987496c36b6e)



**Question 3**
---
![image](https://github.com/user-attachments/assets/5d9dac8a-8699-42e1-8e33-54671f8c955e)

```sql
SELECT DoctorID, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID
;

```

**Output:**

![image](https://github.com/user-attachments/assets/0728045b-c13c-4794-9052-cedea7eeeb0f)

**Question 4**
---
![image](https://github.com/user-attachments/assets/6a79a494-e9a1-476a-a59e-af63a3c5a1f1)

```sql
SELECT AVG(LENGTH(email)) AS avg_email_length_below_30
FROM customer
WHERE city = 'Mumbai';

```

**Output:**

![image](https://github.com/user-attachments/assets/2405d4de-5788-47f4-b663-8dfe9aabd0c9)

**Question 5**
---
![image](https://github.com/user-attachments/assets/b6a76bc6-ea3e-4cac-8b33-c41223b16fdf)

```sql
SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;


```

**Output:**

![image](https://github.com/user-attachments/assets/5e882bbd-45da-4c63-aa5e-692d38dc86aa)


**Question 6**
---
![image](https://github.com/user-attachments/assets/48f6a6ae-e116-4bde-91a2-891bfa97be7c)


```sql
SELECT SUM(income) AS total_income
FROM employee
WHERE age >= 40;
```

**Output:**

![image](https://github.com/user-attachments/assets/895e45be-afd7-4a75-9587-487697bafd56)


**Question 7**
---
![image](https://github.com/user-attachments/assets/a7c598d3-2d6a-47f8-b55a-35b07f23083a)


```sql
SELECT COUNT(*) AS employees_count
FROM employee
GROUP BY income > 50000;
```

**Output:**

![image](https://github.com/user-attachments/assets/98696f2f-7352-466e-babf-399c121f3251)

**Question 8**
---
![image](https://github.com/user-attachments/assets/a73fcce0-9c6a-4954-b44a-19fe6c18e84e)


```sql
SELECT jdate,SUM(workhour) AS 'SUM(workhour)'
FROM employee1
GROUP BY jdate
HAVING SUM(workhour) > 40;

```

**Output:**

![image](https://github.com/user-attachments/assets/2d646ebe-a197-4ef9-85e0-26a112e4ff57)

**Question 9**
---
![image](https://github.com/user-attachments/assets/161964f5-91b9-44c0-9d28-e0128bf0e4a6)


```sql
SELECT  (age / 5) * 5 AS age_group,MAX(salary) AS 'MAX(salary)'
FROM customer1
GROUP BY age_group
HAVING MAX(salary) > 8000;

```

**Output:**

![image](https://github.com/user-attachments/assets/66087769-fad8-47d1-92ef-c02ab34811f6)

**Question 10**
---
![image](https://github.com/user-attachments/assets/f8bcabd3-410b-4a64-a511-22ec7eb30e53)

```sql
SELECT category_id,Min(Price) AS 'Price'
FROM products
GROUP BY category_id
HAVING Min(Price) < 10;

```

**Output:**

![image](https://github.com/user-attachments/assets/945e01fa-701e-488c-b7db-808a0d2d4c08)




## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
