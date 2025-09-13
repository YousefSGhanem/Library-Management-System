# LibraryManagementSystem

**Short Description**: The Library Management System is a Java application with a graphical user interface (GUI) that digitalizes and simplifies library processes such as book management, student registration, issuing, and returning books. It combines a user-friendly interface with a MySQL database to ensure up-to-date information at all times.

---

## Table of Contents

* [Overview](#overview)
* [Main Features](#main-features)
* [Technologies](#technologies)
* [Architecture](#architecture)
* [Database Model](#database-model)
* [Scenarios](#scenarios)
* [Installation & Execution](#installation--execution)
* [Poster](#poster)
* [Future Work](#future-work)
* [Team & Project Management](#team--project-management)
* [License](#license)

---

## Overview

This system was developed as a university project to automate the workflows of a university library. Instead of manual record keeping, it allows:

* Students: Log in, search for books, check available copies, view issued books.
* Admins: Register students, add new books, manage issuing & returning, view statistics, and create additional admin accounts.

Motivation: A digital solution improves organization, reduces errors, saves time, and makes access to books more efficient.

---

## Main Features

* Login System: Role-based (Admin/Student)
* Student Management: Register, search, delete
* Book Management: Add, view catalog, search, delete
* Issue & Return: Manage specific book copies, update return status
* Statistics: Overview of issued & returned books
* Security: Passwords hashed with BCrypt, SQL injections prevented using PreparedStatements

---

## Technologies

* Programming Language: Java (JDK)
* IDE: Apache NetBeans
* GUI: Java Swing, AbsoluteLayout
* Database: MySQL, JDBC Connector
* Libraries: JCalendar, rs2xml, BCrypt
* Tools: GitHub (Version control), Microsoft Teams (Collaboration), Figma (Poster/Design), LaTeX (Documentation)

---

## Architecture

The system is based on a two-role architecture:

```
Student: Login → Book Catalog → Issued Books Overview
Admin: Login → Dashboard → (Students | Books | Issue | Return | Statistics)
```

Key Classes:

* Login, StudentLogin, NewStudent, StudentInfo
* NewBook, Catalogue, StudentBookCatalogue
* IssueBook, ReturnBook
* Statistics, NewAdmin

---

## Database Model

The MySQL relational schema consists of five main tables:

* Admins (Admin data)
* Students (Student data, course, branch)
* Books (Title, Author, ISBN, Year, Total Copies)
* Copies (Concrete book copies)
* Issues (Issued books: Student ID, ISBN, issue date, return status)

Relationships:

* Student ↔ Issues (1\:n)
* Book ↔ Copies (1\:n)
* Copies ↔ Issues (1\:n)
* Book ↔ Issues (n\:m)

---

## Scenarios

**Admin** can:

* Log in
* Register, search, and delete students
* Add, search, and delete books
* Manage issuing and returning of books
* View statistics
* Create new admin accounts

**Student** can:

* Log in (with last name & student ID)
* Search books in the catalog
* View own issued books

---

## Installation & Execution

### Requirements

* Java Development Kit (JDK)
* Apache NetBeans (or another IDE)
* MySQL Database

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/YousefSGhanem/LibraryManagementSystem.git
   cd LibraryManagementSystem
   ```
2. Create a MySQL database and set up the required tables (see [mysql\_tables.txt](LibraryManagementSystem-main/University-java-project/docs/mysql_tables.txt)).
3. Open the project in NetBeans and build the project.
4. Set your JDBC connection details (username, password, DB name) in the code.
5. Start the program → Login as Admin.

### Login Information

* Admin Login
  Username: `admin`
  Password: `admin`

* Student Login
  Students need to be registered by an admin.

---

## Poster

A visual poster with all core features and a project overview is available in this repository:

* [Poster (PDF)](LibraryManagementSystem-main/University-java-project/docs/Poster.pdf)

---

## Team & Project Management

* Process model: Agile / Scrum
* Development phases: Planning → Implementation → Testing → Review → Release
* Tools: GitHub (Code), MS Teams (Communication), Figma (Design), LaTeX (Documentation)

---

## License

This project is a university learning project and is intended for demonstration purposes only.
