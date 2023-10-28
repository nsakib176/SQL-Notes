Here is a list of common database table column constraints along with examples:

1. **PRIMARY KEY Constraint:**
   - Ensures that each value in the column is unique and not NULL.
   - Used to uniquely identify each row in the table.

   Example:
   ```sql
   CREATE TABLE Students (
       student_id INT PRIMARY KEY,
       first_name VARCHAR(50),
       last_name VARCHAR(50)
   );
   ```

2. **UNIQUE Constraint:**
   - Ensures that all values in the column are unique, but NULL values are allowed.

   Example:
   ```sql
   CREATE TABLE Employees (
       employee_id INT UNIQUE,
       first_name VARCHAR(50),
       last_name VARCHAR(50)
   );
   ```

3. **CHECK Constraint:**
   - Defines a condition that must be met for values in the column.

   Example:
   ```sql
   CREATE TABLE Products (
       product_id INT,
       product_name VARCHAR(100),
       price DECIMAL(10, 2),
       CHECK (price >= 0)
   );
   ```

4. **NOT NULL Constraint:**
   - Ensures that values in the column are not NULL.

   Example:
   ```sql
   CREATE TABLE Orders (
       order_id INT,
       customer_id INT NOT NULL,
       order_date DATE
   );
   ```

5. **DEFAULT Constraint:**
   - Specifies a default value for a column if no value is provided during insertion.

   Example:
   ```sql
   CREATE TABLE Tasks (
       task_id INT,
       task_name VARCHAR(100),
       status VARCHAR(20) DEFAULT 'Pending'
   );
   ```

6. **FOREIGN KEY Constraint:**
   - Defines a relationship between columns in different tables, ensuring referential integrity.

   Example:
   ```sql
   CREATE TABLE Orders (
       order_id INT PRIMARY KEY,
       customer_id INT,
       FOREIGN KEY (customer_id) REFERENCES Customers(customer_id)
   );

   CREATE TABLE Customers (
       customer_id INT PRIMARY KEY,
       customer_name VARCHAR(100)
   );
   ```

These constraints help maintain the quality and consistency of data in a database by preventing invalid or inconsistent data from being inserted or updated. They are essential for ensuring data integrity and accuracy in your database.