# 📅 Date Time Checker

A **Spring Boot** web application that validates whether a given date (Day, Month, Year) is a valid date in the Gregorian calendar.

Built with **Spring Boot 4.0.6**, **Thymeleaf**, and packaged as a **WAR** file. Includes a **GitHub Actions CI/CD** pipeline that automatically builds and tests the project on every push to `main`.

---

## ✨ Features

- Validate any date by entering Day, Month, and Year
- Range validation: Day (1–31), Month (1–12), Year (1000–3000)
- Calendar-aware validation (e.g., Feb 29 only valid in leap years)
- User-friendly success/error messages
- Clean, responsive UI with Thymeleaf templates

---

## 🛠️ Tech Stack

| Layer        | Technology                  |
|--------------|-----------------------------|
| Language     | Java 21                     |
| Framework    | Spring Boot 4.0.6           |
| Template     | Thymeleaf                   |
| Build Tool   | Maven (with Maven Wrapper)  |
| Packaging    | WAR                         |
| CI/CD        | GitHub Actions              |

---

## 📁 Project Structure

```
ci-cd-testing/
├── .github/
│   └── workflows/
│       └── cicd.yml                    # GitHub Actions CI/CD pipeline
├── src/
│   ├── main/
│   │   ├── java/com/trieupk/dateTimeChecker/
│   │   │   ├── DateTimeCheckerApplication.java   # Spring Boot entry point
│   │   │   ├── DateTimeController.java           # Web controller (GET /, POST /check)
│   │   │   ├── DateValidator.java                # Date validation logic
│   │   │   └── ServletInitializer.java           # WAR deployment initializer
│   │   └── resources/
│   │       ├── application.properties            # App configuration
│   │       ├── static/                           # CSS and static assets
│   │       └── templates/
│   │           └── index.html                    # Thymeleaf UI template
│   └── test/                                     # Unit tests
├── pom.xml                                       # Maven project config
├── mvnw / mvnw.cmd                               # Maven Wrapper scripts
└── README.md                                     # This file
```

---

## 🚀 Prerequisites

- **Java 21** (JDK) — [Download](https://adoptium.net/)
- **Maven 3.9+** *(optional — the project includes Maven Wrapper)*

Verify your Java installation:
```bash
java -version
```

---

## ▶️ How to Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/JohnPham666/DateTimeChecker.git
cd DateTimeChecker
```

### 2. Run the application

**On Windows (using Maven Wrapper):**

```cmd
.\mvnw.cmd spring-boot:run
```

**On macOS / Linux:**

```bash
./mvnw spring-boot:run
```

**Or, if you have Maven installed globally:**

```bash
mvn spring-boot:run
```

### 3. Open in browser

Navigate to: [http://localhost:8080](http://localhost:8080)

You will see the Date Time Checker form. Enter a Day, Month, and Year, then click **Check** to validate.

---

## 🧪 How to Run Tests

**On Windows:**

```cmd
.\mvnw.cmd clean test
```

**On macOS / Linux:**

```bash
./mvnw clean test
```

**Or with Maven globally:**

```bash
mvn clean test
```

Test results will be displayed in the terminal output.

---

## 📦 How to Build the WAR File

```bash
.\mvnw.cmd clean package
```

The WAR file will be generated at:

```
target/dateTimeChecker-0.0.1-SNAPSHOT.war
```

You can deploy this WAR to any servlet container (e.g., Tomcat, WildFly).

---

## 🔄 CI/CD Pipeline (GitHub Actions)

The project includes a CI/CD pipeline defined in [`.github/workflows/cicd.yml`](.github/workflows/cicd.yml).

### What it does:

| Step            | Description                            |
|-----------------|----------------------------------------|
| **Trigger**     | On every `push` to the `main` branch   |
| **Environment** | Ubuntu (latest), JDK 21 (Temurin)      |
| **Action**      | Runs `mvn clean test`                  |

### Pipeline Flow:

```
Push to main → Checkout code → Setup JDK 21 → Build & Run Tests
```

If any test fails, the pipeline will fail and you'll see it on the GitHub Actions tab.

---

## 📝 API Endpoints

| Method | Path     | Description                                |
|--------|----------|--------------------------------------------|
| GET    | `/`      | Displays the date input form               |
| POST   | `/check` | Validates the submitted date and shows result |

### POST `/check` Parameters:

| Parameter | Type   | Description       | Example |
|-----------|--------|-------------------|---------|
| `day`     | String | Day of the month  | `29`    |
| `month`   | String | Month of the year | `2`     |
| `year`    | String | Year              | `2024`  |

---

## 📄 License

This project is for educational purposes.

CI/CD demo update

CI/CD demo update
