# Gestion Formation 

A Training Management System (Système de Gestion de Formation) built with **Spring Boot**, providing a RESTful API backend to manage trainees, groups, sessions, payments, and attendance.

---

##  Features

- **Trainee Management** — Add, update, and track learners (Apprenants)
- **Group Management** — Organize trainees into groups (Groupes)
- **Session Management** — Schedule and manage training sessions
- **Attendance Tracking** — Record and monitor presence for each session
- **Payment Management** — Track trainee payments and statuses
- **Authentication & Authorization** — JWT-based security with role-based access (Admin, President)
- **CORS Support** — Configured for cross-origin frontend integration

---

##  Tech Stack

| Layer | Technology |
|---|---|
| Language | Java 21 |
| Framework | Spring Boot 3.2.0 |
| Security | Spring Security + JWT (JJWT 0.11.5) |
| ORM | Spring Data JPA / Hibernate |
| Database | MySQL 8 |
| Build Tool | Maven |
| Utilities | Lombok |

---

##  Project Structure

```
gestion/
├── src/main/java/org/example/
│   ├── config/          # Security, JWT, CORS, Admin & President controllers
│   ├── Controller/      # REST controllers (Apprenant, Groupe, Paiement, Presence, Session)
│   ├── DTO/             # Data Transfer Objects
│   ├── Model/           # JPA Entities (Apprenant, Groupe, Formation, Session, Paiement, Presence...)
│   ├── Repository/      # Spring Data JPA repositories
│   └── Main.java        # Application entry point
├── src/main/resources/
│   └── application.properties
└── pom.xml
```

---

##  Prerequisites

- Java 21+
- Maven 3.8+
- MySQL 8+

---

##  Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/BrahimHammouche/Gestion_app.git
cd Gestion_app/gestion
```

### 2. Set up the database

Create the database in MySQL:

```sql
CREATE DATABASE gestion_formation;
```

### 3. Configure the application

Edit `src/main/resources/application.properties` with your MySQL credentials:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/gestion_formation
spring.datasource.username=your_username
spring.datasource.password=your_password
```

### 4. Build and run

```bash
./mvnw spring-boot:run
```

The API will be available at `http://localhost:8080`

---

##  Authentication

The API uses **JWT (JSON Web Token)** for authentication.

1. Register or log in via the `/admin` or `/president` auth endpoints
2. Include the returned token in subsequent requests:

```
Authorization: Bearer <your_token>
```

---

##  API Endpoints

| Resource | Base Path |
|---|---|
| Apprenants (Trainees) | `/api/apprenants` |
| Groupes (Groups) | `/api/groupes` |
| Sessions | `/api/sessions` |
| Présences (Attendance) | `/api/presences` |
| Paiements (Payments) | `/api/paiements` |

---

##  Roles

- **Admin** — Full system access
- **President** — Manages formations, groups, and reports

---

## 📄 License

This project was developed as part of a university assignment.
