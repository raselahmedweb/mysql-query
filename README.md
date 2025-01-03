# This is mySQL documentation

1. For show database.

   ```sh
   SHOW DATABASES;
   ```

2. For create database.

   ```sh
   CREATE DATABASE database_name;
   ```

   - **Example**.

   ```sh
   CREATE DATABASE college;
   ```

3. For delete database.
   ```sh
   DROP DATABASE college;
   ```
4. For create table and table key.

   ```sh
   CREATE TABLE table_name (table_key);
   ```

   - **Example**.

   ```sh
   CREATE TABLE students
   (
       Roll int(3),
       Name varchar(15),
       Gender varchar(10),
       Age int(3),
       GPA double(3,2),
       PRIMARY KEY(Roll)
   );
   ```

5. For delete table.
   ```sh
   DROP TABLE students;
   ```
6. For rename table.
   ```sh
   RENAME TABLE students TO students2;
   ```
7. Insert records or data into table.
   ```sh
   INSERT INTO students
   (Roll, Name, Gender, Age, GPA)
   VALUES(101, 'Rasel', 'Male', 22, 4.35);
   ```
8. Insert records or data into table without mention keys.
   ```sh
   INSERT INTO students
   VALUES(102, 'Shibli', 'Male', 22, 4.30);
   ```
9. Insert multiple records or data into table without mention keys.
   ```sh
   INSERT INTO students
   VALUES(103, 'Shibli', 'Male', 22, 4.30),
   (104, 'Sujon', 'Male', 22, 4.35),
   (105, 'Sohag', 'Male', 20, 4.20);
   ```

# There is two type of data command in database query

1. DDL(Data Defination Language)
   - **CREATE**
   - **ALTER**
   - **DROP**
2. DML(Data manipulation Language)
   - **INSERT**
   - **SELECT**
   - **UPDATE**
   - **DELETE**

## Using of SELECT commands

10. For get a data from table key.

    ```sh
    SELECT Name FROM students;
    ```

    - **Output**.

      | Name   |
      | ------ |
      | Rasel  |
      | Shibli |
      | Sujon  |

11. For get multiple key data.

    ```sh
    SELECT Roll, Name, Age FROM students;
    ```

    - **Output**.

      | Roll | Name   | Age |
      | ---- | ------ | --- |
      | 101  | Rasel  | 22  |
      | 102  | Shibli | 22  |
      | 103  | Sujon  | 22  |
      | 104  | Sohag  | 20  |

12. For get all key data from a table.

    ```sh
    SELECT * FROM students;
    ```

    - **Output**.

      | Roll | Name   | Gender | Age | GPA  |
      | ---- | ------ | ------ | --- | ---- |
      | 101  | Rasel  | Male   | 22  | 4.35 |
      | 102  | Shibli | Male   | 22  | 4.30 |
      | 103  | Sujon  | Male   | 22  | 4.35 |
      | 104  | Sohag  | Male   | 20  | 4.20 |

13. Using of LIMIT to get specific number of record data.

    ```sh
    SELECT * FROM students LIMIT 2;
    ```

    - **Output**.

      | Roll | Name   | Gender | Age | GPA  |
      | ---- | ------ | ------ | --- | ---- |
      | 101  | Rasel  | Male   | 22  | 4.35 |
      | 102  | Shibli | Male   | 22  | 4.30 |

14. Using of LIMIT and set a desire number from where to start get data.

    ```sh
    SELECT * FROM students LIMIT 1, 2;
    ```

    - **Output**.

      | Roll | Name   | Gender | Age | GPA  |
      | ---- | ------ | ------ | --- | ---- |
      | 102  | Shibli | Male   | 22  | 4.30 |
      | 103  | Sujon  | Male   | 22  | 4.35 |

15. Using SELECT DISTINCT command to get data.  
    Suppose we have a new column or key name Country. Its define our students coming from which country. So definetly will be a lot of country and sometimes from same country so many students are coming. And we wants to know how many countries students arte coming here. So if we select Country key as normal its will print all students countryname but we dont want a country name in more than one time to execute. For this we will use DISTINCT with SELECT commands.

    ```sh
    SELECT DISTINCT Country FROM students;
    ```

    - **Output**.  
       just imagine we have 8 students and all of them from bangladesh. because of using DISTINCT its will show us Bangladesgh only one time.
      | Country |  
      | ---- |  
      | Bangladesh |

16. Use ORDER BY to sort Name.

    ```sh
    SELECT Name, GPA FROM students ORDER BY GPA;
    ```

    - **Output**.  
      | Name | GPA |
      | ---- | ---- |  
      | Sohag | 4.20 |
      | Shibli | 4.30 |
      | Sujon | 4.35 |
      | Rasel | 4.35 |

