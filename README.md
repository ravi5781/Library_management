# 📚 Library Management System (Console-Based)

A simple **Library Management System** built using **Java** and **MySQL**, designed to run in the console. It helps manage books, members, and book issue/return operations for a small library or institution.

---

## 🛠️ Tech Stack

- **Java (Core Java)**
- **JDBC (Java Database Connectivity)**
- **MySQL**
- **MySQL Connector/J (JDBC Driver)**

---

## 🔰 Features

- ✅ Add New Books  
- ✅ View All Books  
- ✅ Add New Members  
- ✅ View All Members  
- ✅ Issue Book to Member  
- ✅ Return Book  
- ✅ Update Book Availability  
- ✅ Track Due Dates (Manual Entry)

---

## 🗃️ Project Structure

![image](https://github.com/user-attachments/assets/d32c7c4d-c420-4565-9d34-fb78b24a8005)


---

## 📦 Database Setup

1. Open MySQL and create the database using this script:

```sql
CREATE DATABASE library_db;
USE library_db;

CREATE TABLE books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    author VARCHAR(100),
    publisher VARCHAR(100),
    available BOOLEAN DEFAULT TRUE
);

CREATE TABLE members (
    member_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    phone VARCHAR(15)
);

CREATE TABLE issued_books (
    issue_id INT AUTO_INCREMENT PRIMARY KEY,
    book_id INT,
    member_id INT,
    issue_date DATE,
    due_date DATE,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES books(book_id),
    FOREIGN KEY (member_id) REFERENCES members(member_id)
);

---

## 📦 Update MySQL Password
2 Update your MySQL credentials in DBConnection.java:

```sql


java
Copy
Edit
return DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/library_db", "your_username", "your_password");


## add Connector 
3 Add mysql-connector-java JAR to your build path.


📌 Notes
Ensure MySQL server is running.
Date input format: YYYY-MM-DD


👨‍💻 Author
Ravikiran
Email: ravikiransh018@gmail.com
Skills: Core Java, JDBC, MySQL, Eclipse, IntelliJ, VS Code


