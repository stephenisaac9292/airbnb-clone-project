# Airbnb Clone - Backend Documentation

## Project Overview

This project is a backend implementation of an Airbnb-like system that allows users to register, list properties, make bookings, leave reviews, and manage payments. The goal is to create a robust, secure, and scalable backend system with a well-structured database and continuous deployment pipeline.

---

## Team Roles

- **Backend Developer**  
  Responsible for building RESTful APIs, implementing business logic, and integrating third-party services.

- **Database Administrator (DBA)**  
  Manages database structure, ensures data integrity, handles migrations, and optimizes performance.

- **DevOps Engineer**  
  Sets up CI/CD pipelines, manages deployment infrastructure, and ensures system reliability.

- **Project Manager**  
  Coordinates tasks, monitors progress, manages communication among team members, and ensures timely delivery.

- **Quality Assurance (QA) Engineer**  
  Tests application functionality, writes automated tests, and ensures that all features work as expected.

---

## Technology Stack

- **Django**: A Python web framework used to build RESTful APIs and manage backend logic.
- **PostgreSQL**: A powerful relational database used to store and manage structured data.
- **GraphQL**: A query language for APIs that allows clients to request exactly the data they need.
- **Docker**: Used to containerize the application for consistent development and deployment environments.
- **GitHub Actions**: Provides automated workflows for testing and deploying code changes.

Each technology has been chosen for its stability, scalability, and ability to integrate well within a microservice-like architecture.

---

## Database Design

### Entities and Fields

- **Users**
  - `user_id` (UUID)
  - `email` (string)
  - `password` (hashed string)
  - `full_name` (string)
  - `date_joined` (datetime)

- **Properties**
  - `property_id` (UUID)
  - `user_id` (foreign key to Users)
  - `title` (string)
  - `description` (text)
  - `location` (string)

- **Bookings**
  - `booking_id` (UUID)
  - `user_id` (foreign key to Users)
  - `property_id` (foreign key to Properties)
  - `start_date` (date)
  - `end_date` (date)

- **Reviews**
  - `review_id` (UUID)
  - `user_id` (foreign key to Users)
  - `property_id` (foreign key to Properties)
  - `rating` (integer)
  - `comment` (text)

- **Payments**
  - `payment_id` (UUID)
  - `user_id` (foreign key to Users)
  - `booking_id` (foreign key to Bookings)
  - `amount` (decimal)
  - `status` (string)

### Relationships

- A **User** can create multiple **Properties**.
- A **User** can make multiple **Bookings**.
- A **Booking** is tied to one **Property** and one **User**.
- A **Review** is left by a **User** for a **Property**.
- A **Payment** is associated with a **Booking** and **User**.

The database structure is normalized, scalable, and optimized for relational queries.

---

## Feature Breakdown

- **User Management**  
  Users can register, log in, manage their profiles, and reset passwords securely.

- **Property Management**  
  Users can list properties, edit details, and upload property information.

- **Booking System**  
  Users can check availability and make bookings for specific dates.

- **Review System**  
  After a stay, users can leave ratings and reviews for listed properties.

- **Payment Processing**  
  Integrates secure payment gateways to process and track transactions.

---

## API Security

To protect the backend APIs, the following security measures are implemented:

- **Authentication**  
  Ensures only registered users can access protected resources using JWT tokens.

- **Authorization**  
  Controls user access levels (e.g., only owners can edit their own properties).

- **Rate Limiting**  
  Prevents abuse by limiting the number of requests a user can make in a given time frame.

Security is essential to protect sensitive user data, prevent unauthorized access, and ensure financial transactions are secure.

---

## CI/CD Pipeline

**CI/CD (Continuous Integration/Continuous Deployment)** automates the process of testing, building, and deploying the application.

- **Continuous Integration** ensures that code changes are automatically tested and merged safely.
- **Continuous Deployment** allows automatic deployment of updates with minimal downtime.

### Tools Used

- **GitHub Actions**: Automates workflows like testing and deployment on push or pull request.
- **Docker**: Ensures the app runs the same way across all environments.

This setup speeds up development, reduces bugs, and ensures a smoother deployment cycle.
