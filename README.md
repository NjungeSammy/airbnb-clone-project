# Airbnb Clone Backend

This is the backend for the Airbnb Clone project. It provides RESTful APIs for user management, property listings, and bookings.

**Tech Stack:** Node.js, Express.js, MongoDB, Mongoose, JWT


## Team Roles
### Backend Developer
Responsible for implementing API endpoints, database schemas, and business logic
### Database Administrator
Manages database design, indexing, and optimizations.
### DevOps Engineer
Handles deployment, monitoring, and scaling of the backend services
### QA Engineer
Ensures the backend functionalities are thoroughly tested and meet quality standards
## Technology Stack
### Django
A high-level python web framework for building and managing RESTFUL API for the backend.
### Django REST Framework
Provides tools and features for creating, authenticating, and managing RESTful API endpoints.
### PostgreSQL
A robust relational database system used to store and manage structured project data efficiently .
### GraphQl
Used to enable flexible and efficienct querying of backend data, offering more control to the frontend.
### Celery
Handles asynchronous background tasks such as sending notifications or processing payments.
### Redis
Used as an in-memory data store for caching and managing session data to improve performance.
#### Docker
Provides containeration for consistent development, testing, and deployment environments.
#### CI/CD pipelines
Automates testing and deployment, ensuring smooth integration and delivery of new code changes.

## Database Design
### Key Entities
#### 1. Users
- Fields: id, name, email, password, role, date_joined
- Description: Represents users who can list, book, or review properties. A user can own multiple properties and make multiple bookings.
#### 2. Properties
- Fields: id, owner_id, title, description, location, price_per_night
- Description: Represents listed properties. Each property is linked with one user and can have multiple bookings and reviews.
#### 3. Bookings
- Fields: id, user_id, property_id, check_in, check_out, total_price
- Description: Represents reservations made by users. Each booking is linked to one user and one property.
#### 4. Reviews
- Fields: id, user_id, property_id, rating, comment, created_at
- Description: Represents feedback left by users about a property. Each review belongs to one property and one user.
#### 5. Payments
- Fields: id, booking_id, amount, payment_method, status, transaction_date
- Description: Represents payment transactions related to bookings. Each payment is tied to a specific booking.
### Relationships
- A **User** can own many **Properties**
- A **Property** can have many **Bookings** and **Reviews**
- A **Booking** belongs to one **User** and one **Property**.
- A **Payment** belongs to one **Booking**.
- A **User** can leave multiple **Reviews** on different **Properties**.
## 4. Feature Breakdown

### 1. API Documentation
The backend APIs are documented using the **OpenAPI** standard and built with **Django REST Framework**, ensuring clear and consistent communication between the backend and frontend. **GraphQL** further enhances flexibility by enabling efficient and specific data queries.

### 2. User Authentication
Implements secure registration, login, and profile management for users through endpoints such as `/users/` and `/users/{user_id}/`. Authentication ensures data privacy and controlled access across the system.

### 3. Property Management
Enables users to create, update, retrieve, and delete property listings through endpoints like `/properties/` and `/properties/{property_id}/`. This forms the foundation for users to manage available accommodations.

### 4. Booking System
Handles the reservation process using endpoints `/bookings/` and `/bookings/{booking_id}/`. It supports creating, updating, and managing bookings, ensuring seamless user experience for check-ins and check-outs.

### 5. Payment Processing
Provides secure payment handling for booking transactions through the `/payments/` endpoint. Integrates payment validation and transaction tracking for a smooth and reliable booking experience.

### 6. Review System
Allows users to post and manage property reviews using endpoints like `/reviews/` and `/reviews/{review_id}/`. Reviews help maintain transparency and improve property credibility.

### 7. Database Optimizations
Implements **indexing** for quick data retrieval and **caching** to reduce database load, enhancing overall performance and response time.


## API Security

Securing the backend APIs is crucial because it:

- Protects sensitive user data from unauthorized access or breaches.  
- Maintains trust between users and the platform.  
- Prevents fraudulent activities and data manipulation.  
- Safeguards payment transactions and financial information.  
- Preserves user privacy and system integrity.  
- Ensures the reliability and stability of backend operations.  

## 6. CI/CD Pipeline

Continuous Integration and Continuous Deployment (CI/CD) pipelines help automate the software development process.

**Importance of CI/CD Pipelines:**
- Automate building, testing, and deployment of code changes.  
- Improve code quality through continuous testing.  
- Reduce deployment errors and manual workload.  
- Speed up feature delivery and ensure consistent updates.  
- Maintain reliability and stability across environments.  

**Common Tools Used:**
- **GitHub Actions:** Automates testing and deployment workflows.  
- **Docker:** Ensures consistent environments across development and production.  
- **CI/CD Services:** Other tools like Jenkins or Travis CI can also be integrated for automation.  

