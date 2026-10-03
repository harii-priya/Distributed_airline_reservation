# Airline Reservation System

A web-based airline reservation and administration application built with **Spring Boot**, **React**, and **MySQL**. It allows users to browse airports and flights, manage flight information, and create or cancel reservations through a web interface.

## Features

- **Airport Management** – View airport information and manage airport records.
- **Flight Management** – Add, view, update, and manage flight details.
- **Flight Search** – Browse available flights and review departure, arrival, destination, and seat information.
- **Booking Management** – Create reservations and view booking details.
- **Cancellation** – Cancel reservations and update booking status.
- **REST API** – Spring Boot backend endpoints connect the frontend to the database.
- **Relational Database** – MySQL stores airport, flight, and booking data.

## Technologies Used

| Layer | Technology |
|---|---|
| Frontend | React, JavaScript, HTML, CSS, Bootstrap |
| Backend | Java, Spring Boot |
| Database | MySQL |
| ORM / Persistence | Spring Data JPA, Hibernate |
| Build Tool | Maven |
| API Style | REST |

## Project Structure

```text
airline-reservation-system/
├── src/
│   ├── main/
│   │   ├── java/              # Spring Boot application and backend code
│   │   └── resources/
│   │       └── application.yaml
│   └── test/                  # Backend tests
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/        # React components
│   │   └── services/          # API service functions
│   └── package.json
├── pom.xml
└── README.md
```

## Prerequisites

Install the following before running the project:

- Java JDK compatible with the version configured in `pom.xml`
- Apache Maven (or use the Maven wrapper if included)
- Node.js and npm
- MySQL Server and MySQL Workbench (Workbench is optional)
- Git (optional, for cloning the repository)

## Setup and Installation

### 1. Clone the repository

```bash
git clone <YOUR_GIT_REPOSITORY_URL>
cd airline-reservation-system
```

Replace `<YOUR_GIT_REPOSITORY_URL>` with your repository URL.

### 2. Create the MySQL database

Open MySQL Workbench and execute:

```sql
CREATE DATABASE IF NOT EXISTS ars_db;
```

### 3. Configure the backend database connection

Open `src/main/resources/application.yaml` and configure the datasource to match your local MySQL credentials:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/ars_db
    username: YOUR_MYSQL_USERNAME
    password: YOUR_MYSQL_PASSWORD
    driver-class-name: com.mysql.cj.jdbc.Driver
```

Keep any existing application settings in the file, including the server port and JPA configuration. **Do not commit real database passwords or other secrets to a public repository.**

### 4. Run the Spring Boot backend

From the project root (the directory containing `pom.xml`), run:

```bash
mvn spring-boot:run
```

If the Maven wrapper is included, you can use the appropriate wrapper command for your operating system instead.

The backend is configured to use port **8080**. If that port is already occupied, stop the other process or update the configured server port.

### 5. Install frontend dependencies

Open a second terminal and move into the frontend directory:

```bash
cd frontend
npm install
```

### 6. Start the React frontend

```bash
npm start
```

The React development server typically runs at:

```text
http://localhost:3000
```

Keep both the backend and frontend terminals running while using the application.

## Configuration Notes

- Ensure MySQL Server is running before starting the backend.
- The database username and password in `application.yaml` must match your local MySQL account.
- If the frontend cannot communicate with the backend, check the API base URL in the frontend service files and confirm that the backend is running.
- If Maven tests fail during startup, inspect the test report and resolve the reported database or configuration issue. For local troubleshooting only, Maven can run the application without executing tests using `mvn spring-boot:run` (this command does not run the test phase).

## Future Improvements

- User authentication and role-based access control
- Improved search and filtering for flights
- Booking history and printable booking confirmations
- Input validation and clearer error messages
- Automated backend and frontend tests

## License

No license has been specified yet. Add a `LICENSE` file if you intend to distribute the project under a particular open-source license.
