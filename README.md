# airbnb-clone-project
It's a project to learn back-end technologies by creating an Airbnb clone.

# Project Goals
    * Master collaborative team workflows using GitHub.
    * Deepen your understanding of backend architecture and database design principles.
    * Implement advanced security measures for API development.
    * Gain proficiency in designing and managing CI/CD pipelines for efficient deployment.
    * Strengthen your ability to document and plan complex software projects effectively.
    * Develop an understanding of integrating technologies like Django, MySQL, and GraphQL in a unified ecosystem

# Tech Stack
This project leverages a modern tech stack to ensure robustness and scalability:

    * Django: A high-level Python web framework for building RESTful APIs.
    * MySQL: A relational database management system for data storage.
    * GraphQL: A query language for APIs that provides flexibility and efficiency.
    * Docker: A containerization tool for consistent development and deployment environments.
    * GitHub Actions (or similar CI/CD platforms): For automating continuous integration and continuous deployment pipelines.

# Team roles
1. Business Analyst (BA)

    Responsibilities: Understands customer business needs and translates them into clear requirements for the development team. Acts as a bridge between business stakeholders and the technical team to ensure the final product delivers maximum value.

2. Product Owner (PO)

    Responsibilities: Holds the product vision and its roadmap. Ensures the product meets customer and market needs, and manages the product backlog by prioritizing features.

3. UI/UX Designer

    Responsibilities: Transforms the product vision into user-friendly designs. Creates the user interface (UI) and user experience (UX) to ensure the application is intuitive, aesthetically pleasing, and easy to use, by designing optimal user journeys.

4. Software Architect

    Responsibilities: Makes high-level software design decisions. Selects appropriate tools and platforms, defines the system architecture (how services and databases communicate), and establishes code quality standards.

5. Software Developer (Frontend and Backend Developers)

    Responsibilities:
        Frontend Developer: Creates the part of the application that users directly interact with, ensuring a smooth user experience across all devices and platforms.
        Backend Developer: Implements the core of the application, including algorithms and business logic. May also participate in architectural design and integrations.

6. Quality Assurance (QA) Engineer

    Responsibilities: Ensures the application performs according to functional and non-functional requirements. Identifies defects, runs various tests (functional, usability, security, performance), and reports on application quality.

7. Test Automation Engineer

    Responsibilities: Designs and implements the test automation ecosystem. Writes and maintains automated test scripts to provide reliable and continuous feedback on application quality, reducing manual effort.

8. DevOps Engineer

    Responsibilities: Facilitates cooperation between development and operations teams. Builds and manages Continuous Integration/Continuous Delivery (CI/CD) pipelines to automate and accelerate the software delivery process, ensuring application stability.

# Technology Stack

    1. Django: A high-level Python web framework used for building the RESTful API and overall backend structure.

    2. Django REST Framework: Provides tools for creating and managing robust RESTful APIs, facilitating CRUD operations for various data.

    3. PostgreSQL: A powerful relational database used for efficient and reliable data storage of all project information (users, properties, bookings, etc.).

    4. GraphQL: Offers a flexible and efficient query mechanism for interacting with the backend, allowing clients to request exactly the data they need.

    5. Celery: Used for handling asynchronous tasks, such as sending notifications, processing payments in the background, or other time-consuming operations without blocking the main application flow.

    6. Redis: Utilized for caching strategies to reduce database load and improve application performance, and also for session management.

    7. Docker: A containerization tool used for consistent development and deployment environments, ensuring the application runs uniformly across different machines.

    8. CI/CD Pipelines: Automated pipelines (using tools like GitHub Actions, not explicitly named here but implied by CI/CD context) for testing and deploying code changes, ensuring efficient and reliable delivery of updates.

# Database Design
Key Entities and Their Relationships

    Users
        Important Fields: user_id (Primary Key), username, email, password_hash, registration_date
        Relationships:
            A User can have multiple Properties.
            A User can make multiple Bookings.
            A User can write multiple Reviews.
            A User can make multiple Payments.

    Properties
        Important Fields: property_id (Primary Key), title, description, location, price_per_night, owner_id (Foreign Key to Users)
        Relationships:
            A Property belongs to one User (its owner).
            A Property can have multiple Bookings.
            A Property can receive multiple Reviews.

    Bookings
        Important Fields: booking_id (Primary Key), property_id (Foreign Key to Properties), user_id (Foreign Key to Users), check_in_date, check_out_date, total_price, status
        Relationships:
            A Booking belongs to one Property.
            A Booking is made by one User.
            A Booking can be associated with one Payment.

    Reviews
        Important Fields: review_id (Primary Key), property_id (Foreign Key to Properties), user_id (Foreign Key to Users), rating, comment, review_date
        Relationships:
            A Review is for one Property.
            A Review is written by one User.

    Payments
        Important Fields: payment_id (Primary Key), booking_id (Foreign Key to Bookings), user_id (Foreign Key to Users), amount, payment_date, status
        Relationships:
            A Payment is associated with one Booking.
            A Payment is made by one User.

# Feature Breakdown
    User Management
    This feature involves implementing a secure system for user registration, authentication, and profile management. It's crucial for the project as it allows users to create accounts, log in securely, and manage their personal information, forming the foundation for all user-specific interactions on the platform.

    Property Management
    This encompasses developing functionalities for property listing creation, updates, and retrieval. It's essential for hosts to be able to efficiently list their properties, provide detailed information, and manage their availability, directly contributing to the platform's inventory and appeal.

    Booking System
    This feature involves creating a robust mechanism that allows users to reserve properties and manage their booking details. It's at the core of a booking platform, enabling the primary transaction flow between guests and hosts, ensuring properties can be reserved and managed effectively.

    Payment Processing
    This integrates a system to securely handle transactions and record payment details. It's vital for monetizing the platform and ensuring that financial transactions between guests and hosts are processed smoothly and reliably.

    Review System
    This allows users to leave reviews and ratings for properties after their stay. It contributes significantly to building trust and transparency within the platform, helping future guests make informed decisions and providing valuable feedback for hosts.