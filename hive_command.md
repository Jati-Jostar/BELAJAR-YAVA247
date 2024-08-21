
# Hive Commands

## **Data Definition Language (DDL)**
Commands for defining database schema and managing tables.

1. **`CREATE DATABASE database_name`**
   - Creates a new database.
   - **Example:**
     ```sql
     CREATE DATABASE my_database;
     ```

2. **`DROP DATABASE database_name`**
   - Deletes an existing database.
   - **Example:**
     ```sql
     DROP DATABASE my_database;
     ```

3. **`CREATE TABLE table_name (column1 datatype, column2 datatype, ...)`**
   - Creates a new table.
   - **Example:**
     ```sql
     CREATE TABLE employees (id INT, name STRING, salary FLOAT);
     ```

4. **`DROP TABLE table_name`**
   - Deletes an existing table.
   - **Example:**
     ```sql
     DROP TABLE employees;
     ```

5. **`ALTER TABLE table_name ADD COLUMNS (column_name datatype, ...)`**
   - Adds columns to an existing table.
   - **Example:**
     ```sql
     ALTER TABLE employees ADD COLUMNS (department STRING);
     ```

6. **`ALTER TABLE table_name DROP [COLUMN] column_name`**
   - Drops a column from an existing table.
   - **Example:**
     ```sql
     ALTER TABLE employees DROP COLUMN department;
     ```

7. **`ALTER TABLE table_name RENAME TO new_table_name`**
   - Renames an existing table.
   - **Example:**
     ```sql
     ALTER TABLE employees RENAME TO staff;
     ```

8. **`TRUNCATE TABLE table_name`**
   - Removes all rows from a table without deleting the table itself.
   - **Example:**
     ```sql
     TRUNCATE TABLE employees;
     ```

9. **`DESCRIBE DATABASE [EXTENDED] database_name`**
   - Describes a database, showing details like location, owner, etc.
   - **Example:**
     ```sql
     DESCRIBE DATABASE EXTENDED my_database;
     ```

10. **`DESCRIBE [EXTENDED] table_name`**
    - Describes a table, showing columns, data types, etc.
    - **Example:**
      ```sql
      DESCRIBE EXTENDED employees;
      ```

11. **`SHOW DATABASES`**
    - Lists all databases.
    - **Example:**
      ```sql
      SHOW DATABASES;
      ```

12. **`SHOW TABLES [IN database_name]`**
    - Lists all tables in the current or specified database.
    - **Example:**
      ```sql
      SHOW TABLES IN my_database;
      ```

13. **`SHOW COLUMNS IN table_name`**
    - Lists all columns in a table.
    - **Example:**
      ```sql
      SHOW COLUMNS IN employees;
      ```

14. **`SHOW PARTITIONS table_name`**
    - Lists all partitions of a table.
    - **Example:**
      ```sql
      SHOW PARTITIONS employees;
      ```

15. **`MSCK REPAIR TABLE table_name`**
    - Updates the Hive metastore with new partitions added to HDFS.
    - **Example:**
      ```sql
      MSCK REPAIR TABLE employees;
      ```

16. **`USE database_name`**
    - Sets the current database to the specified one.
    - **Example:**
      ```sql
      USE my_database;
      ```

## **Data Manipulation Language (DML)**
Commands for inserting, updating, deleting, and retrieving data.

1. **`SELECT columns FROM table_name [WHERE condition]`**
   - Retrieves data from a table.
   - **Example:**
     ```sql
     SELECT name, salary FROM employees WHERE department = 'Sales';
     ```

2. **`INSERT INTO table_name (columns) VALUES (values)`**
   - Inserts new data into a table.
   - **Example:**
     ```sql
     INSERT INTO employees (id, name, salary) VALUES (1, 'John Doe', 50000);
     ```

3. **`INSERT OVERWRITE TABLE table_name [PARTITION (partition)] SELECT ...`**
   - Overwrites existing data in a table or partition with new data.
   - **Example:**
     ```sql
     INSERT OVERWRITE TABLE employees SELECT * FROM new_employees;
     ```

4. **`UPDATE table_name SET column = value [WHERE condition]`**
   - Updates existing data in a table.
   - **Example:**
     ```sql
     UPDATE employees SET salary = 60000 WHERE id = 1;
     ```

5. **`DELETE FROM table_name [WHERE condition]`**
   - Deletes data from a table.
   - **Example:**
     ```sql
     DELETE FROM employees WHERE salary < 30000;
     ```

6. **`LOAD DATA INPATH 'filepath' INTO TABLE table_name`**
   - Loads data from a file into a table.
   - **Example:**
     ```sql
     LOAD DATA INPATH '/user/hive/data/employees.csv' INTO TABLE employees;
     ```

7. **`EXPORT TABLE table_name TO 'filepath'`**
   - Exports data from a table to a file.
   - **Example:**
     ```sql
     EXPORT TABLE employees TO '/user/hive/backup/employees';
     ```

8. **`IMPORT TABLE table_name FROM 'filepath'`**
   - Imports data from a file into a table.
   - **Example:**
     ```sql
     IMPORT TABLE employees FROM '/user/hive/backup/employees';
     ```

9. **`TRUNCATE TABLE table_name`**
   - Removes all rows from a table without deleting the table itself.
   - **Example:**
     ```sql
     TRUNCATE TABLE employees;
     ```

## **Data Control Language (DCL)**
Commands for controlling access to data.

1. **`GRANT privilege ON table_name TO user`**
   - Grants a specific privilege on a table to a user.
   - **Example:**
     ```sql
     GRANT SELECT ON employees TO user1;
     ```

2. **`REVOKE privilege ON table_name FROM user`**
   - Revokes a specific privilege on a table from a user.
   - **Example:**
     ```sql
     REVOKE SELECT ON employees FROM user1;
     ```

## **Utility Commands**
Commands that assist in managing Hive environment and configurations.

1. **`SET key=value`**
   - Sets a configuration property.
   - **Example:**
     ```sql
     SET hive.execution.engine=tez;
     ```

2. **`RESET`**
   - Resets all configuration properties to their default values.
   - **Example:**
     ```sql
     RESET;
     ```

3. **`EXPLAIN [EXTENDED|DEPENDENCY] query`**
   - Displays the execution plan for a query.
   - **Example:**
     ```sql
     EXPLAIN EXTENDED SELECT * FROM employees;
     ```

4. **`SHOW FUNCTIONS`**
   - Lists all available functions.
   - **Example:**
     ```sql
     SHOW FUNCTIONS;
     ```

5. **`DESCRIBE FUNCTION function_name`**
   - Describes a function.
   - **Example:**
     ```sql
     DESCRIBE FUNCTION CONCAT;
     ```

6. **`ADD JAR filepath`**
   - Adds a JAR file to the classpath.
   - **Example:**
     ```sql
     ADD JAR /user/hive/lib/custom_udf.jar;
     ```

7. **`LIST JARS`**
   - Lists all JAR files added to the classpath.
   - **Example:**
     ```sql
     LIST JARS;
     ```
