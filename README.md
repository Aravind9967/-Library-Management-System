# 📚 Library Management System

A RESTful Library Management System built using **Java, Spring Boot, Spring Security, JWT Authentication, Hibernate, and MySQL**. This project helps manage books, library members, borrowing records, book returns, and overdue fines through REST APIs.

## 🚀 Features

- **JWT Authentication** – Secure login and token-based authentication.
- **Role-Based Authorization** – Separate access for librarians and members.
- **Book Management** – Add, view, update, delete, and search books.
- **Member Management** – Register and manage library members.
- **Borrow Books** – Track book borrowing and due dates.
- **Return Books** – Record returns and calculate overdue fines.
- **Overdue Tracking** – Find borrowed books that have passed their due dates.
- **RESTful APIs** – Organized endpoints for frontend or API client integration.
- **Database Integration** – Persist data using MySQL and Spring Data JPA.
- **Password Encryption** – Protect passwords using BCrypt.
- **Pagination and Search** – Support efficient browsing of book records.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Java 21 | Programming language |
| Spring Boot | Backend application framework |
| Spring Security | Authentication and authorization |
| JWT | Token-based authentication |
| Spring Data JPA | Database operations |
| Hibernate | ORM |
| MySQL | Relational database |
| Maven | Dependency management and build |
| Postman | API testing |
| Eclipse IDE | Development environment |

## 📂 Project Structure

```text
library-management/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/library_management/library_management/
│   │   │       ├── Confg/
│   │   │       ├── Security/
│   │   │       ├── Controller/
│   │   │       ├── Services/
│   │   │       ├── Repositories/
│   │   │       ├── Entity/
│   │   │       ├── DTO/
│   │   │       └── Exceptions/
│   │   └── resources/
│   │       └── application.yml
│   └── test/
├── pom.xml
└── README.md
```

*Note: Adjust the package names in this diagram if your actual project uses different names.*

## ⚙️ Prerequisites

Install the following before running the project:

- Java Development Kit (JDK) 21
- Maven
- MySQL Server
- Eclipse IDE or another Java IDE
- Postman

## 🗄️ Database Configuration

The application uses a MySQL database named `library_db`.

Create the database if you prefer to create it manually:

```sql
CREATE DATABASE library_db;
```

Configure your database and JWT settings in `src/main/resources/application.yml`:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/library_db?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
    username: ${DB_USERNAME:root}
    password: ${DB_PASSWORD}
  jpa:
    hibernate:
      ddl-auto: update

server:
  port: 8081

jwt:
  secret: ${JWT_SECRET}
  expiration: 86400000
```

Set `DB_USERNAME`, `DB_PASSWORD`, and `JWT_SECRET` in your environment before running the application. Use a securely generated JWT secret of at least 32 bytes for HS256. Never commit real credentials or secrets to GitHub.

## ▶️ Run the Application

**1. Clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Replace the URL with your actual GitHub repository URL.

**2. Build the project**

```bash
mvn clean package
```

**3. Run the application**

```bash
mvn spring-boot:run
```

The API server runs at:

`http://localhost:8081`

## 🔐 API Endpoints

Base URL: `http://localhost:8081`

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register an account |
| POST | `/api/auth/login` | Authenticate and obtain a JWT |
| POST | `/api/books` | Create a book |
| GET | `/api/books` | List books |
| GET | `/api/books/{id}` | Get a book by ID |
| GET | `/api/books/search?keyword=java` | Search books |
| PUT | `/api/books/{id}` | Update a book |
| DELETE | `/api/books/{id}` | Delete a book |
| POST | `/api/members` | Create a member |
| GET | `/api/members` | List members |
| POST | `/api/borrow-records` | Borrow a book |
| PUT | `/api/borrow-records/{id}/return` | Return a book |
| GET | `/api/borrow-records/overdue` | List overdue records |

*Protected endpoints require a valid JWT and the appropriate role. Confirm the endpoint paths against your controllers.*

## 🧪 Testing with Postman

1. Start the Spring Boot application and MySQL.
2. Register an account using `/api/auth/register`.
3. Log in using `/api/auth/login`.
4. Copy the JWT returned by the login endpoint.
5. For protected requests, add this header:

```http
Authorization: Bearer YOUR_JWT_TOKEN
```

6. Test book operations, member management, borrowing, returns, and overdue records.

## 🔒 Security

- JWT-based authentication.
- Role-based access control.
- BCrypt password hashing.
- Stateless session management.
- Protected API endpoints.

Public registration should assign the `MEMBER` role on the server. Librarian privileges should only be granted through a trusted administrative process.

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

- Building REST APIs using Spring Boot.
- Implementing JWT authentication with Spring Security.
- Designing entity relationships using JPA and Hibernate.
- Integrating MySQL with a Java backend.
- Applying role-based authorization.
- Handling book borrowing, returns, and overdue fines.
- Testing APIs with Postman.
- Structuring a layered backend application.

## 👨‍💻 Author

**Babbadi Aravind**

Java Developer | Spring Boot | Hibernate | REST APIs

