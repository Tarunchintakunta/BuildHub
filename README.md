# BuildHub: Urban Company for Construction - Project README

## 1. Product Vision & Target Personas

### Product Vision

BuildHub is a technology-driven marketplace designed to revolutionize the construction industry by connecting consumers and businesses with a curated network of reliable and skilled service providers and material suppliers. Our platform aims to bring transparency, efficiency, and trust to a traditionally fragmented and opaque industry. We envision a future where anyone can seamlessly plan, book, and manage construction projects, from minor repairs to major renovations, with the same ease and confidence as ordering a meal online. By empowering both customers and providers with powerful tools for communication, project management, and payments, BuildHub will become the go-to platform for all construction needs, fostering a community built on quality, reliability, and exceptional service.

### Target Personas

*   **Priya, the Homeowner**: A 35-year-old marketing professional who recently purchased an older home. She needs reliable contractors for various renovation projects (kitchen, bathroom, etc.) but is overwhelmed by the process of finding and vetting them. She values transparency in pricing, clear communication, and the ability to track project progress.

*   **Raj, the Small Business Owner**: A 45-year-old restaurant owner who needs to build out a new location. He is looking for a one-stop-shop for all his construction needs, from architects and contractors to material suppliers. He is budget-conscious and needs a platform that can help him manage multiple bids and timelines efficiently.

*   **Sandeep, the Skilled Contractor**: A 40-year-old electrician with his own small business. He is looking for a steady stream of projects without the hassle of marketing and lead generation. He wants a platform that is easy to use, allows him to showcase his work, and ensures he gets paid on time.

*   **Anita, the Material Supplier**: A 50-year-old owner of a local hardware store. She wants to expand her business by reaching a larger customer base. She is looking for a platform that can help her manage inventory, process orders, and compete with larger suppliers.

## 2. Features & Roadmap

### MVP Feature List (Must-Have)

*   **User Authentication**: Secure sign-up and login for all user types.
*   **Provider Onboarding**: A streamlined process for contractors and suppliers to create profiles, upload documents, and get verified.
*   **Service & Product Listings**: Basic browsing and searching for services and materials.
*   **Booking & Ordering**: A simple flow for users to book services or order materials.
*   **Bidding System**: A basic bidding system for service requests.
*   **In-App Messaging**: Real-time chat between users and providers.
*   **Payment Integration**: Secure payment processing for bookings and orders.
*   **Ratings & Reviews**: A simple system for users to rate and review providers.

### Prioritized Backlog

| Priority | Feature                  | V1/V2      | Description                                                                 |
|----------|--------------------------|------------|-----------------------------------------------------------------------------|
| 1        | Advanced Search & Filters| V1         | Enhanced search with filters for location, specialty, availability, etc.    |
| 2        | Project Management Tools | V1         | Tools for users to track project progress, milestones, and payments.         |
| 3        | Chatbot Assistant        | V1         | An AI-powered chatbot to assist users with common queries and tasks.         |
| 4        | Dispute Resolution       | V1         | A formal system for managing and resolving disputes between users and providers.|
| 5        | Subscription Plans       | V2         | Premium plans for providers with features like featured listings and analytics.|
| 6        | PWA & Offline Support    | V2         | PWA for a native-like experience and offline support for field workers.    |
| 7        | 3rd-Party Integrations   | V2         | Integrations with accounting software, CRMs, and other business tools.       |

## 3. User Stories & Acceptance Criteria

### Service Booking

*   **User Story**: As Priya, I want to be able to easily search for and book a plumber for a leaky faucet, so I can get it fixed quickly and without hassle.
*   **Acceptance Criteria**:
    *   I can search for "plumber" and see a list of available providers in my area.
    *   I can view a plumber's profile, including their rates, reviews, and availability.
    *   I can select a date and time for the service and confirm the booking.
    *   I receive a confirmation notification and can communicate with the plumber through the app.

### Product Order

