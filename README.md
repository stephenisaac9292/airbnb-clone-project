# airbnb-clone-project
Team Roles
Backend Developer
Responsible for designing, implementing, and maintaining the server-side logic of the application. They develop APIs, manage the integration of data storage and retrieval, and ensure the backend performs efficiently and securely.

Database Administrator (DBA)
Manages the database systems used in the project. This includes designing database schemas, optimizing queries, ensuring data integrity, performing backups, and managing access controls.

Frontend Developer
Focuses on the user interface and user experience by building responsive and interactive web pages. They implement designs and ensure the frontend communicates seamlessly with the backend.

Project Manager
Oversees the project timeline, resources, and communication. Ensures the project meets its goals by coordinating between team members, managing deadlines, and resolving any roadblocks.

Quality Assurance (QA) Engineer
Responsible for testing the software to identify bugs, verify functionality, and ensure the final product meets quality standards. They create test plans, perform manual and automated testing, and report issues to the development team.

DevOps Engineer
Handles the deployment, monitoring, and infrastructure automation of the project. They set up continuous integration and delivery pipelines, manage cloud resources, and ensure system reliability and scalability.

Technology Stack
Django
A high-level Python web framework used to build robust, scalable web applications. In this project, Django is used to develop the backend and expose RESTful or GraphQL APIs.

PostgreSQL
A powerful, open-source relational database system used to store and manage structured project data with high reliability and performance.

GraphQL
A query language for APIs that allows the client to request exactly the data it needs. Used in this project to optimize data fetching and reduce over-fetching of data.

HTML/CSS/JavaScript
Core frontend technologies used to structure, style, and add interactivity to the user interface of the web application.

Docker
A containerization tool used to package the application and its dependencies, making it easy to deploy and run the app consistently across different environments.



Database Design
Key Entities and Fields
1. User
id: Unique identifier for the user

name: Full name of the user

email: Email address (used for login)

password: Hashed password

role: Defines if the user is a host or a guest

2. Property
id: Unique identifier for the property

user_id: References the owner (host)

title: Name/title of the property

location: Address or city where the property is located

price_per_night: Cost to book per night

3. Booking
id: Unique identifier for the booking

user_id: References the guest making the booking

property_id: References the booked property

start_date: Start date of the booking

end_date: End date of the booking

4. Review
id: Unique identifier for the review

user_id: Reviewer (guest)

property_id: Property being reviewed

rating: Numeric rating (e.g., 1 to 5)

comment: Optional written feedback

5. Payment
id: Unique identifier for the payment

booking_id: Booking this payment is for

amount: Total amount paid

payment_date: Date when payment was made

status: Status (e.g., pending, completed)

Entity Relationships
A User can own multiple Properties (1-to-many).

A User (as a guest) can make multiple Bookings.

A Property can have multiple Bookings.

A Booking is linked to one Property and one User.

A Review belongs to a User and a Property.

A Payment is associated with one Booking.