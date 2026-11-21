# OOSE Semesta

A Spring Boot web app with a login/registration page and semester → subject → unit navigation (OOSE).

## Tech stack
- Java 21
- Spring Boot 4.0.5 (Web, Thymeleaf, Data JPA)
- MySQL

## Prerequisites
- JDK 21
- MySQL running locally with a database named `login_db`:
  ```sql
  CREATE DATABASE login_db;
  ```

## Configuration
Database settings are read from environment variables (defaults in brackets):

| Variable | Default |
|---|---|
| `DB_URL` | `jdbc:mysql://localhost:3306/login_db` |
| `DB_USERNAME` | `root` |
| `DB_PASSWORD` | *(empty)* |

Windows (PowerShell):
```powershell
$env:DB_PASSWORD="your_password"
```
macOS/Linux:
```bash
export DB_PASSWORD="your_password"
```

## Run
```bash
cd sampleapp
./mvnw spring-boot:run        # Windows: .\mvnw.cmd spring-boot:run
```
Then open http://localhost:8080

## Routes
| Method | Path | Purpose |
|---|---|---|
| GET | `/` | Login page |
| POST | `/login` | Log in |
| POST | `/register` | Register |
| GET | `/home` | Home |
| GET | `/semester/{sem}` | Semester page |
| GET | `/subject/oose` | OOSE subject page |
| GET | `/unit1` | Unit 1 |

## Tests
```bash
cd sampleapp
./mvnw test
```
> Tests need a reachable MySQL database (see Configuration).
