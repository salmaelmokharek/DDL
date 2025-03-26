# DDL Checkpoint

Create the Customer Table
-
CREATE TABLE Customer (
    customer_id VARCHAR2(20) PRIMARY KEY,
    customer_name VARCHAR2(20) NOT NULL,
    customer_tel NUMBER
);

Create the Product Table
-
CREATE TABLE Product (
    product_id VARCHAR2(20) PRIMARY KEY,
    product_name VARCHAR2(20) NOT NULL,
    price NUMBER (price > 0)
);

Create the Orders Table
-
CREATE TABLE Orders (
    customer_id VARCHAR2(20),
    product_id VARCHAR2(20),
    quantity NUMBER,
    total_amount NUMBER(10, 2),
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id),
    FOREIGN KEY (product_id) REFERENCES Product(product_id)
);

Add Category column to Product table
-
ALTER TABLE Product
ADD Category VARCHAR2(20);

Add OrderDate column to Orders table with default SYSDATE
-
ALTER TABLE Orders
ADD OrderDate DATE DEFAULT SYSDATE;
