# 🍕 Food Ordering & Delivery App

A full-stack food ordering and delivery platform built with **React** and **Spring Boot**, featuring secure authentication, real-time order management, integrated payments, and cloud deployment on AWS.

---

## ✨ Features

- **Role-Based Access Control** — Distinct dashboards and permissions for Admin, Customer, and Delivery roles
- **JWT Authentication** — Secure, stateless authentication with token-based authorization
- **Stripe Payment Integration** — End-to-end payment processing with real-time payment status updates
- **Email Notifications** — Automated order confirmation and payment status emails
- **RESTful API** — Clean, well-structured REST endpoints connecting the frontend and backend
- **Cloud Deployment** — Production-ready deployment on AWS with a scalable architecture

---

## 🛠️ Tech Stack

### Frontend
- React
- React Router
- Axios

### Backend
- Java / Spring Boot
- Spring Security (JWT)
- Spring Data JPA
- RESTful APIs

### Database & Cloud
- AWS RDS (relational database for users, orders, and menu items)
- AWS EC2 (application hosting)
- AWS S3 (static asset storage)

### Integrations
- Stripe (payment gateway)
- JavaMailSender / SMTP (email notifications)

---

## 🏗️ Architecture

```
┌─────────────────┐        ┌──────────────────────┐        ┌──────────────┐
│   React Client  │ ──────▶│  Spring Boot REST API │ ──────▶│   AWS RDS    │
│  (EC2 / S3)     │◀────── │  (EC2, JWT Auth)      │        │  (MySQL/PG)  │
└─────────────────┘        └──────────────────────┘        └──────────────┘
                                      │
                          ┌───────────┴───────────┐
                          │                       │
                   ┌──────▼──────┐       ┌────────▼───────┐
                   │   Stripe    │       │  Email Service  │
                   │  Payments   │       │  (SMTP/SES)     │
                   └─────────────┘       └────────────────┘
```

---

## 👥 User Roles

| Role | Capabilities |
|------|-------------|
| **Admin** | Manage menu items, view all orders, manage users |
| **Customer** | Browse menu, place orders, track delivery, manage profile |
| **Delivery** | View assigned orders, update delivery status |

---

## 🚀 Getting Started

### Prerequisites

- Node.js (v18+)
- Java 17+
- Maven
- AWS account (for cloud deployment)
- Stripe account (test mode)

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name/backend

# Configure environment variables
cp src/main/resources/application.example.properties src/main/resources/application.properties
# Fill in your DB credentials, JWT secret, Stripe key, and SMTP settings

# Run the application
./mvnw spring-boot:run
```

### Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
# Add your API base URL and Stripe publishable key

# Start the development server
npm start
```

---

## ⚙️ Environment Variables

### Backend (`application.properties`)

```properties
spring.datasource.url=******************
spring.datasource.username=**************
spring.datasource.password=****************

jwt.secret=your-jwt-secret
jwt.expiration=86400000

stripe.secret.key=sk_test_...

spring.mail.host=***********
spring.mail.username=***********
spring.mail.password=***********
```

### Frontend (`.env`)

```env
REACT_APP_API_BASE_URL=http://localhost:8080/api
REACT_APP_STRIPE_PUBLISHABLE_KEY=pk_test_...
```

---

## ☁️ AWS Deployment

| Service | Usage |
|---------|-------|
| **EC2** | Hosts the Spring Boot backend |
| **RDS** | Managed relational database for users, orders, and menu data |
| **S3** | Stores static frontend assets and media files |

---

## 📸 Screenshots


---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
