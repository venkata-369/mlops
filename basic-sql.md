For  **Enterprise MLOps Churn Prediction Platform**, start with only **3 business tables**. is enough

### Database

```sql
CREATE DATABASE mlopsdb;
```

Connect:

```sql
\c mlopsdb
```

---

### DDL (Data Definition Language)

#### Create Customers

```sql
CREATE TABLE customers
(
    customer_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(20),
    city VARCHAR(50),
    state VARCHAR(50),
    country VARCHAR(50),
    signup_date DATE,
    status VARCHAR(20)
);
```

---

#### Create Products

```sql
CREATE TABLE products
(
    product_id SERIAL PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    price DECIMAL(10,2),
    stock_quantity INT,
    created_date DATE
);
```

---

#### Create Orders

```sql
CREATE TABLE orders
(
    order_id SERIAL PRIMARY KEY,
    customer_id INT,
    product_id INT,
    quantity INT,
    total_amount DECIMAL(10,2),
    order_date TIMESTAMP,
    payment_status VARCHAR(20),

    CONSTRAINT fk_customer
    FOREIGN KEY(customer_id)
    REFERENCES customers(customer_id),

    CONSTRAINT fk_product
    FOREIGN KEY(product_id)
    REFERENCES products(product_id)
);
```

---

#### Create Predictions

```sql
CREATE TABLE predictions
(
    prediction_id SERIAL PRIMARY KEY,
    customer_id INT,
    churn_probability DECIMAL(5,2),
    prediction VARCHAR(20),
    model_version VARCHAR(20),
    prediction_time TIMESTAMP,

    CONSTRAINT fk_prediction_customer
    FOREIGN KEY(customer_id)
    REFERENCES customers(customer_id)
);
```

---

## ALTER TABLE

```sql
ALTER TABLE customers
ADD gender VARCHAR(20);
```

```sql
ALTER TABLE customers
DROP COLUMN gender;
```

```sql
ALTER TABLE products
ALTER COLUMN category TYPE VARCHAR(100);
```

---

## RENAME TABLE

```sql
ALTER TABLE products
RENAME TO product_master;
```

Rename back

```sql
ALTER TABLE product_master
RENAME TO products;
```

---

## DROP TABLE

```sql
DROP TABLE predictions;
```

---

## TRUNCATE TABLE

```sql
TRUNCATE TABLE predictions;
```

---

# DML (Data Manipulation Language)

## INSERT

```sql
INSERT INTO customers
(first_name,last_name,email,phone,city,state,country,signup_date,status)

VALUES

('John','David','john@gmail.com','9876543210','Hyderabad','Telangana','India','2026-07-20','ACTIVE');
```

---

## Multiple Inserts

```sql
INSERT INTO products
(product_name,category,price,stock_quantity,created_date)

VALUES

('Laptop','Electronics',65000,25,CURRENT_DATE),
('Mouse','Electronics',500,150,CURRENT_DATE),
('Keyboard','Electronics',1200,75,CURRENT_DATE);
```

---

## SELECT

```sql
SELECT * FROM customers;
```

```sql
SELECT * FROM products;
```

```sql
SELECT * FROM orders;
```

---

## WHERE

```sql
SELECT *
FROM customers
WHERE city='Hyderabad';
```

---

## ORDER BY

```sql
SELECT *
FROM products
ORDER BY price DESC;
```

---

## LIMIT

```sql
SELECT *
FROM products
LIMIT 5;
```

---

## UPDATE

```sql
UPDATE customers

SET status='INACTIVE'

WHERE customer_id=1;
```

---

## DELETE

```sql
DELETE FROM customers

WHERE customer_id=1;
```

---

# DQL (Data Query Language)

```sql
SELECT * FROM customers;
```

```sql
SELECT first_name,email
FROM customers;
```

```sql
SELECT DISTINCT city
FROM customers;
```

---

# DCL (Data Control Language)

## Create User

```sql
CREATE USER mluser
WITH PASSWORD 'Password@123';
```

---

## Grant

```sql
GRANT SELECT
ON customers
TO mluser;
```

---

## Grant All

```sql
GRANT ALL PRIVILEGES
ON TABLE customers
TO mluser;
```

---

## Revoke

```sql
REVOKE INSERT
ON customers
FROM mluser;
```

---

# TCL (Transaction Control Language)

## BEGIN

```sql
BEGIN;
```

---

## INSERT

```sql
INSERT INTO customers
(first_name,last_name,email)

VALUES

('Venkat','Sarath','venkat@gmail.com');
```

---

## COMMIT

```sql
COMMIT;
```

---

## ROLLBACK

```sql
ROLLBACK;
```

---

## SAVEPOINT

```sql
BEGIN;

INSERT INTO customers(first_name,email)
VALUES('ABC','abc@gmail.com');

SAVEPOINT sp1;

INSERT INTO customers(first_name,email)
VALUES('XYZ','xyz@gmail.com');

ROLLBACK TO SAVEPOINT sp1;

COMMIT;
```

---

## Useful DDL Commands

```sql
CREATE TABLE
ALTER TABLE
DROP TABLE
TRUNCATE TABLE
RENAME TABLE
COMMENT ON TABLE
COMMENT ON COLUMN
CREATE INDEX
DROP INDEX
```

---

## Useful DML Commands

```sql
INSERT
UPDATE
DELETE
MERGE (where supported)
COPY
```

---

## Useful DQL Commands

```sql
SELECT
WHERE
ORDER BY
GROUP BY
HAVING
LIMIT
DISTINCT
JOIN
UNION
```

---

## Useful DCL Commands

```sql
CREATE USER
ALTER USER
GRANT
REVOKE
```

---

## Useful TCL Commands

```sql
BEGIN
COMMIT
ROLLBACK
SAVEPOINT
ROLLBACK TO SAVEPOINT
```

This forms a solid **Day 1 SQL lab** for your MLOps course. From here, you can progressively cover constraints, joins, aggregate functions, indexes, views, sequences, stored procedures/functions, triggers, and performance tuning using these same four tables.
