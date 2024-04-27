# PES1UG21CS329_PES1UG21CS331_PES1UG21CS338_PES1UG21CS911-Microservices-communication-using-RabbitMQ

- PES1UG21CS523 - Samarth Hiremath
- PES1UG21CS496 - Rohan Lal
- PES1UG21CS505 - Priyadarshi
- PES1UG21CS533 - Sanjana

This repository contains a containerized microservices-based Inventory Management System that utilizes RabbitMQ for interservice communication. The system is designed to handle various operations such as creating items, managing stock, processing orders, and performing health checks.


## Features
- <b>Microservices Architecture: </b>The system is built using a microservices architecture, with each service responsible for a specific task.
- <b>RabbitMQ Integration:</b> RabbitMQ is used as the message broker for communication between the microservices.
- <b>Docker Containerization:</b> The entire system is containerized using Docker and Docker Compose for easy deployment and scalability.
- <b>MongoDB Integration: </b>MongoDB is used as the database for storing inventory data.
- <b>Flask Web Application: </b>A Flask web application serves as the producer, providing a user interface and API endpoints for interacting with the system.

## Services
The repository contains the following services:

- <b>Producer</b> (```app.py```): A Flask web application that exposes endpoints for various operations such as health checks, creating items, managing stock, and processing orders. This service publishes messages to the appropriate RabbitMQ queues.
- <b>Consumer One</b> (```healthcheck.py```): A consumer service that listens for health check messages from the RabbitMQ queue and performs necessary actions.
- <b>Consumer Two </b>(```insert_record.py```): A consumer service that listens for messages to create new inventory items and inserts them into the MongoDB database.
- <b>Consumer Three</b> (```stock_management.py```): A consumer service that listens for messages to update stock levels and manages the deletion of items from the MongoDB database.
- <b>Consumer Four</b> (```order_processing.py```): A consumer service that listens for messages to retrieve all records from the MongoDB database and sends them back to the producer through RabbitMQ.

## Getting Started
To run the Inventory Management System locally, follow these steps:

1. Navigate to the project directory:
    cd dockerproject

2. Ensure docker engine is running.

3. Build and start the containers:

    docker-compose up

4. Once the containers are up and running, you can access the Flask web application at http://localhost:5000.

