 🏥 Clinic Management System

A full-stack web application for managing a clinic — patients, doctors, offices, specializations, and appointments.

## 🛠 Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Java 21, Spring Boot 3.4.1 |
| Database | PostgreSQL |
| ORM | Spring Data JPA / Hibernate |
| Frontend | HTML, CSS, Vanilla JavaScript |
| Server | Apache Tomcat (embedded) |

## 📁 Project Structure

```
src/main/java/kigali/clinc/clinicmanagement/
├── config/         → CORS configuration
├── controller/     → REST API controllers
├── domain/         → JPA entities
├── repository/     → JPA repositories (JPQL + derived queries)
├── service/        → Business logic
└── ClinicmanagementApplication.java

src/main/resources/
├── static/
│   ├── index.html  → Frontend UI (single page, 5 tabs)
│   └── app.js      → Frontend API calls and DOM logic
└── application.properties
```

## ⚙️ Configuration

Edit `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/clinic
spring.datasource.username=postgres
spring.datasource.password=123
server.port=8081
```

## 🚀 How to Run

### 1. Prerequisites
- Java 21
- PostgreSQL 16
- Maven (or use `mvnw`)

### 2. Create the database
```sql
CREATE DATABASE clinic;
```

### 3. Run the application
```cmd
mvnw.cmd spring-boot:run
```

### 4. Open in browser
```
http://localhost:8081
```

## 🌐 API Endpoints

### Patients `/api/patients`
| Method | URL | Description |
|--------|-----|-------------|
| POST | `/save` | Add patient |
| GET | `/all` | Get all patients |
| GET | `/{id}` | Get patient by ID |
| PUT | `/update/{id}` | Update patient |
| DELETE | `/delete/{id}` | Delete patient |
| GET | `/by-last-name?lastName=` | Filter by last name |
| GET | `/frequent?min=` | Frequent patients |
| GET | `/of-doctor/{doctorId}` | Patients of a doctor |

### Doctors `/api/doctors`
| Method | URL | Description |
|--------|-----|-------------|
| POST | `/save` | Add doctor |
| GET | `/all` | Get all doctors |
| GET | `/{id}` | Get doctor by ID |
| PUT | `/update/{id}` | Update doctor |
| DELETE | `/delete/{id}` | Delete doctor |
| GET | `/by-specialization?name=` | Filter by specialization |
| GET | `/without-office` | Doctors without office |

### Offices `/api/offices`
| Method | URL | Description |
|--------|-----|-------------|
| POST | `/save` | Add office |
| GET | `/all` | Get all offices |
| PUT | `/update/{id}` | Update office |
| DELETE | `/delete/{id}` | Delete office |
| GET | `/busiest` | Get busiest office |

### Specializations `/api/specializations`
| Method | URL | Description |
|--------|-----|-------------|
| POST | `/save` | Add specialization |
| GET | `/all` | Get all specializations |
| PUT | `/update/{id}` | Update specialization |
| DELETE | `/delete/{id}` | Delete specialization |
| GET | `/unused` | Unused specializations |

### Appointments `/api/appointments`
| Method | URL | Description |
|--------|-----|-------------|
| POST | `/save` | Book appointment |
| GET | `/all` | Get all appointments |
| PUT | `/update/{id}` | Update appointment |
| PUT | `/{id}/status?status=` | Update status |
| DELETE | `/delete/{id}` | Delete appointment |
| GET | `/by-status?status=` | Filter by status |
| GET | `/between?start=&end=` | Filter by date range |
| GET | `/stats/by-status` | Count per status |
| PATCH | `/cancel-day?doctorId=&date=` | Cancel doctor's day |

## 📊 Features

- ✅ Full CRUD for Patients, Doctors, Offices, Specializations, Appointments
- ✅ Filter patients by last name (case-insensitive)
- ✅ Find frequent patients by minimum appointment count
- ✅ Filter doctors by specialization
- ✅ Find doctors without an office
- ✅ Find busiest office by appointment count
- ✅ Filter appointments by status or date range
- ✅ Appointment stats by status
- ✅ Bulk cancel appointments by doctor and date
- ✅ Double booking prevention

## 👤 Author

**evine55** — [https://github.com/evine55](https://github.com/evine55)
