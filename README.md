# SangConnect - Blood Donation Platform

## Project Overview
SangConnect is a **web application** designed to modernize and digitalize blood donation processes in Morocco.  

It provides two main interfaces:  
- **Front Office (ReactJS + Spring Boot)**: for general users (donors/requesters) and center managers. Users can view blood requests, participate in donations, and manage their profiles. Center managers can monitor requests and track activities via a dashboard.  
- **Back Office (Spring Boot + Thymeleaf)**: for system administrators, providing full control over users, centers, blood requests, and reporting.

The platform is **secure** (JWT authentication, HTTPS), responsive, and built for reliability and performance.

---

## Architecture & Technologies

| Layer                  | Technology / Tool                     |
|------------------------|--------------------------------------|
| Backend                | Java 17, Spring Boot, Spring Security, JWT |
| Frontend               | ReactJS, TailwindCSS / Bootstrap     |
| Back Office Templates  | Thymeleaf                             |
| Database               | Oracle XE 21c                         |
| Server & Deployment    | Ubuntu, Nginx (React static files), Apache HTTP Server (proxy) |
| Monitoring & Logging   | ELK stack (logs), Grafana & Prometheus (metrics) |

---

## Installation & Setup

### Prerequisites
- Git  
- Node.js (18+) and npm  
- Java 17  
- Maven  
- Oracle XE 21c  

---

### 1. Clone the repository
```bash
git clone https://github.com/username/SangConnect.git
cd SangConnect
```
The repository contains three main folders:

- front-office-react

- front-office-api

-  back-office

### 2. Configure the database

Create Oracle XE database if not already available.

Run SQL scripts in database-scripts/ to create tables and initial data.

Update backend configuration (application.properties):
``` bash
spring.datasource.url=jdbc:oracle:thin:@localhost:1521:XE
spring.datasource.username=YOUR_DB_USERNAME
spring.datasource.password=YOUR_DB_PASSWORD
```

### 3. Start the backend
``` bash
cd back-office
mvn clean install
mvn spring-boot:run
```
The backend will run on port 8081 by default.

### 4. Start the frontend
``` bash
cd front-office-react
npm install
npm start
```
The frontend will be accessible at http://localhost:3000
.

⚠ Ensure the backend is running first, so the frontend can interact with APIs.
``` bash
cd front-office-api
mvn spring-boot:run
```
The backend runs on port 8080 by default.
## Key Features

### Front Office

**User Types:** Simple User (Donor/Requester) and Center Manager

**Common Features:**
- Registration and login with JWT authentication
- View and respond to blood requests
- Update personal profile and manage history of donations/reservations

**Center Manager Dashboard:**
- Monitor requests in their assigned center
- Confirm or reject donations
- View reservation schedules and blood stock
- Generate statistics and reports

### Back Office

**Admin Features:**
- Manage users and center managers
- Manage blood donation centers
- Oversee and filter blood requests
- Generate PDF reports
- Access system logs and monitoring dashboards

### Notifications
- Automated email notifications for eligible donors
- Updates on confirmed requests, reservations, and system alerts

[![Demo](https://raw.githubusercontent.com/SALimanaim18/BloodConnectApp/main/video_Demo/hero.jpeg)](https://raw.githubusercontent.com/SALimanaim18/BloodConnectApp/main/video_Demo/BloodConnect.mp4)


