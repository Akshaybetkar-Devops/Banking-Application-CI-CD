# 🏦 Banking Management System (Java Web Application)

A simple Banking Management System built using Java Servlets, Maven, Apache Tomcat, and MySQL.
The application supports user registration, login, deposit, withdrawal, and balance enquiry.

This project is structured using Maven best practices and follows clean Git version control rules.

THis is the updated file for testing purpose #chnages done by Akshay

---

## 🚀 Features

- User registration with password hashing (SHA-256)
- Secure login with session management
- Deposit money into account
- Withdraw money with balance validation
- View current account balance
- Maven-based WAR deployment
- MySQL database integration

---

## 🛠 Tech Stack

Build Tool  : Maven  
Server      : Apache Tomcat 9  
Database    : MySQL 8  
JDBC Driver : MySQL Connector/J  
Java        : Java 17  

---

## 📁 Project Structure
```
banking-system/
│
├── src/
│ └── main/
│ ├── java/
│ │ ├── util/
│ │ │ ├── DBConnection.java
│ │ │ └── PasswordUtils.java
│ │ └── web/
│ │ ├── LoginServlet.java
│ │ ├── RegisterServlet.java
│ │ ├── DepositServlet.java
│ │ ├── WithdrawServlet.java
│ │ └── BalanceServlet.java
│ │
│ ├── resources/
│ │ └── config.properties
│ │
│ └── webapp/
│ ├── login.html
│ ├── register.html
│ ├── dashboard.html
│ └── WEB-INF/
│ └── web.xml
│
├── pom.xml
├── .gitignore
└── README.md
```

---

## 🗄 Database Schema

```sql
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    email VARCHAR(50) UNIQUE,
    balance DOUBLE,
    role VARCHAR(12),
    password VARCHAR(256)
);
```
⚙ Configuration

Create the file:

src/main/resources/config.properties


Add the following content:
```
db.url=jdbc:mysql://localhost:3306/banking_system?useSSL=false&serverTimezone=UTC&allowPublicKeyRetrieval=true
db.username=root
db.password=YOUR_PASSWORD
```
▶ How to Run the Project
1️⃣ Prerequisites

Java 17 installed

Maven installed

MySQL running

Apache Tomcat 9 installed

2️⃣ Build the Project
mvn clean package

3️⃣ Deploy to Tomcat

Copy the generated WAR file:

target/banking-system-1.0.war


to:

apache-tomcat-9/webapps/

Start Tomcat:
startup.bat

4️⃣ Access the Application
http://localhost:8080/banking-system-1.0/login.html


🔐 Security Notes

Passwords are stored using SHA-256 hashing

Database credentials are externalized

Sessions prevent unauthorized access

Build artifacts are excluded using .gitignore

📌 Key Learnings

Java Servlet lifecycle

JDBC database connectivity

Maven-based project structure

Session handling

Git version control best practices

📈 Future Enhancements

Transaction history feature

JSP-based UI rendering

DAO and Service layer refactoring

REST API implementation

👤 Author

Manikanta
Java Full Stack Developer (Fresher)

⭐ If you like this project, feel free to star the repository.

## Example
<img width="771" height="476" alt="Screenshot 2025-09-21 164233" src="images/Screenshot 2026-01-11 122703.png" />

<img width="764" height="250" alt="image" src="[https://github.com/user-attachments/assets/d9710af5-9bea-4adc-a8f3-e3c224de319a](https://github.com/mani180473/banking-Management-system/blob/main/images/Screenshot%202026-01-11%20122720.png)" />

<img width="771" height="476" alt="Screenshot 2025-09-21 164233" src="[images/Screenshot 2026-01-11 122703.png](https://github.com/mani180473/banking-Management-system/blob/main/images/Screenshot%202026-01-11%20122733.png)" />

<img width="771" height="476" alt="Screenshot 2025-09-21 164233" src="https://github.com/mani180473/banking-Management-system/blob/main/images/Screenshot%202026-01-11%20122741.png" />
<img width="771" height="476" alt="Screenshot 2025-09-21 164233" src="[images/Screenshot 2026-01-11 122703.png](https://github.com/mani180473/banking-Management-system/blob/main/images/Screenshot%202026-01-11%20122756.png)" />
<img width="771" height="476" alt="Screenshot 2025-09-21 164233" src="[images/Screenshot 2026-01-11 122703.png](https://github.com/mani180473/banking-Management-system/blob/main/images/Screenshot%202026-01-11%20122805.png)" />