17. Use ORDER BY to sort Name Descending.
    ```sh
    SELECT Name, GPA FROM students ORDER BY GPA DESC;
    ```
    - **Output**.  
      | Name | GPA |
      | ---- | ---- |  
      | Rasel | 4.35 |
      | Sujon | 4.35 |
      | Shibli | 4.30 |
      | Sohag | 4.20 |

# We will learn now to find value using arithmatc, comparison and logical operators.

18. We want to see \* record where GPA 4.35
    ```sh
    SELECT * FROM students
    WHERE GPA = 4.35;
    ```
    - **Output**.  
      | Roll | Name | Gender | Age | GPA |
      | ---- | ------ | ------ | --- | ---- |
      | 101 | Rasel | Male | 22 | 4.35 |
      | 103 | Sujon | Male | 22 | 4.35 |

# Create a new table.

```sh
CREATE TABLE employee
(
   Id int(5),
   Name varchar(20),
   Department varchar(30),
   Position varchar(30),
   Gender varchar(10),
   Age int(3),
   Address varchar(15),
   PRIMARY KEY(Id)
)
```

- **Output**

| Id  | Name | Department | Position | Gender | Age | Address |
| --- | ---- | ---------- | -------- | ------ | --- | ------- |

```sh
   INSERT INTO employee
   VALUES (1, 'Anisul Islam', 'IT', 'Full Stack Developer', 'Male', 31, 'Finland'),
   (2, 'Sohel Rana', 'Marketing', 'Manager', 'Male', 35, 'Saudi Arabiya'),
   (3, 'Raihan', 'Coffee', 'Barista', 'Male', 27, 'Saudi Arabiya'),
   (4, 'Srijita', 'Reciption', 'Reciptionist', 'Female', 24, 'Saudi Arabiya'),
   (5, 'Anamol', 'F and b', 'Supervisor', 'Male', 31, 'UAE'),
   (6, 'Abu Ahmed', 'Marketing', 'Manager', 'Male', 33, 'Saudi Arabiya'),
    (7, 'Fatima Noor', 'HR', 'HR Manager', 'Female', 29, 'UAE'),
   (8, 'John Smith', 'Finance', 'Accountant', 'Male', 45, 'USA'),
   (9, 'Emily Johnson', 'Sales', 'Sales Executive', 'Female', 30, 'UK'),
   (10, 'Ahmed Ali', 'IT', 'System Administrator', 'Male', 28, 'India');
```

- **Output**

| Id  | Name          | Department | Position             | Gender | Age | Address      |
| --- | ------------- | ---------- | -------------------- | ------ | --- | ------------ |
| 1   | Anisul Islam  | IT         | Full Stack Developer | Male   | 31  | Finland      |
| 2   | Sohel Rana    | Marketing  | Manager              | Male   | 35  | Saudi Arabia |
| 3   | Raihan        | Coffee     | Barista              | Male   | 27  | Saudi Arabia |
| 4   | Srijita       | Reciption  | Reciptionist         | Female | 24  | Saudi Arabia |
| 5   | Anamol        | F and B    | Supervisor           | Male   | 31  | UAE          |
| 6   | Abu Ahmed     | Marketing  | Manager              | Male   | 33  | Saudi Arabia |
| 7   | Fatima Noor   | HR         | HR Manager           | Female | 29  | UAE          |
| 8   | John Smith    | Finance    | Accountant           | Male   | 45  | USA          |
| 9   | Emily Johnson | Sales      | Sales Executive      | Female | 30  | UK           |
| 10  | Ahmed Ali     | IT         | System Administrator | Male   | 28  | India        |

## Now practice query based on this new table data

19. Select data by Logical Operators.

```sh
SELECT * FROM employee WHERE Id > 6;
```

- **Output**

| Id  | Name          | Department | Position             | Gender | Age | Address |
| --- | ------------- | ---------- | -------------------- | ------ | --- | ------- |
| 7   | Fatima Noor   | HR         | HR Manager           | Female | 29  | UAE     |
| 8   | John Smith    | Finance    | Accountant           | Male   | 45  | USA     |
| 9   | Emily Johnson | Sales      | Sales Executive      | Female | 30  | UK      |
| 10  | Ahmed Ali     | IT         | System Administrator | Male   | 28  | India   |

20. Use two condition AND operators.

```sh
SELECT * FROM employee WHERE Id > 6 AND Gender = 'Female';
```

- **Output**

| Id  | Name          | Department | Position        | Gender | Age | Address |
| --- | ------------- | ---------- | --------------- | ------ | --- | ------- |
| 7   | Fatima Noor   | HR         | HR Manager      | Female | 29  | UAE     |
| 9   | Emily Johnson | Sales      | Sales Executive | Female | 30  | UK      |

21. Use of LIKE operators.

```sh
SELECT Name, Age, Address FROM employee WHERE Age >= 30 AND Name LIKE 'A%';
```

- **Output**

