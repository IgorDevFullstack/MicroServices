# Microservices Architecture — Customer & Product

This project demonstrates a microservices-based backend architecture built with Java 17 and Spring Boot 3, focusing on service isolation, scalability, and clean API design using Docker, PostgreSQL, and Swagger/OpenAPI.

## Overview

The application is composed of two independent microservices, each one with its own database and container, allowing independent deployment, scaling, and versioning.

- Customer Service: responsible for customer management
- Product Service: responsible for product management

## Technologies

Backend:
- Java 17
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- Spring Validation
- Swagger / OpenAPI 3
- Lombok

Database & Infrastructure:
- PostgreSQL
- Docker
- Docker Compose
- pgAdmin 4

## Architecture


Customer Service (8081)
└── PostgreSQL (clientedb)

Product Service (8082)
└── PostgreSQL (produtodb)


Each microservice:
- Has its own database
- Runs in its own container
- Exposes its own REST API and Swagger documentation

## Running the Project

### Prerequisites
- Docker
- Docker Compose
- Git
- (Optional) Maven

### Clone the repository
```bash
git clone https://github.com/your-username/microservices.git
cd microservices
Build and start containers
docker compose build
docker compose up -d
Running containers
Service	Port
customer-service	8081
product-service	8082
postgres-clientes	5433
postgres-produtos	5434
pgadmin	5050
API Documentation

Customer Service: http://localhost:8081/swagger-ui.html

Product Service: http://localhost:8082/swagger-ui.html

API Examples

Create a customer:

curl -X POST http://localhost:8081/customers \
-H "Content-Type: application/json" \
-d '{"name":"Maria Silva","email":"maria@email.com","phone":"11999999999"}'

List products:

curl http://localhost:8082/products
Database Access (pgAdmin)

URL: http://localhost:5050

Login: admin@admin.com

Password: admin

Customer database:

Host: postgres-clientes

Port: 5432

User: postgres

Password: senha

Database: clientedb

Product database:

Host: postgres-produtos

Port: 5432

User: postgres

Password: senha

Database: produtodb

License

This project is open for learning, experimentation, and improvements.
