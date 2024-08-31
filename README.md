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

        | Name |  
        | ---- |    
        | Rasel |
        | Shibli |  
        | Sujon |
    
11. For get multiple key data.
    ```sh
    SELECT Roll, Name, Age FROM students;
    ```
    - **Output**.

       | Roll | Name | Age |
       | ----- | ----- | ----- |
       | 101 | Rasel | 22 |
       | 102 | Shibli | 22 |
       | 103 | Sujon | 22 |
       | 104 | Sohag | 20 |

12. For get all key data from a table.
    ```sh
    SELECT * FROM students;
    ```
    - **Output**.

       | Roll | Name | Gender | Age | GPA |
       | ----- | ----- | ----- | ----- | ----- |
       | 101 | Rasel | Male | 22 | 4.35 |
       | 102 | Shibli | Male | 22 | 4.30 |
       | 103 | Sujon | Male | 22 | 4.35 |
       | 104 | Sohag | Male | 20 | 4.20 |
13. Using of LIMIT to get specific number of record data.
    ```sh
    SELECT * FROM students LIMIT 2;
    ```
    - **Output**.

       | Roll | Name | Gender | Age | GPA |
       | ----- | ----- | ----- | ----- | ----- |
       | 101 | Rasel | Male | 22 | 4.35 |
       | 102 | Shibli | Male | 22 | 4.30 |
13. Using of LIMIT and set a desire number from where to start get data.
    ```sh
    SELECT * FROM students LIMIT 1, 2;
    ```
    - **Output**.

       | Roll | Name | Gender | Age | GPA |
       | ----- | ----- | ----- | ----- | ----- |
       | 102 | Shibli | Male | 22 | 4.30 |
       | 103 | Sujon | Male | 22 | 4.35 |


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