<<<<<<< HEAD
# 💰 Expense Manager Services

This repository contains the backend implementation of the Expense Manager project.
The project was developed as part of an academic course on asynchronous server side development.
The system is implemented using Node.js Express and MongoDB and follows a multi service architecture.

---

## 🧩 Project Overview

The Expense Manager system provides RESTful web services that allow clients to manage users.
Add and retrieve expense records.
Generate monthly expense reports.
Collect and store logs for all HTTP requests.

Each responsibility is handled by a dedicated service.
Each service runs as an independent Express application and is deployed separately.

---

## 🏗 Architecture

The project is structured as a monorepo that contains multiple independent services.

## expense-manager-services
└── src
├── user_service
├── costs_service
├── reports_service
└── logs_service



Each service:
Has its own package.json.
Runs independently.
Is deployed as a separate web service on Render.
Communicates with other services via HTTP.

---

## 🔧 Services

### 👤 User Service

Purpose:
Manages user data.

Main endpoints:
POST /users/api/add  
GET /users/api/all  
GET /users/api/:id  

Live URL:
https://user-services-fqb9.onrender.com

Example:
GET https://user-services-fqb9.onrender.com/users/api/all

---

### 💸 Costs Service

Purpose:
Handles expense records and generates monthly cost reports.

Main endpoints:
POST /costs/api/add  
GET /costs/api/report?userid=&year=&month=  

Live URL:
https://cost-service-1d44.onrender.com

Example:
GET https://cost-service-1d44.onrender.com/costs/api/report?userid=12334&year=2026&month=1

---

### 📊 Reports Service

Purpose:
Stores and serves cached monthly reports.
Implements the computed design pattern to avoid recalculating reports.

Main endpoints:
GET /reports/api/:userid/:year/:month  

Live URL:
https://reports-service.onrender.com

---

### 📝 Logs Service

Purpose:
Centralized logging service for all HTTP requests.

Main endpoints:
POST /logs/api/add  
GET /logs/api/all  

Live URL:
https://log-service-1oo2.onrender.com

---

## 📜 Logging

All services use Pino for structured logging.
Each incoming HTTP request is logged.
Logs are sent asynchronously to the Logs Service.

---

## 🗄 Database

MongoDB Atlas is used as the database.
Each service connects independently using environment variables.

Collections:
users  
costs  
reports  
logs  

---

## 🚀 Deployment

Each service is deployed as a separate Render web service.
All services are deployed from this single GitHub repository.
Each Render service is configured with a different root directory.
Services communicate using public Render URLs.

---

## 🛠 Technologies Used

Node.js  
Express.js  
MongoDB Atlas  
Mongoose  
Pino  
REST APIs  
Render  

--
=======

##  Expense Manager – Backend Services

**Expense Manager** is a backend system built using a **microservices architecture** for managing users, expenses, and monthly reports.
The project was developed as part of an academic course on **asynchronous server-side development** using **Node.js, Express, and MongoDB**.

The system exposes **RESTful APIs** and consists of multiple independently deployed services.

---

##  Architecture

The project is structured as a **monorepo** containing several independent services.
Each service runs as a standalone Express application, has its own dependencies, and communicates with other services via HTTP.

```
expense-manager-services/
└── src/
    ├── user_service
    ├── costs_service
    ├── reports_service
    └── logs_service
```

---

##  Services

###  User Service

Manages user data.
Endpoints:

* `POST /users/api/add`
* `GET /users/api/all`
* `GET /users/api/:id`

🔗 [https://user-services-fqb9.onrender.com](https://user-services-fqb9.onrender.com)

---

###  Cost Service

Handles expense records and generates monthly reports.
Endpoints:

* `POST /costs/api/add`
* `GET /costs/api/report?userid=&year=&month=`

🔗 [https://cost-service-1d44.onrender.com](https://cost-service-1d44.onrender.com)

---

###  Reports Service

Caches and serves monthly reports to avoid redundant calculations.
Endpoint:

* `GET /reports/api/:userid/:year/:month`

🔗 [https://reports-service.onrender.com](https://reports-service.onrender.com)

---

###  Logs Service

Centralized service for HTTP request logging.
Endpoints:

* `POST /logs/api/add`
* `GET /logs/api/all`

🔗 [https://log-service-1oo2.onrender.com](https://log-service-1oo2.onrender.com)

---

##  Database

* MongoDB Atlas
* Each service connects independently via environment variables

Collections: `users`, `costs`, `reports`, `logs`

---

##  Technologies

Node.js · Express.js · MongoDB Atlas · Mongoose · Pino · REST · Render

>>>>>>> 4a09232e724607f7cc064e163ac1eb8bcf64d0bc
