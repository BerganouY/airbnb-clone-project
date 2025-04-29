## Team Roles

### Role Descriptions

**A. Software Engineer:**

* **Description:** Designs, develops, tests, and maintains software systems. This can involve writing code, debugging, and ensuring the software meets the project's requirements. In this project, they are responsible for building the core application features.
* **Responsibilities:**
    * Writes clean, efficient, and well-documented code.
    * Collaborates with other team members to define software specifications.
    * Troubleshoots and resolves software defects.
    * Participates in code reviews.

**B. Front-End Developer:**

* **Description:** This department focuses on the application's user interface (UI) and user experience (UX). They implement the visual elements and interactive components that users interact with.
* **Responsibilities:**
    * Develops user-friendly interfaces using HTML, CSS, and JavaScript.
    * Ensures cross-browser compatibility and responsiveness.
    * Works closely with designers to implement visual designs.

**C. Back-End Developer:**

* **Description:** Handles the server-side logic, databases, and APIs that power the application. They are responsible for data management, server performance, and security.
* **Responsibilities:**
    * Designs, develops, and maintains server-side applications.
    * Manages databases and ensures data integrity.
    * Develops and integrates APIs.

**D. Database Administrator:**

* **Description:** Responsible for the design, implementation, maintenance, and security of the project's databases.
* **Responsibilities:**
    * Designs and implements database schemas.
    * Optimizes database performance.
    * Ensures data security and backup/recovery.

**E. DevOps Engineer:**

* **Description:** Focuses on automating and streamlining the software development lifecycle, including continuous integration and continuous delivery (CI/CD).
* **Responsibilities:**
    * Sets up and manages CI/CD pipelines.
    * Automates infrastructure provisioning and deployment.
    * Monitors system performance and reliability.

**F. Project Manager:**

* **Description:** Plans, organizes, and manages the project to ensure it is completed on time and within budget.
* **Responsibilities:**
    * Defines project scope and objectives.
    * Creates project schedules and manages resources.
    * Communicates with stakeholders and resolves issues.

## Technology Stack

This project utilizes the following technologies:

* **Django:** A high-level Python web framework that enables rapid development of clean, pragmatic web applications. In this project, Django is used for building the RESTful APIs that power the application's backend.
* **PostgreSQL:** A powerful, open-source relational database system. It is used in this project for storing and managing the application's data, including user information, product details, and order history.
* **GraphQL:** A query language for APIs and a runtime for fulfilling those queries with your existing data. GraphQL provides a more efficient and flexible alternative to REST APIs, allowing clients to request only the specific data they need.
* **GitHub Actions:** A continuous integration and continuous delivery (CI/CD) platform that automates your software development workflow. In this project, GitHub Actions is used to automate testing, building, and deployment of the application whenever code is pushed to the repository.
* **Jenkins:** An open-source automation server. It helps to automate the parts of the software development process related to building, testing, and deploying, facilitating continuous integration and continuous delivery. In this project, Jenkins is used to create CI/CD pipelines for automated testing and deployment.


## Database Design

This section outlines the key entities in the database and their relationships.

### Entities

**A. Users**

* **Description:** Stores information about users of the application.
* **Fields:**
    * `user_id` (Primary Key): Unique identifier for each user.
    * `username`: User's login name.
    * `email`: User's email address.
    * `password`: User's password (hashed).
    * `registration_date`: Date the user registered.

**B. Properties**

* **Description:** Stores information about the properties listed on the platform.
* **Fields:**
    * `property_id` (Primary Key): Unique identifier for each property.
    * `owner_id` (Foreign Key referencing Users): ID of the user who owns the property.
    * `address`: Address of the property.
    * `property_type`: Type of property (e.g., apartment, house).
    * `price`: Price per night/day.

**C. Bookings**

* **Description:** Stores information about booking transactions.
* **Fields:**
    * `booking_id` (Primary Key): Unique identifier for each booking.
    * `user_id` (Foreign Key referencing Users): ID of the user who made the booking.
    * `property_id` (Foreign Key referencing Properties): ID of the booked property.
    * `check_in_date`: Booking start date.
    * `check_out_date`: Booking end date.

**D. Reviews**

* **Description:** Stores reviews given by users for properties.
* **Fields:**
    * `review_id` (Primary Key): Unique identifier for each review.
    * `user_id` (Foreign Key referencing Users): ID of the user who wrote the review.
    * `property_id` (Foreign Key referencing Properties): ID of the property being reviewed.
    * `rating`: Rating given by the user.
    * `comment`: Text of the review.

**E. Payments**

* **Description:** Stores information about payment transactions.
* **Fields:**
    * `payment_id` (Primary Key): Unique identifier for each payment.
    * `booking_id` (Foreign Key referencing Bookings): ID of the booking the payment is for.
    * `payment_date`: Date of the payment.
    * `amount`: Amount paid.
    * `payment_method`: Method of payment (e.g., credit card).

### Relationships

* A **User** can have multiple **Properties** (one-to-many relationship).
* A **User** can make multiple **Bookings** (one-to-many relationship).
* A **Property** can have multiple **Bookings** (one-to-many relationship).
* A **User** can write multiple **Reviews** (one-to-many relationship).
* A **Property** can have multiple **Reviews** (one-to-many relationship).
* A **Booking** has one **Payment** (one-to-one relationship or one-to-optional-one).
* A **Payment** belongs to one **Booking** (one-to-one relationship).


## Feature Breakdown

This section details the main features of the Airbnb clone project and their functionalities.

**A. User Management**

This feature allows users to create accounts, log in, manage their profiles, and handle authentication. It ensures secure access to the platform and enables personalized experiences for both hosts and guests.

**B. Property Management**

This feature enables hosts to list their properties, providing details such as location, amenities, pricing, and availability. It also allows hosts to edit property information and manage bookings. This is crucial for hosts to showcase their offerings and control their listings.

**C. Booking System**

This feature facilitates the reservation process between guests and hosts. Guests can search for properties, select dates, and make booking requests. Hosts can confirm or reject bookings, and the system manages booking statuses and details. This feature is core to the platform's functionality, enabling transactions and scheduling.

**D. Review System**

This feature allows guests to leave reviews and ratings for properties they have stayed in. This provides valuable feedback for other users and helps build trust and transparency within the platform. Hosts can also respond to reviews, fostering communication and accountability.

**E. Payment Processing**

This feature handles the financial transactions between guests and hosts. It securely processes payments for bookings, manages payment methods, and ensures accurate transaction records. This is essential for the platform's commercial viability and user trust.
