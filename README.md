# 🧩 Microservices Architecture — Customer & Product

A modern **microservices-based backend architecture** built with **Java 17** and **Spring Boot 3**, designed to demonstrate service isolation, scalability, and clean API design using **Docker**, **PostgreSQL**, and **Swagger/OpenAPI**.

---

## 📌 Overview

This project consists of **two independent microservices**, each with its **own database**, **own container**, and **independent lifecycle**.

### 🧍 Customer Service
Responsible for **customer management**.

### 📦 Product Service
Responsible for **product management**.

Each service can be **scaled, deployed, and versioned independently**, following microservices best practices.

---

## 🚀 Tech Stack

### 🖥️ Back-end
- Java 17  
- Spring Boot 3.x  
- Spring Web  
- Spring Data JPA  
- Spring Validation  
- Swagger / OpenAPI 3  
- Lombok  

### 🗄️ Database & Infrastructure
- PostgreSQL  
- Docker & Docker Compose  
- pgAdmin 4  

---

## 🏛️ Architecture Diagram


+----------------------+
| Customer Service |
| Port: 8081 |
+---------+------------+
|
v
+----------------------+
| PostgreSQL |
| DB: clientedb |
+----------------------+

+----------------------+
| Product Service |
| Port: 8082 |
+---------+------------+
|
v
+----------------------+
| PostgreSQL |
| DB: produtodb |
+----------------------+


✔ Each microservice has its own database  
✔ Each microservice runs in its own container  
✔ Each microservice exposes its own API and documentation  

---

## 📦 Running the Project

### 1️⃣ Prerequisites
- Docker  
- Docker Compose  
- Git  
- *(Optional)* Maven (to run services outside Docker)

---

### 2️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/microservices.git
cd microservices
3️⃣ Start the Services with Docker 🐳
docker compose build
docker compose up -d
4️⃣ Verify Running Containers
docker ps
Service	Port
customer-service	8081
product-service	8082
postgres-clientes	5433
postgres-produtos	5434
pgadmin	5050
📚 API Documentation (Swagger)
Service	URL
Customer	http://localhost:8081/swagger-ui.html

Product	http://localhost:8082/swagger-ui.html
🧪 API Request Examples
➕ Create Customer
curl -X POST http://localhost:8081/customers \
-H "Content-Type: application/json" \
-d '{"name":"Maria Silva","email":"maria@email.com","phone":"11999999999"}'
📄 List Products
curl http://localhost:8082/products
🗂️ Database Access (pgAdmin)

🌐 URL: http://localhost:5050

👤 Login: admin@admin.com

🔑 Password: admin

Register Databases
🔹 Customer Database

Host: postgres-clientes

Port: 5432

User: postgres

Password: senha

Database: clientedb

🔹 Product Database

Host: postgres-produtos

Port: 5432

User: postgres

Password: senha

Database: produtodb

✅ Project Highlights

Clean microservices architecture

Independent databases per service

Containerized infrastructure

Production-ready API documentation

Scalable and maintainable design

📜 License

This project is open for learning, experimentation, and improvements.
