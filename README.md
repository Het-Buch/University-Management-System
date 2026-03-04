<div align="center">

# 🎓 University Management System

**A professional desktop application for managing university operations — built with Java Swing, powered by SQLite, and distributed as a Windows installer.**

[![Java](https://img.shields.io/badge/Java-8+-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.java.com/)
[![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![Swing](https://img.shields.io/badge/Java%20Swing-GUI-blue?style=for-the-badge&logo=java&logoColor=white)](https://docs.oracle.com/javase/tutorial/uiswing/)
[![License](https://img.shields.io/badge/License-Educational-green?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://www.microsoft.com/windows)

<br/>

[📦 Download Installer](#-running-the-application) · [🚀 Quick Start](#-option-1--installer-recommended) · [💻 Dev Setup](#-development-setup) · [📸 Screenshots](#-screenshots)

</div>

---

## 📖 About

The **University Management System** is a full-featured desktop application that automates day-to-day university administrative tasks — from student registration and faculty management to fee tracking and attendance monitoring.

What makes this project stand out:

- **No external database server required** — SQLite is bundled directly into the application, so there's no MySQL, XAMPP, or any server setup needed
- **Ships as a professional Windows installer** — built with Launch4j and Inno Setup, complete with desktop shortcut, Start Menu entry, and an uninstaller
- **Clean Java Swing UI** — tabbed portals, interactive tables, image-rich forms, and role-based dashboards for both students and faculty

> Built as a practical demonstration of Java desktop application development, JDBC connectivity, and end-to-end software packaging.

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 👨‍🎓 Student Management
- Register new students with full details
- Update and delete student records
- View all students in a searchable table
- Generate student ID cards
- Track attendance with percentage indicators

</td>
<td width="50%">

### 👩‍🏫 Faculty Management
- Faculty registration & login portal
- Faculty attendance tracking
- Dedicated faculty dashboard
- Manage assigned student data

</td>
</tr>
<tr>
<td width="50%">

### 💳 Fees Management
- Record and process fee payments
- View complete payment history per student
- Track pending and cleared dues

</td>
<td width="50%">

### 🔐 Authentication System
- Separate login for students and faculty
- Secure password handling
- Password retrieval functionality
- Role-based access to portals

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **GUI Framework** | Java Swing |
| **Language** | Java 8+ |
| **Database** | SQLite (embedded, no server needed) |
| **DB Connectivity** | JDBC via `sqlite-jdbc` |
| **Table Rendering** | `rs2xml` |
| **Date Picker** | `jcalendar` |
| **Logging** | `slf4j` |
| **JAR → EXE** | Launch4j |
| **Installer** | Inno Setup |

---

## 📂 Project Structure

```
University-Management-System/
│
├── 📦 Downloadable Exe/
│   └── UniversityManagementSystem_Setup.exe   ← Full installer
│
├── 🗄️ Database/
│   └── college.db                              ← SQLite database file
│
├── 📚 lib/                                     ← Required JAR libraries
│   ├── sqlite-jdbc.jar
│   ├── rs2xml.jar
│   ├── jcalendar.jar
│   ├── slf4j-api.jar
│   └── slf4j-simple.jar
│
├── 💻 Source Code/
│   ├── Login.java                              ← App entry point
│   ├── CustomPanel.java                        ← Reusable UI component
│   ├── StudentPortal.java                      ← Student dashboard
│   ├── StudentReg.java                         ← Student registration
│   ├── StudentUpdate.java                      ← Update student info
│   ├── StudentId.java                          ← Student ID card generator
│   ├── FacultyPortal.java                      ← Faculty dashboard
│   ├── FacultyReg.java                         ← Faculty registration
│   └── Fees.java                               ← Fee management
│
├── 🖼️ Images/                                  ← UI assets and icons
├── 📸 Output Preview/                          ← Application screenshots
└── 📄 README.md
```

---

## 🚀 Running the Application

### ✅ Option 1 — Installer (Recommended)

The easiest way. Download and run the setup file:

```
Downloadable Exe/UniversityManagementSystem_Setup.exe
```

The installer will automatically:
- Install the application to your chosen directory
- Create a **Desktop shortcut**
- Add a **Start Menu** entry
- Register an **Uninstaller** in Windows settings

**Steps:**
1. Double-click `UniversityManagementSystem_Setup.exe`
2. Click **Next** through the setup wizard
3. Choose your installation directory
4. Click **Install** → **Finish**
5. Launch from Desktop or Start Menu

---

### ✅ Option 2 — Standalone EXE

If you want to run it without installing:

```
Downloadable Exe/UniversityManagementSystem_Setup.exe
```

Make sure the following files are in the **same folder** as the EXE:

```
📁 UniversityManagementSystem/
├── UniversityManagementSystem.exe
├── college.db
└── lib/
    ├── sqlite-jdbc.jar
    ├── rs2xml.jar
    ├── jcalendar.jar
    └── slf4j.jar
```

Then simply double-click the `.exe` to launch.

---

## 👨‍💻 Development Setup

Want to run or modify the source code? Follow these steps.

### Prerequisites

- **JDK 8 or higher** — [Download here](https://www.oracle.com/java/technologies/downloads/)
- **NetBeans IDE** (recommended) — [Download here](https://netbeans.apache.org/front/main/index.html)
  > IntelliJ IDEA or Eclipse also work fine

---

### Step 1 — Clone the Repository

```bash
git clone https://github.com/Het1014/University-Management-System.git
cd University-Management-System
```

### Step 2 — Open in NetBeans

1. Open **NetBeans**
2. Go to **File → Open Project**
3. Navigate to the cloned folder and select it

### Step 3 — Add Libraries to Project

Right-click the project → **Properties → Libraries → Add JAR/Folder**, then add all JARs from the `lib/` folder:

```
lib/sqlite-jdbc.jar
lib/rs2xml.jar
lib/jcalendar.jar
lib/slf4j-api.jar
lib/slf4j-simple.jar
```

### Step 4 — Set Main Class

Right-click the project → **Properties → Run** → Set Main Class to:

```
Project.Login
```

### Step 5 — Run

Press **F6** or click the green **Run** button.

> ✅ The `college.db` SQLite file will be created automatically on first run if it doesn't exist.

---

### Building a JAR

To compile and package using Ant (NetBeans built-in):

```bash
ant clean jar
```

Output will be in the `dist/` folder. The `lib/` folder inside `dist/` must stay alongside the JAR when distributing.

---

## 📸 Screenshots

All UI screenshots are in the `Output Preview/` folder. Here's what's included:

| Screen | Description |
|---|---|
| 🔑 **Login Page** | Role-based login for Student / Faculty |
| 🏠 **Student Portal** | Full dashboard with attendance & records |
| 🖥️ **Faculty Portal** | Faculty tools and student management |
| 📝 **Registration Forms** | Student and faculty registration |
| 💰 **Fees Module** | Payment recording and history |
| 🪪 **Student ID Card** | Auto-generated ID card view |

---

## 🔮 Future Improvements

- 📊 Attendance analytics with charts
- 📝 Student grade & result management  
- 📄 PDF report generation (report cards, receipts)
- 🔑 Admin super-role with full system control
- 🌐 Web version using Spring Boot + React
- ☁️ Cloud database support (PostgreSQL / Firebase)
- 📱 Android companion app

---

## 📄 License

This project is built for **educational purposes**. Feel free to use it as a reference or learning resource.

---

[![GitHub](https://img.shields.io/badge/GitHub-Het-Buch-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Het-Buch)
