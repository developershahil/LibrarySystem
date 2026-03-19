# 📚 Library Management System

A simple and functional web-based Library Management System built with **ASP.NET Web Forms (C#)**. This system allows administrators to manage books, students, branches, book issues, and returns efficiently.

---

## 🚀 Features

- 📘 Add and manage books
- 🎓 Add student information
- 🏢 Manage library branches
- 📤 Issue books to students
- 📥 Return books
- 📊 Generate book and issue reports
- 🏠 Admin home dashboard

---

## 🛠️ Tech Stack

- **Frontend**: ASP.NET Web Forms (.aspx)
- **Backend**: C# (.aspx.cs)
- **IDE**: Visual Studio
- **Database**: SQL Server

---

## 📂 Project Structure

```
LibrarySystem/
├── Addbook.aspx & Addbook.aspx.cs
├── Addbranch.aspx & Addbranch.aspx.cs
├── AddStudent.aspx & AddStudent.aspx.cs
├── BookIssue.aspx & BookIssue.aspx.cs
├── BookReturn.aspx & BookReturn.aspx.cs
├── bookreport.aspx & bookreport.aspx.cs
├── Issuereport.aspx & Issuereport.aspx.cs
├── Home.aspx & Home.aspx.cs
├── Default.aspx & Default.aspx.cs
├── LibrarySystem.sln
└── ...
```

---

## 🗄️ Database Schema (Sample)

You can create the following tables in SQL Server:

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY IDENTITY,
    Name NVARCHAR(100),
    Branch NVARCHAR(50),
    Email NVARCHAR(100)
);

CREATE TABLE Books (
    BookID INT PRIMARY KEY IDENTITY,
    Title NVARCHAR(100),
    Author NVARCHAR(100),
    ISBN NVARCHAR(50),
    Quantity INT
);

CREATE TABLE Branches (
    BranchID INT PRIMARY KEY IDENTITY,
    BranchName NVARCHAR(100)
);

CREATE TABLE BookIssues (
    IssueID INT PRIMARY KEY IDENTITY,
    StudentID INT FOREIGN KEY REFERENCES Students(StudentID),
    BookID INT FOREIGN KEY REFERENCES Books(BookID),
    IssueDate DATE,
    ReturnDate DATE,
    Status NVARCHAR(20)
);
```

---

## 🔧 How to Run

1. **Open in Visual Studio**  
   Launch the `.sln` file in Visual Studio.

2. **Create a fresh SQL Server database**  
   - Open `Database/LibrarySystem.Fresh.sql` in SQL Server Management Studio.
   - Run the script to recreate the `LibrarySystem` database, tables, indexes, stored procedures, and a default admin login.
   - Default admin credentials created by the script: **`admin` / `admin123`**.

3. **Configure the connection string**  
   - Open `Web.config` and update `LibrarySystemConnectionString` so `Data Source` points to your SQL Server instance.
   - Keep `Initial Catalog=LibrarySystem`.

4. **Build and Run**  
   Press `F5` or click "Start" in Visual Studio to run the app locally.

---

## 📝 Author

- **Developed by:** Rathod Sahil  
- 📧 Email: sahilrathod222@gmail.com