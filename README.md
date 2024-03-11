
# Overview
This document provides instructions on how to use the Product and Inventory Services. These services are part of the Invento Hub application, which is a microservices-based system for managing products and inventory.

# Prerequisites
- Docker and Docker Compose installed on your machine.
- Postman for testing the APIs (collections under the Postman Folder).

# Getting Started
- Clone the repository containing the <code>docker-compose.yml</code> file.
- Navigate to the directory containing the <code>docker-compose.yml</code> file.
- Run the command <code>docker-compose up -d</code> to start all the services.

# Services
## Redpanda
Redpanda is a Kafka-compatible event streaming platform. This service is used for inter-service communication.

## Console
The console is a user interface for managing and monitoring Redpanda.

## Product Service
The Product Service manages product-related operations. It exposes APIs for creating, updating, and deleting products.

## Inventory Service
The Inventory Service manages inventory-related operations. It listens to the product-create topic to update the inventory when a new product is created.

## Topics
The following topics are used for communication between services:

- product-create: This topic is used when a new product is created.
- product-update: This topic is used when an existing product is updated.
- product-delete: This topic is used when a product is deleted.

# How to Look Up the Topics
You can look up the topics using the Redpanda console. Navigate to the console on your browser by going to http://localhost:8082. From there, you can see the list of topics and their details.

# Database Services
Two PostgreSQL database services are used, one for each of the Product and Inventory services. The connection details are specified in the docker-compose.yml file.

Please note that this setup is intended for development purposes. For production environments, additional configurations for security, scalability, and resilience would be necessary.