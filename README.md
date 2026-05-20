# 🚨 Incident Report System API

A backend REST API built with **Spring Boot** that simulates an enterprise-level incident management system (like Jira / ServiceNow-lite).
Users can report incidents, and admins can manage, assign, and resolve them.

# 🎯 Project Goal
The goal of this project is to demonstrate:
* REST API development using Spring Boot
* Role-based access control (USER / ADMIN)
* Real-world workflow system (incident lifecycle)
* Clean architecture (Controller → Service → Repository)
* Database relationship modeling
* Backend system design skills

# 🧠 System Overview
Users can:
* Create incident reports
* View their own incidents
* Track incident status
Admins can:
* View all incidents
* Assign incidents to users/admins
* Update incident status
* Manage workflow (OPEN → IN_PROGRESS → RESOLVED → CLOSED)

# ⚙️ Tech Stack
## Backend
* Java 17+
* Spring Boot
* Spring Web (REST API)
* Spring Data JPA
* Spring Validation
## Database
* PostgreSQL

## Build Tool
* Maven

## Security (Optional Upgrade)
* Spring Security
* JWT Authentication

# 🧰 Tools Used
* IntelliJ IDEA / VS Code
* Postman (API testing)
* MySQL Workbench / DBeaver
* Git & GitHub
* Maven

# 🏗️ Project Architecture
com.incident
│
├── controller      → Handles HTTP requests
├── service         → Business logic layer
├── repository      → Database access layer
├── model           → Entity classes (DB tables)
├── dto             → Data transfer objects
├── enums           → Status & Priority types
├── exception       → Custom error handling
└── config          → Security / application config

# 🔁 Incident Workflow

OPEN → IN_PROGRESS → RESOLVED → CLOSED

Each incident follows a strict lifecycle managed by admins.
# 🚀 Features
## 👤 User Features
* Register account
* Login
* Create incident report
* View own incidents
* Add comments (optional)
## 🛠️ Admin Features
* View all incidents
* Assign incidents
* Update incident status
* Filter incidents by status/priority

# 📡 API Endpoints
## Auth
POST /api/auth/register
POST /api/auth/login
## Incidents
POST   /api/incidents              → Create incident
GET    /api/incidents/my           → User incidents
GET    /api/incidents              → Admin view all
GET    /api/incidents/{id}         → Get incident by ID
PUT    /api/incidents/{id}/status  → Update status (ADMIN)
PUT    /api/incidents/{id}/assign  → Assign incident (ADMIN)
## Comments (Optional)
POST /api/incidents/{id}/comments
GET  /api/incidents/{id}/comments
# 🧱 Core Entities
## User
* id
* name
* email
* password
* role (USER / ADMIN)
## Incident
* id
* title
* description
* priority (LOW / MEDIUM / HIGH / CRITICAL)
* status (OPEN / IN_PROGRESS / RESOLVED / CLOSED)
* createdAt
* updatedAt
* user_id
* assigned_to
## Comment (Optional)
* id
* message
* incident_id
* user_id
* createdAt

# 🧪 How to Run the Project
## 1. Clone repository
git clone https://github.com/AndrewSanAntonio1/Incident-Report-System.git
## 2. Configure database
Edit `application.properties`:
spring.datasource.url=jdbc:mysql://localhost:3306/incident_db
spring.datasource.username=root
spring.datasource.password=yourpassword
## 3. Build project
mvn clean install
## 4. Run application
mvn spring-boot:run
## 5. Test API

Use Postman:
http://localhost:8080/api/incidents
# 📈 Future Improvements
* JWT Authentication
* Email notifications (incident updates)
* Pagination & filtering
* Audit logs (who changed what)
* Dashboard analytics
* Docker deployment

# 🧠 What This Project Shows Employers
This project demonstrates:
* Backend system design thinking
* REST API development skills
* Database modeling ability
* Role-based access control
* Clean code architecture
* Real-world workflow understanding

 project sprint (Week 1 → Week 2 plan)
