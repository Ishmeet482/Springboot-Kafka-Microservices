## 📘 Description

This project implements an event-driven microservices architecture using Spring Boot and Apache Kafka. It's designed to illustrate asynchronous communication between multiple independent services, exemplified through an e-commerce order processing flow.

The application leverages Kafka as a message broker to enable loose coupling, improved flexibility, maintainability, availability, and scalability among services. It features RESTful APIs for triggering events, which are then asynchronously consumed and processed by other microservices. A key component is the use of Data Transfer Objects (DTOs) for seamless data exchange between producers and consumers.

## ⚙️ Prerequisites

1. Java
2. Spring Boot
3. Apache Kafka
4. RESTful API
   
### 📂 Key Components

The project is structured around several microservices, each with a specific role in the event-driven flow:

Order Service: Acts as a Kafka producer, featuring a REST endpoint to receive order requests and publish them as OrderEvent messages to a Kafka topic.

Stock Service: Functions as a Kafka consumer, subscribing to the order topic to process OrderEvent messages and update stock information.

Email Service: Also a Kafka consumer, it listens to the same order topic to send email notifications based on OrderEvent messages.

Base Domains: A shared module containing common DTOs (like Order and OrderEvent) used across all services to ensure consistent data structures.

### 📂 Optional API keys

1. `Add data via rest-client`
   - API URL: http://localhost:8080/api/v1/orders
   - HTTP Method: POST