| Name         | Age | Address      |
| ------------ | --- | ------------ |
| Anisul Islam | 31  | Finland      |
| Anamol       | 31  | UAE          |
| Abu Ahmed    | 33  | Saudi Arabia |

22. Use of AS keyword.

```sh
SELECT Id AS Roll, Name AS 'First Name' FROM employee WHERE Id < 5;
```

- **Output**

| Roll | First Name   |
| ---- | ------------ |
| 1    | Anisul Islam |
| 2    | Sohel Rana   |
| 3    | Raihan       |
| 4    | Srijita      |

# Create SQL Constraints

- **NOT NULL**

```sh
CREATE TABLE Users (
 ID INT NOT NULL,
 Name VARCHAR(100) NOT NULL
);
```

- **UNIQUE**

```sh
CREATE TABLE Users (
    ID INT UNIQUE,
    Email VARCHAR(100) UNIQUE
);
```

- **PRIMARY KEY = NOT NALL + UNIQUE**

```sh
CREATE TABLE Users (
    ID INT PRIMARY KEY,
    Name VARCHAR(100)
);
```

- **FOREIGN KEY**

```sh
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    UserID INT,
    FOREIGN KEY (UserID) REFERENCES Users(ID)
);
```

- **CHECK**

```sh
CREATE TABLE Products (
    ProductID INT PRIMARY KEY,
    Price DECIMAL(10, 2),
    CHECK (Price > 0)
);
```

- **DEFAULT**

```sh
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Salary DECIMAL(10, 2) DEFAULT 50000
);
```

23. Use UPDATE SET to update the records.

```sh
UPDATE employee SET Address = 'Bangladesh' WHERE Id = 10;
```

- **Output**

| Id  | Name          | Department | Position             | Gender | Age | Address |
| --- | ------------- | ---------- | -------------------- | ------ | --- | ------- |
| 7   | Fatima Noor   | HR         | HR Manager           | Female | 29  | UAE     |
| 8   | John Smith    | Finance    | Accountant           | Male   | 45  | USA     |
| 9   | Emily Johnson | Sales      | Sales Executive      | Female | 30  | UK      |
| 10  | Ahmed Ali     | IT         | System Administrator | Male   | 28  | Bangladesh* |


# Use of some function in query.

   - **UPPER()**
   - **LOWER()**
   - **CONCAT()**
   - **POW()**
   - **GREATEST()**
   - **LEAST()**
   - **LOG()**
   - **LOG10()**
   - **EXP()**
   - **RAND()**

24. example

```sh
SELECT CONCAT(Name, ' is ', Age, ' year old') FROM employee WHERE Id = 8;
```
   - **Output**  
      CONCAT(Name, ' is ', Age, ' year old')  
      John Smith is 45 year old

# Aggregate functions
   - **COUNT()**
   - **SUM()**
   - **AVG()**
   - **MIN()**
   - **MAX()**

25. example.

```sh
SELECT SUM(Id) AS 'Sum of Id', AVG(Id) AS 'Avarage of Id' FROM employee;
```
- **Output**

| Sum of Id | Avarage of Id |
| ----- | ------- |
| 55 | 5.5000 |

# ALTER TABLE 
### ALTER TABLE command is used for
   - **to add new column in the table**
   - **to change the name of column**
   - **to delete the column**
26. ADD column syntax
```sh
ALTER TABLE employee ADD Salery int(7);
```
27. Rename column
```sh
ALTER TABLE employee CHANGE Salery Salery_per int(7);
```
28. Delete column
```sh
ALTER TABLE employee DROP TABLE Salery;
```

29. GRUOP BY CLAUSE
```sh
SELECT Department, SUM(Salery) FROM employee GROUP BY Department;
```


30. use TRUNCATE TABLE to remove all data or records from the table
```sh
TRUNCATE TABLE employee;
```

31. Join Table to get data from multiple tables
```sh
SELECT employee.ID, Name, Gender, Department, Salery, Location, Budget, EstablishedYear FROM department, employee WHERE employee.ID = department.ID;
```
alternatively here also we can use JOIN instead of coma and ON instead of WHERE;

```sh
SELECT employee.ID, Name, Gender, Department, Salery, Location, Budget, EstablishedYear FROM department JOIN employee ON employee.ID = department.ID;
```
also LEFT JOIN and RIGHT JOIN can be use.

32. UNION and UNION ALL
To use this syntex we have to make sure that we are taking same column and same sequence order.

```sh
SELECT Name, Gender, TourPlace From student_one
UNION
SELECT Name, Gender, TourPlace From student_two;
```
here its will not show us duplicate value. to see the duplicate value we can use UNION ALL instead of UNION.

33. creating virtual table.

```sh
CREATE VIEW employee_views AS SELECT ID, Name, Gender FROM employee;
```
34. then we can use date related some functions.


