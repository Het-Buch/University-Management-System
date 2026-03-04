# 🎓 University Management System  
A complete desktop-based **Java Swing + JDBC** application for managing university operations such as students, faculty, courses, departments, fees, and administration.  
This system connects to a **MySQL database (via XAMPP & phpMyAdmin)** and provides a clean, interactive UI for real-time data management.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [End-to-End Execution Guide](#end-to-end-execution-guide)
  - [Prerequisites](#prerequisites)
  - [Start XAMPP & phpMyAdmin](#start-xampp--phpmyadmin)
  - [Create Database & Tables](#create-database--tables)
  - [Configure JDBC](#configure-jdbc)
  - [Import Project in NetBeans / Eclipse](#import-project-in-netbeans--eclipse)
  - [Add MySQL Connector](#add-mysql-connector)
  - [Run the Project](#run-the-project)
  - [Troubleshooting](#troubleshooting)
- [Screenshots](#screenshots)
- [Output Preview](#output-preview)
- [Future Improvements](#future-improvements)
- [License](#license)
- [Author](#author)

---

## 🧠 Overview
The University Management System is a **Java Swing GUI** application that automates core university tasks like student management, faculty assignment, department records, fees, and authentication.  
It demonstrates:
- JDBC connectivity  
- CRUD operations  
- GUI programming  
- Database-driven workflows  

---

## ✨ Features
### 👨‍🎓 Student Module
- Add, update, delete students  
- View student list in table format  
- Assign departments & courses  

### 👩‍🏫 Faculty Module
- Add / update faculty  
- Assign departments  
- View faculty list  

### 🏛 Department & Course Management
- Manage departments  
- Add/view courses & subjects  

### 💳 Fees Management
- Add fee records  
- View payment history  

### 🔐 Login System
- Admin login  
- Credential validation  

### 🎨 User Interface
- Java Swing Windows  
- Buttons, tables, forms  
- Image-based UI components  

---

## 🛠 Tech Stack
- **Java Swing** (Frontend UI)  
- **JDBC** (Database connection)  
- **MySQL** (Database)  
- **XAMPP** (Local server + phpMyAdmin)  
- **MySQL Connector/J** (Driver)

---

## 📂 Project Structure
```
University-Management-System/
│
├── Images/                   # Icons, logos, UI graphics
├── Output Preview/           # Screenshots of all frames (Swing UI)
├── Source Code/              # Complete Java source code
│   ├── CustomPanel.java
│   ├── FacultyPortal.java
│   ├── FacultyReg.java
│   ├── Fees.java
│   ├── Login.java
│   ├── StudentId.java
│   ├── StudentPortal.java
│   └── StudentReg.java
│   └── StudentUpdate.java
│
└── README.md
```

---

# 🚀 End-to-End Execution Guide

## ✅ Prerequisites
Install the following:
- **JDK 8+**
- **XAMPP** (MySQL + phpMyAdmin)
- **NetBeans (recommended)** or **Eclipse / IntelliJ**
- **MySQL Connector/J** (JDBC driver)
- Git (optional)

---

## 1️⃣ Start XAMPP & phpMyAdmin
1. Open **XAMPP Control Panel**
2. Start **Apache**  
3. Start **MySQL**
4. Open phpMyAdmin:
   ```
   http://localhost/phpmyadmin/
   ```

---

## 2️⃣ Create Database & Tables
### Step 1: Create database
Inside phpMyAdmin → Databases → Create:
```
university
```

### Step 2: Create tables manually  
Use phpMyAdmin → university → SQL → Paste your SQL schema.

📌 **Note:**  
If you provide your schema, I will generate the full `schema.sql` file for you.

---

## 3️⃣ Configure JDBC
Edit `ConnectionProvider.java`:

```java
public class ConnectionProvider {
    public static Connection getCon() {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/university?useSSL=false&serverTimezone=UTC",
                "root",
                ""  // Default XAMPP password
            );
            return con;
        } catch (Exception e) {
            JOptionPane.showMessageDialog(null, e);
            return null;
        }
    }
}
```

If your MySQL password is not empty, update the 3rd argument.

---

## 4️⃣ Import Project in NetBeans / Eclipse

### 📌 NetBeans (recommended)
1. Open NetBeans → File → Open Project  
2. Select folder **University-Management-System**
3. If project isn't recognized:
   - Create New Java Project
   - Copy **Source Code/** files into `src/`

### 📌 Eclipse
1. File → Import → Existing Project  
OR  
Create new Java project → paste files into `src/`

---

## 5️⃣ Add MySQL Connector/J

### NetBeans
```
Right-click Project → Properties → Libraries → Add JAR/Folder → select mysql-connector.jar
```

### Eclipse
```
Right-click Project → Build Path → Add External JAR → mysql-connector.jar
```

---

## 6️⃣ Run the Project
Choose the main class:
- `ogin.java`

Run using IDE Run button.

---

## 7️⃣ Troubleshooting
### ❌ Driver not found
```
ClassNotFoundException: com.mysql.cj.jdbc.Driver
```
➡ Add MySQL Connector JAR.

### ❌ Database not found
```
SQLException: Unknown database 'university'
```
➡ Create database or correct URL.

### ❌ Access denied
Check MySQL username/password.

### ❌ MySQL not running
Start MySQL in XAMPP.

---

## 🎯 Output Preview (Swing Frames)
All application screens:  
📁 https://github.com/Het1014/University-Management-System/tree/main/Output%20Preview

---

## 🚀 Future Improvements
- Attendance tracking  
- Student grade management  
- PDF export  
- Role-based login  
- Web version (Spring Boot / JSP)  

---
