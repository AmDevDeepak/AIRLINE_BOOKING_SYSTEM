# Airline Booking System

This project is a backend system for an airline booking platform, designed using a microservices architecture. The system is built with Node.js and Express.js, using MySQL as the database and RabbitMQ for message queuing.

## Microservices

The system consists of the following microservices:

- **Auth Service**: Handles user authentication and authorization.
- **Booking Service**: Manages flight bookings.
- **Flight Service**: Provides flight search functionality.
- **Reminder Service**: Sends reminders and notifications.
- **API Gateway**: Acts as a single entry point.

- [Auth Service](https://github.com/AmDevDeepak/AuthServices): Handles user authentication and authorization.
- [Booking Service](https://github.com/AmDevDeepak/BookingService): Manages flight bookings.
- [Flights and Search Service](https://github.com/AmDevDeepak/FlightsAndSearchService): Provides flight search functionality.
- [Reminder Service](https://github.com/AmDevDeepak/ReminderService): Sends reminders and notifications.
- [API Gateway](https://github.com/AmDevDeepak/API_Gateway): Acts as a single entry point.

## Architecture

### Overview

The architecture of the Airline Booking System is based on microservices, where each service is responsible for a specific piece of functionality. This approach ensures that the system is scalable, maintainable, and can be developed and deployed independently.

### Microservices Breakdown

1. **Auth Service**
    - **Functionality**: Manages user authentication and authorization.
    - **Dependencies**: MySQL for storing user credentials and JWT for token-based authentication.
    - **Technology Stack**: Node.js, Express.js, MySQL, JWT

2. **Booking Service**
    - **Functionality**: Handles flight bookings.
    - **Dependencies**: MySQL for storing booking information and RabbitMQ for queuing reminder tasks.
    - **Technology Stack**: Node.js, Express.js, MySQL, RabbitMQ

3. **Flight Service**
    - **Functionality**: Provides flight search functionality.
    - **Technology Stack**: Node.js, Express.js, MySQL

4. **Reminder Service**
    - **Functionality**: Sends reminders and notifications to users.
    - **Dependencies**: RabbitMQ for receiving tasks from the Booking Service and an email service for sending notifications.
    - **Technology Stack**: Node.js, Express.js, RabbitMQ

5. **API Gateway**
    - **Functionality**: Acts as a single entry point for all microservices.
    - **Dependencies**: Configured with routes to each microservice.
    - **Technology Stack**: Node.js, Express.js

### Inter-Service Communication

- **RabbitMQ**: Used for message queuing between the Booking Service and the Reminder Service. If the Reminder Service is down, tasks are stored in RabbitMQ and processed once the service is up again.
- **HTTP Requests**: Microservices communicate with each other via HTTP requests through the API Gateway.

### Features

- **Search Flights**: Users can search for flights based on different filters.
- **Book Flights**: Registered users can book flights.
- **Classify Flights**: Users can classify and filter flights based on price, departure time, and duration.
- **Flight Notifications**: Users receive email notifications about flights.

## Running the Services

To run the services locally, follow the setup instructions in each repository. Ensure all services are running simultaneously to allow for proper inter-service communication.
