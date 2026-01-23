
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