*   **User Story**: As Raj, I want to be able to order a specific type of tile for my new restaurant, so I can get the best price and have it delivered to my site.
*   **Acceptance Criteria**:
    *   I can search for "ceramic tiles" and filter by color, size, and price.
    *   I can view product details, including specifications and supplier information.
    *   I can add the tiles to my cart, specify the quantity, and complete the purchase.
    *   I receive an order confirmation and can track the delivery status.

### Bidding

*   **User Story**: As Priya, I want to be able to post a job for a kitchen renovation and receive multiple bids, so I can compare prices and choose the best contractor for my budget.
*   **Acceptance Criteria**:
    *   I can create a job posting with a detailed description, photos, and my budget.
    *   I receive notifications when contractors submit bids.
    *   I can review the bids, compare contractor profiles, and communicate with them for more details.
    *   I can accept a bid and proceed with the project.

### Provider Onboarding

*   **User Story**: As Sandeep, I want a simple and quick way to create a profile and get verified, so I can start receiving job requests.
*   **Acceptance Criteria**:
    *   I can sign up as a contractor and fill out my profile with my skills, experience, and rates.
    *   I can upload necessary documents like my license and insurance for verification.
    *   I receive a notification once my profile is approved and live on the platform.

### Dispute Resolution

*   **User Story**: As Raj, I want a clear process for raising a dispute if a contractor does a poor job, so I can get a refund or have the work redone.
*   **Acceptance Criteria**:
    *   I can initiate a dispute from the project page and provide details and evidence.
    *   A support agent is assigned to the case and mediates the dispute.
    *   The platform facilitates a resolution, such as a partial refund or re-work.

## 4. High-Level Architecture

```
[Mobile App (React Native)] <--> [API Gateway] <--> [Backend Services (Java)]
                                      ^
                                      |
                                [Auth Service]
                                      ^
                                      |
[NLP Services (Python)] <--> [Backend Services (Java)] <--> [Database (Postgres/MongoDB)]
                                      ^
                                      |
                                [Websockets]
```

*   **Mobile App (React Native)**: The user-facing application for both customers and providers.
*   **API Gateway**: The single entry point for all client requests, responsible for routing, authentication, and rate limiting.
*   **Backend Services (Java)**: The core business logic of the platform, including user management, bookings, payments, etc.
*   **NLP Services (Python)**: A set of microservices for handling chatbot interactions, intent recognition, and other NLP tasks.
*   **Database**: A combination of Postgres for structured data and MongoDB for unstructured data.
*   **Websockets**: For real-time communication, such as in-app messaging and notifications.

## 5. Low-Level Design

### Frontend (React Native)

*   **State Management**: Redux for managing global application state.
*   **UI Components**: A custom component library for a consistent look and feel.
*   **API Client**: Axios for making HTTP requests to the backend.
*   **Authentication**: JWT-based authentication with secure storage of tokens.

### Backend (Java)

*   **Framework**: Spring Boot for building robust and scalable REST APIs.
*   **Database**: JPA/Hibernate for interacting with the Postgres database and Spring Data MongoDB for MongoDB.
*   **Authentication**: Spring Security with JWT for securing endpoints.
*   **Messaging**: RabbitMQ for asynchronous communication between services.

### API Design

*   **RESTful APIs**: All APIs will follow REST principles.
*   **Versioning**: APIs will be versioned (e.g., `/api/v1/...`).
*   **Authentication**: All protected endpoints will require a valid JWT in the `Authorization` header.

### Database Schema (Postgres)

*   **Users**: `id`, `name`, `email`, `password`, `role`, etc.
*   **Providers**: `id`, `user_id`, `specialty`, `rate`, `availability`, etc.
*   **Bookings**: `id`, `user_id`, `provider_id`, `service`, `date`, `status`, etc.

### Database Schema (MongoDB)

*   **Messages**: `id`, `sender_id`, `receiver_id`, `content`, `timestamp`, etc.
*   **Reviews**: `id`, `user_id`, `provider_id`, `rating`, `comment`, etc.

## 6. Data Storage Strategy

