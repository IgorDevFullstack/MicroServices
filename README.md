# 🧩 Microservices Architecture — Customer & Product

This project demonstrates a complete **microservices architecture** using **Java 17**, **Spring Boot 3**, **PostgreSQL**, **Docker**, **Swagger/OpenAPI**, and modern backend development best practices.

The application is composed of **two independent services**, each one with its **own database**, deployed and managed separately.

## 🧍 Customer Service
Responsible for **customer management**.

## 📦 Product Service
Responsible for **product management**.

Each service is **isolated, scalable, and independently versioned**.

---

## 🚀 Technologies Used

### Back-end
- Java 17  
- Spring Boot 3.x  
- Spring Web  
- Spring Data JPA  
- Spring Validation  
- Swagger / OpenAPI 3  
- Lombok  

### Database & Infrastructure
- PostgreSQL  
- Docker & Docker Compose  
- pgAdmin 4  

---

## 🏛️ Architecture


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


Each microservice has:
- ✔ Its own database  
- ✔ Its own container  
- ✔ Its own routes and API documentation  

---

## 📦 How to Run the Project

### 1️⃣ Prerequisites
- Docker installed  
- Docker Compose  
- Git  
- (Optional) Maven, if you want to run services outside Docker  

---

### 2️⃣ Clone the repository
```bash
git clone https://github.com/your-username/microservices.git
cd microservices
3️⃣ Start everything with Docker 🐳
docker compose build
docker compose up -d
4️⃣ Check running containers
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
🧪 Request Examples (cURL)
📄 Create Customer
curl -X POST http://localhost:8081/customers \
-H "Content-Type: application/json" \
-d '{"name":"Maria Silva","email":"maria@email.com","phone":"11999999999"}'
📄 List Products
curl http://localhost:8082/products
🗂️ Access Databases via pgAdmin

📌 URL: http://localhost:5050

📌 Login: admin@admin.com

📌 Password: admin

Register the servers:
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

✅ Summary

This project showcases a clean and scalable microservices architecture, emphasizing service isolation, independent databases, containerization, and clear API documentation using Swagger/OpenAPI.
