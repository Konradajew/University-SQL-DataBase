# :mortar_board: University-DataBase

## SQL DataBase Project implemented in team:

:man_technologist: Maciej Wiśniewski [mcjwsn](https://github.com/mcjwsn)

:man_technologist: Konrad Szymański [Konradajew](https://github.com/Konradajew)  

:man_technologist: Kajetan Frątczak [KajetanFratczak](https://github.com/KajetanFratczak)

:page_facing_up: Task description: [View PDF](https://github.com/mcjwsn/University-SQL-DataBase/blob/main/task%20description.pdf)


## 📘 Project Assignment Overview

This project involves designing a database system for a company offering various types of courses and training programs. Initially, all services were delivered on-site, but due to the COVID-19 pandemic, many were partially digitized. The current service model is hybrid, though not standardized across all offerings. The system must support three main types of educational services:

---

## 🧩 Offered Services

### **1. Webinars**
- Conducted live on popular cloud platforms; recordings are stored externally (binary data is not stored in the database).
- Webinars can be free or paid. Paid webinars require purchasing access (valid for 30 days).
- Free webinars are publicly accessible.
- All webinars are stored indefinitely unless deleted by an administrator.
- Access requires a user account and, for paid events, confirmed payment.

### **2. Courses**
Short-term paid training programs, typically lasting several days. Completion requires passing at least 80% of modules. Modules may be:
- **On-site** – synchronous, room-based sessions; attendance required.
- **Online synchronous** – live sessions, recorded externally; attendance required.
- **Online asynchronous** – completion based on watching the provided recording (automatic verification).
- **Hybrid** – combination of online and on-site sessions (e.g., 2 recordings + 2 in-person days).

### **3. Studies**
Long-term (multi-year) programs combining online and on-site meetings, plus:
- Mandatory internships (twice a year, 14 days each, full attendance required).
- Final exam.
- Study program (syllabus) must be fixed before the program starts.
- Semester schedules must be known in advance but may change for unforeseen reasons.
- Attendance requirement: min. 80%. Absences may be made up via participation in other similar classes or commercial courses.
- Enrollment is possible for individual study meetings without joining the entire program, with different pricing for non-students.

---

## 💳 Payment System Integration
A fully external payment provider is used (no implementation required). Key rules:

1. Users can add one or more products to a cart; each order generates a payment link.
2. Upon payment completion, the provider returns a success/failed status.
3. Webinar access requires full payment (even immediately before the event).
4. Course participation requires:
   - A deposit at registration.
   - Full payment no later than 3 days before the course starts.  
     (Full payment upfront is also allowed.)
5. Studies require:
   - An enrollment fee (varies by program).
   - Payment for each meeting block, no later than 3 days before it starts.
6. Exceptions to any rule (3–5) may be granted individually by the Director (e.g., deferred payment for loyal customers).

---

## 📊 Reporting Requirements
The system should support frequently used reports via SQL views:

1. Financial reports – revenue summary per webinar/course/study program.
2. List of “debtors” – users who used services but have not paid.
3. Overall report on the number of registered users for upcoming events, including on-site/online mode.
4. Attendance statistics for completed events.
5. Attendance list for each training session (date, participant name, presence status).
6. Collision report – users registered for at least two upcoming events that overlap in time.

---

## 📚 Additional Rules & Constraints
- All training types are conducted by an assigned lecturer and in a specific language.
- Some programs include real-time translation; information about the translator must be stored.
- Webinars and online courses have unlimited capacity. Hybrid and on-site courses have limited seats (varies).
- Study programs have a maximum number of students, which cannot exceed the smallest capacity among their scheduled meetings.
- Participants receive a diploma upon completing a course or study program; it must be physically mailed to the provided address.

---

## 📝 Required Project Components

### **System Functionality**
- List of system functions with assigned user roles and permissions.

### **Database Design**
- Full database schema.
- SQL definition of all tables (DDL).
- Data generation scripts.
- Integrity constraints:  
  default values, allowed ranges, uniqueness, nullability, composite constraints.

### **Views**
- Views that simplify data access for users.
- Views supporting required reports.

### **Data Operations**
- Stored procedures, triggers, and functions:
  - Procedures for data entry & configuration updates.
  - Functions returning key quantitative information.
  - Triggers ensuring consistency and meeting client requirements.

### **Indexes**
- Proposal and definition of indexing strategy.

### **Permissions**
- Roles and their access rights to tables, views, and procedures.

---

## 🛠️ Technology
The project must be implemented using **Microsoft SQL Server**.

---

### :file_folder: Project Structure  

:file_folder: **`/raports`** – Reports from database development steps  

:file_folder: **`/diagram`** – Database schema (.png & .svg)  

:file_folder: **`/SQL Code`** – SQL scripts:  
- :scroll: **`DDL Code.sql`** – Database schema (DDL)  
- :scroll: **`Functions.sql`** – Defined functions  
- :scroll: **`Indexes and Permission.sql`** – Indexes & permissions  
- :scroll: **`Procedures.sql`** – Stored procedures  
- :scroll: **`Views.sql`** – Database views  
- :scroll: **`Triggers.sql`** – Triggers  

:snake: **`data_generator.py`** – Python script for generating test data  

---

## 📊 Database Diagram

<p align="left">
  <img src="diagram/Database_diagram.png" alt="Database Diagram" width="1200">
</p>