*   **Structured (Postgres)**:
    *   **User Data**: Core user information, credentials, and roles are highly structured and relational.
    *   **Bookings & Orders**: Transactional data that requires strong consistency and integrity.
    *   **Provider Profiles**: Core provider information, skills, and verification status.
    *   **Why**: SQL databases like Postgres are ideal for this type of data due to their ACID compliance, strong consistency, and powerful querying capabilities.

*   **Unstructured (MongoDB)**:
    *   **Messaging**: Chat messages are unstructured and can be stored as individual documents, making it easy to scale.
    *   **Reviews & Ratings**: User-generated content that can vary in structure and is often read-heavy.
    *   **Provider Portfolios**: Images, project descriptions, and other rich media are best stored in a document-oriented database.
    *   **Why**: NoSQL databases like MongoDB are well-suited for this type of data due to their flexible schema, scalability, and performance for read-heavy workloads.

## 7. Chatbot & NLP Pipeline

### User Intents

*   `greet`
*   `book_service`
*   `track_order`
*   `get_help`
*   `small_talk`

### Slot Filling

*   **`book_service`**: `service_type`, `location`, `date`, `time`
*   **`track_order`**: `order_id`

### RAG-style Knowledge Retrieval

*   **Knowledge Base**: FAQs, user manuals, and provider profiles will be stored in a vector database.
*   **Retrieval**: When a user asks a question, the chatbot will first search the vector database for relevant information.
*   **Generation**: The retrieved information will be used to generate a context-aware and accurate response.

### Integration

*   The chatbot will be a Python-based microservice using libraries like Rasa or TensorFlow.
*   It will communicate with the Java backend via a REST API to access user data, book services, and perform other actions.

## 8. API Endpoints & Payloads

### Create Booking

*   **Endpoint**: `POST /api/v1/bookings`
*   **Request**:
    ```json
    {
      "provider_id": "123",
      "service": "Plumbing",
      "date": "2024-10-26"
    }
    ```
*   **Response**:
    ```json
    {
      "id": "456",
      "status": "confirmed"
    }
    ```

### Send Message

*   **Endpoint**: `POST /api/v1/messages`
*   **Request**:
    ```json
    {
      "receiver_id": "789",
      "content": "Hello, I have a question about my booking."
    }
    ```
*   **Response**:
    ```json
    {
      "id": "101",
      "status": "sent"
    }
    ```

## 9. Offline-First & PWA Strategy

*   **Offline Support**:
    *   Use a local database (e.g., SQLite) to store essential data on the device.
    *   Implement a synchronization mechanism to sync data with the server when the device is online.
*   **PWA**:
    *   Use service workers to cache static assets and API responses for offline access.
    *   Provide a native-like experience with features like push notifications and an "Add to Home Screen" prompt.
*   **Storage Strategy**:
    *   **localStorage**: For persisting data across sessions (e.g., user preferences).
    *   **sessionStorage**: For temporary data that is cleared when the session ends.
    *   **In-Memory**: For data that is only needed for the current session and does not need to be persisted.

## 10. Security, Scaling & Testing

*   **Security**:
    *   Implement JWT-based authentication and authorization.
    *   Use HTTPS for all communication.
    *   Protect against common vulnerabilities like SQL injection and XSS.
*   **Scaling**:
    *   Use a microservices architecture to scale individual services independently.
    *   Use a load balancer to distribute traffic across multiple instances.
    *   Use a CDN to cache static assets and reduce latency.
*   **Testing**:
    *   Write unit tests for all backend and frontend components.
    *   Implement integration tests to ensure that all services work together correctly.
    *   Conduct end-to-end testing to simulate real-user scenarios.

## 11. 3-Phase Roadmap

### Phase 1: MVP (3-6 months)

*   **Focus**: Core features for booking services and ordering materials.
*   **Goal**: Launch in a limited market and gather user feedback.

### Phase 2: Beta (6-12 months)

*   **Focus**: Adding advanced features like project management tools and a chatbot.
*   **Goal**: Expand to new markets and refine the user experience.

### Phase 3: Launch (12-18 months)

*   **Focus**: Scaling the platform and adding new features like subscription plans and 3rd-party integrations.
*   **Goal**: Become the leading platform for construction services and materials.
