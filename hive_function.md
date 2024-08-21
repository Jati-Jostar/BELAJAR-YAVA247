# Hive Functions

## **Aggregate Functions**

1. **`AVG(column)`**
   - Returns the average of the values in a group.
   - **Example:**
     ```sql
     SELECT AVG(salary) FROM employees;
     ```

2. **`COUNT(column)`**
   - Returns the count of the number of rows in a group.
   - **Example:**
     ```sql
     SELECT COUNT(*) FROM employees WHERE department = 'Sales';
     ```

3. **`MAX(column)`**
   - Returns the maximum value in a group.
   - **Example:**
     ```sql
     SELECT MAX(salary) FROM employees;
     ```

4. **`MIN(column)`**
   - Returns the minimum value in a group.
   - **Example:**
     ```sql
     SELECT MIN(salary) FROM employees;
     ```

5. **`SUM(column)`**
   - Returns the sum of the values in a group.
   - **Example:**
     ```sql
     SELECT SUM(salary) FROM employees WHERE department = 'HR';
     ```

## **String Functions**

1. **`CONCAT(string1, string2, ...)`**
   - Concatenates two or more strings.
   - **Example:**
     ```sql
     SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;
     ```

2. **`SUBSTR(string, start_position, length)`**
   - Returns a substring from the specified string.
   - **Example:**
     ```sql
     SELECT SUBSTR('hive', 1, 2); -- Returns 'hi'
     ```

3. **`LENGTH(string)`**
   - Returns the length of the string.
   - **Example:**
     ```sql
     SELECT LENGTH('hive'); -- Returns 4
     ```

4. **`LOWER(string)`**
   - Converts the string to lowercase.
   - **Example:**
     ```sql
     SELECT LOWER('HIVE'); -- Returns 'hive'
     ```

5. **`UPPER(string)`**
   - Converts the string to uppercase.
   - **Example:**
     ```sql
     SELECT UPPER('hive'); -- Returns 'HIVE'
     ```

6. **`TRIM(string)`**
   - Removes leading and trailing spaces from the string.
   - **Example:**
     ```sql
     SELECT TRIM(' hive '); -- Returns 'hive'
     ```

7. **`REVERSE(string)`**
   - Reverses the characters in the string.
   - **Example:**
     ```sql
     SELECT REVERSE('hive'); -- Returns 'evih'
     ```

## **Date Functions**

1. **`CURRENT_DATE()`**
   - Returns the current date.
   - **Example:**
     ```sql
     SELECT CURRENT_DATE();
     ```

2. **`CURRENT_TIMESTAMP()`**
   - Returns the current timestamp.
   - **Example:**
     ```sql
     SELECT CURRENT_TIMESTAMP();
     ```

3. **`DATE_ADD(date, days)`**
   - Adds a specified number of days to a date.
   - **Example:**
     ```sql
     SELECT DATE_ADD('2024-01-01', 5); -- Returns '2024-01-06'
     ```

4. **`DATE_SUB(date, days)`**
   - Subtracts a specified number of days from a date.
   - **Example:**
     ```sql
     SELECT DATE_SUB('2024-01-01', 5); -- Returns '2023-12-27'
     ```

5. **`DATEDIFF(end_date, start_date)`**
   - Returns the difference in days between two dates.
   - **Example:**
     ```sql
     SELECT DATEDIFF('2024-01-10', '2024-01-01'); -- Returns 9
     ```

6. **`YEAR(date)`**
   - Returns the year from a date.
   - **Example:**
     ```sql
     SELECT YEAR('2024-01-01'); -- Returns 2024
     ```

7. **`MONTH(date)`**
   - Returns the month from a date.
   - **Example:**
     ```sql
     SELECT MONTH('2024-01-01'); -- Returns 1
     ```

8. **`DAY(date)`**
   - Returns the day of the month from a date.
   - **Example:**
     ```sql
     SELECT DAY('2024-01-01'); -- Returns 1
     ```

## **Mathematical Functions**

1. **`ABS(number)`**
   - Returns the absolute value of a number.
   - **Example:**
     ```sql
     SELECT ABS(-5); -- Returns 5
     ```

2. **`CEIL(number)`**
   - Returns the smallest integer greater than or equal to the specified number.
   - **Example:**
     ```sql
     SELECT CEIL(4.2); -- Returns 5
     ```

3. **`FLOOR(number)`**
   - Returns the largest integer less than or equal to the specified number.
   - **Example:**
     ```sql
     SELECT FLOOR(4.8); -- Returns 4
     ```

4. **`ROUND(number, decimal_places)`**
   - Rounds a number to the specified number of decimal places.
   - **Example:**
     ```sql
     SELECT ROUND(4.5678, 2); -- Returns 4.57
     ```

5. **`SQRT(number)`**
   - Returns the square root of a number.
   - **Example:**
     ```sql
     SELECT SQRT(16); -- Returns 4
     ```

6. **`POWER(base, exponent)`**
   - Returns the value of a number raised to the power of another number.
   - **Example:**
     ```sql
     SELECT POWER(2, 3); -- Returns 8
     ```

7. **`RAND(seed)`**
   - Generates a random number between 0 and 1.
   - **Example:**
     ```sql
     SELECT RAND(1234);
     ```

8. **`EXP(number)`**
   - Returns e raised to the power of the specified number.
   - **Example:**
     ```sql
     SELECT EXP(1); -- Returns e (approximately 2.718)
     ```

## **Conditional Functions**

1. **`IF(condition, true_value, false_value)`**
   - Returns one value if the condition is true, and another value if the condition is false.
   - **Example:**
     ```sql
     SELECT IF(salary > 50000, 'High', 'Low') FROM employees;
     ```

2. **`COALESCE(value1, value2, ...)`**
   - Returns the first non-null value in the list.
   - **Example:**
     ```sql
     SELECT COALESCE(NULL, NULL, 'default'); -- Returns 'default'
     ```

3. **`CASE WHEN condition THEN result [WHEN ...] ELSE result END`**
   - Evaluates conditions and returns a value when the first condition is met.
   - **Example:**
     ```sql
     SELECT CASE 
              WHEN salary > 50000 THEN 'High' 
              WHEN salary > 30000 THEN 'Medium'
              ELSE 'Low'
            END
     FROM employees;
     ```

4. **`NVL(expr1, expr2)`**
   - Returns expr2 if expr1 is null; otherwise, returns expr1.
   - **Example:**
     ```sql
     SELECT NVL(bonus, 0) FROM employees;
     ```

5. **`NULLIF(expr1, expr2)`**
   - Returns null if expr1 equals expr2; otherwise, returns expr1.
   - **Example:**
     ```sql
     SELECT NULLIF(salary, 0) FROM employees;
     ```

## **Type Conversion Functions**

1. **`CAST(expression AS type)`**
   - Converts an expression from one data type to another.
   - **Example:**
     ```sql
     SELECT CAST(salary AS STRING) FROM employees;
     ```

2. **`CONVERT(expression USING encoding)`**
   - Converts the character set of a string.
   - **Example:**
     ```sql
     SELECT CONVERT('hive', 'latin1', 'utf8');
     ```

3. **`BINARY(string)`**
   - Converts a string to binary format.
   - **Example:**
     ```sql
     SELECT BINARY('hive');
     ```

4. **`UNIX_TIMESTAMP()`**
   - Converts the current time or a specified time to a Unix timestamp.
   - **Example:**
     ```sql
     SELECT UNIX_TIMESTAMP();
     ```

5. **`TO_DATE(string)`**
   - Converts a string to a date.
   - **Example:**
     ```sql
     SELECT TO_DATE('2024-01-01');
     ```
