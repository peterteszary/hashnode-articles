---
title: "#Day3 - The Database"
datePublished: Wed Feb 28 2024 08:13:06 GMT+0000 (Coordinated Universal Time)
cuid: clt5irm4m000309jvb3e90w5l
slug: day3-the-database
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/WEizaiwLk1k/upload/9c6438c3f91e383dc4856a4b5fa93db7.jpeg
tags: databases, developer, sql

---

### Intro

I was a few days late with the development. I just had so much time with work and school that I never had time to do the project.

Anyway...

### The Database

Today I created the database for the desktop application. The database contains 3 tables: Users, Websites and Products. The goal is to be able to synchronize the products created in the desktop application with the website database.

The data types and everything else that is needed are available. Of course this is not the final version, but we have been given the task to present our database.

### The ER Diagram

I have also created the linked ER diagram.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709107798843/8f3437ab-a598-47bf-a9a8-66abab8abd4b.png align="center")

That has since been corrected with my Tutor and One of my Teammates and two additional tables have been added to make the handling of the functions more logical and easier

### This is the SQL command to create the table:

```plaintext
-- Creating table of Users
CREATE TABLE Users (
    UserID INT PRIMARY KEY AUTO_INCREMENT,
    Username VARCHAR(50) NOT NULL,
    Password VARCHAR(100) NOT NULL,
    Email VARCHAR(100),
    FullName VARCHAR(100),
    UNIQUE(Username)
);

-- Creating Table of Products
CREATE TABLE Products (
    ProductID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(100) NOT NULL,
    Description TEXT,
    Price DECIMAL(10, 2) NOT NULL,
    SalesPrice DECIMAL(10, 2),
    Category VARCHAR(50),
    Tag VARCHAR(50),
    ShortDescription TEXT,
    LongDescription TEXT,
    SKU VARCHAR(50),
    StockQuantity INT NOT NULL,
    UNIQUE(Name)
);

-- Creating Table of Websites
CREATE TABLE Websites (
    WebsiteID INT PRIMARY KEY AUTO_INCREMENT,
    URL VARCHAR(255) NOT NULL,
    AuthenticationURL VARCHAR(255) NOT NULL,
    Username VARCHAR(50) NOT NULL,
    Password VARCHAR(100) NOT NULL,
    UNIQUE(URL)
);

-- Add an example user
INSERT INTO Users (Username, Password, Email, FullName) 
VALUES ('peterteszary', 'jelszo123', 'peterteszary@gmail.com', 'Peter Teszary');

-- Adding example products (10 flash drives)
INSERT INTO Products (Name, Description, Price, Category, ShortDescription, SKU, StockQuantity) 
VALUES 
('Pendrive 1GB', '1 gigabájtos pendrive', 10.99, 'Pendrive', '1GB pendrive', 'PD1GB', 100),
('Pendrive 2GB', '2 gigabájtos pendrive', 14.99, 'Pendrive', '2GB pendrive', 'PD2GB', 80),
('Pendrive 4GB', '4 gigabájtos pendrive', 19.99, 'Pendrive', '4GB pendrive', 'PD4GB', 70),
('Pendrive 8GB', '8 gigabájtos pendrive', 24.99, 'Pendrive', '8GB pendrive', 'PD8GB', 60),
('Pendrive 16GB', '16 gigabájtos pendrive', 29.99, 'Pendrive', '16GB pendrive', 'PD16GB', 50),
('Pendrive 32GB', '32 gigabájtos pendrive', 39.99, 'Pendrive', '32GB pendrive', 'PD32GB', 40),
('Pendrive 64GB', '64 gigabájtos pendrive', 49.99, 'Pendrive', '64GB pendrive', 'PD64GB', 30),
('Pendrive 128GB', '128 gigabájtos pendrive', 69.99, 'Pendrive', '128GB pendrive', 'PD128GB', 20),
('Pendrive 256GB', '256 gigabájtos pendrive', 99.99, 'Pendrive', '256GB pendrive', 'PD256GB', 10),
('Pendrive 512GB', '512 gigabájtos pendrive', 149.99, 'Pendrive', '512GB pendrive', 'PD512GB', 5);
```

My goal for the week is to finish the Front End part of the Desktop application and have some basic connection to the database already.

### Plans for the Week

I would like to have the design in place and be able to format program elements on a style sheet. Part of the reason why I wanted to write the program in Java is because then I could use Bootstrap for the Desktop application, the plugin and the WordPress theme. But now I have to go with that.

I'll report back tomorrow with further developments.