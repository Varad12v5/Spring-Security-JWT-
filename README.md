# Spring Security JWT Implementation

This project demonstrates a robust implementation of JWT (JSON Web Token) authentication using Spring Security 6 and Spring Boot 3.

## Features

- JWT-based authentication
- Role-based authorization
- Secure password encoding
- Token-based user session management
- MySQL database integration
- RESTful API endpoints

## Technologies Used

- Spring Boot 3.x
- Spring Security 6
- JSON Web Token (JWT)
- MySQL
- Maven
- Java 17
- Lombok
- JPA/Hibernate

## Project Structure

```
src/main/java/com/example/Spring/Security/JWT/
├── config/
│   ├── ApplicationConfig.java
│   ├── JwtAuthenticationFilter.java
│   └── SecurityConfig.java
├── controller/
│   └── AuthController.java
├── service/
│   ├── AuthenticationService.java
│   └── JwtService.java
├── repository/
│   └── UserRepo.java
├── user/
│   ├── User.java
│   └── Role.java
└── SpringSecurityJwtApplication.java
```

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven
- MySQL

### Configuration

1. Clone the repository:
```bash
git clone [https://github.com/Varad12v5/Spring-Security-JWT-.git]
```

2. Configure MySQL database in `application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/jwt_security
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=create-drop
```

3. Build the project:
```bash
mvn clean install
```

### Running the Application

```bash
mvn spring-boot:run
```

## API Endpoints

### Authentication

- **Register User**
  - POST `/api/v1/auth/register`
  ```json
  {
    "firstname": "John",
    "lastname": "Doe",
    "email": "john.doe@example.com",
    "password": "password123"
  }
  ```

- **Login**
  - POST `/api/v1/auth/authenticate`
  ```json
  {
    "email": "john.doe@example.com",
    "password": "password123"
  }
  ```

### Protected Endpoints

All other endpoints require a valid JWT token in the Authorization header:
```
Authorization: Bearer your_jwt_token
```

## Security Implementation

- Uses `HS256` algorithm for JWT signing
- Implements stateless session management
- Secures endpoints with role-based authorization
- Password encryption using BCrypt
- JWT token validation on each request
- Custom authentication filter for token processing

## Contributing

Feel free to submit issues and enhancement requests!


