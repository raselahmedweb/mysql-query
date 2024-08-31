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
    CREATE TABLE database_name (table_key);
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
8. Insert multiple records or data into table without mention keys.
    ```sh
    INSERT INTO students
    VALUES(103, 'Shibli', 'Male', 22, 4.30),
    (104, 'Sujon', 'Male', 22, 4.35),
    (105, 'Sohag', 'Male', 20, 4.20);
    ```