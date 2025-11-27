# 🏥 Hospital Management System

The **Hospital Management System (HMS)** is a dynamic and interactive web application designed to manage hospital operations efficiently.  
This system is built using **JDBC, JSP, and Servlet**, following the **MVC architecture** to maintain clean project structure and separation of concerns.

The project supports **two main roles: Admin and User**, featuring authentication, registration, patient record management, user data updates, and a responsive dashboard for monitoring information.

This application can run on **:contentReference[oaicite:0]{index=0}** and uses **:contentReference[oaicite:1]{index=1}** for database interaction with **:contentReference[oaicite:2]{index=2}** or **:contentReference[oaicite:3]{index=3}**.

---

## 🧠 Project Objective

The goal of HMS is to:

- Provide centralized patient and user data handling
- Reduce manual data entry
- Enable role-based secure access
- Maintain real-time updates with the database
- Simplify CRUD operations through a web UI

---

## 🔐 Authentication System

The authentication module ensures secure access using:

- Registration and login using email/username and password
- Session-based access control using `HttpSession`
- Validation directly from database using JDBC queries
- Different dashboards and access based on role

### ✅ Supported Scenarios

| Scenario | Result |
|---|---|
| New user | Can register and login as **User** |
| Existing user | Can login and view patient data |
| Admin credentials | Redirected to **Admin Dashboard** |
| Invalid login | Shows error message & retry |
| Unauthorized URL access | Blocked by session filter |

---

## 👨‍⚕️ Admin Module

The Admin has full control over the system.

### 🛠 Capabilities

- View all registered users
- Update and delete user records
- Add new patients
- Update and remove patient details
- View full patient list
- Search for patients by ID, name, or email
- View assigned patient data
- Logout and invalidate admin session

### Typical Admin Dashboard Flow

1. Login → Session created
2. Dashboard access granted
3. Manage Users or Patients
4. Perform INSERT / UPDATE / DELETE / VIEW
5. Logout → Session invalidated

---

## 👤 User Module

Provides secure, limited access for hospital users.

### Capabilities

- Register with username, email, and password
- Login using stored database credentials
- View patient-related records
- Logout and invalidate user session
- Cannot access Admin features

---

## 🧾 Patient Management

Patient details stored can include:

- Patient ID (Primary key)
- Full Name
- Age
- Gender
- Disease/Problem description
- Mobile No.
- Address
- Date of admission
- Emergency Contact
- Assigned Doctor (Future-ready field)

---

## 🗄 Database Operations Covered (via JDBC)

| Operation | Table |
|---|---|
| Create | Users, Patients |
| Read | Users, Patients |
| Update | Users, Patients |
| Delete | Users, Patients |
| Filter/Search | Patients |

All DB connections are handled using:

```java
Connection con = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/hospital_db", "root", "password"
);
