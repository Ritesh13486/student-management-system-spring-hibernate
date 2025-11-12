# Online Student Management System

## Project Overview

A Spring Framework and Hibernate ORM-based application for managing students, courses, and fee payments. This project demonstrates dependency injection, CRUD operations, and transaction management.

## Technologies Used

- **Java** (JDK 11+)
- **Spring Framework** (Core, Context)
- **Hibernate ORM**
- **MySQL** (or H2 database)
- **Maven/Gradle** (for dependency management)
- **IntelliJ IDEA / Eclipse** (IDE)

## Features

### 1. Student-Course Management
- Dependency Injection using Spring Java-based configuration
- Student entity depends on Course entity
- Java-based @Configuration and @Bean annotations

### 2. CRUD Operations
- **Create**: Add new students and courses
- **Read**: View all enrolled students or specific student details
- **Update**: Modify student records (name, course, etc.)
- **Delete**: Remove student records
- Implemented using Hibernate sessions and annotated entity classes

### 3. Fee Payment & Refund Management
- Transaction management using @Transactional annotation
- Atomicity ensured for payment and refund operations
- Deduct amount from student balance on payment
- Refund on cancellation with automatic rollback on failure

### 4. Spring + Hibernate Integration
- Layered architecture with DAO, Service, and Main classes
- Hibernate configuration via hibernate.cfg.xml or Java Config
- Spring configuration via AppConfig.java with @Bean

## Project Structure

```
src/main/java/
├── model/
│   ├── Student.java          (Entity)
│   ├── Course.java           (Entity)
│   └── Payment.java          (Entity)
├── dao/
│   └── StudentDAO.java       (Data Access Layer)
├── service/
│   └── FeeService.java       (Service Layer with @Transactional)
├── config/
│   └── AppConfig.java        (Spring Configuration)
└── MainApp.java              (Main class or Controller)

resources/
├── hibernate.cfg.xml         (Hibernate Configuration)
└── application.properties    (Optional)
```

## Database Schema

### students
- student_id (Primary Key)
- name
- course_id (Foreign Key)
- balance

### courses
- course_id (Primary Key)
- course_name
- duration

### payments
- payment_id (Primary Key)
- student_id (Foreign Key)
- amount
- date

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/Ritesh13486/student-management-system-spring-hibernate.git
   cd student-management-system-spring-hibernate
   ```

2. **Configure Database**
   - Update `hibernate.cfg.xml` with your database credentials
   - Create database: `CREATE DATABASE student_management;`

3. **Build the project**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn exec:java -Dexec.mainClass="MainApp"
   ```

## Configuration Files

### hibernate.cfg.xml
Configure database connection, dialect, and entity mappings.

### AppConfig.java
Spring Java-based configuration with @Bean for DAO, services, and entities.

## Key Concepts Demonstrated

- **Dependency Injection**: Spring IoC container manages bean lifecycle
- **ORM Mapping**: Hibernate annotations (@Entity, @Id, @Column, @ManyToOne)
- **Transaction Management**: @Transactional ensures ACID properties
- **Layered Architecture**: Separation of concerns (DAO, Service, Controller)

## Usage

The application provides a console-based or web-based interface to:
- Add, view, update, and delete students
- Assign courses to students
- Process fee payments
- Handle refunds with transaction rollback

## Learning Outcomes

- Understanding Spring Framework's Dependency Injection
- Implementing CRUD operations with Hibernate
- Managing transactions in enterprise applications
- Integrating Spring with Hibernate for real-world scenarios

## License

This project is created for educational purposes as part of the CU - Project Based Learning with Java curriculum.

## Author

Ritesh Kumar Vishwakarma
