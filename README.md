# Spring Boot Microservices Project

**Student:** [Dauletkerey Kelgenbay]  
**Branch:** [main]  
---

## What I Built

### Eureka Server
- **Explanation:** The Eureka Server is a service registry where all microservices register themselves. It allows services to discover each other and manage their interactions dynamically.
- **Key Points:**
  - Dependency: `spring-cloud-starter-netflix-eureka-server`
  - Runs on port 8761.
  - Registers the microservices that are part of the system.

### API Gateway
- **Explanation:** The API Gateway acts as the entry point for all client requests. It handles routing, load balancing, security, and response aggregation for all microservices.
- **Key Points:**
  - Dependency: `spring-cloud-starter-gateway`
  - Routes requests to `/api/students/**` to the Student Service.
  - Runs on port 8085.

### Student-Service
- **Explanation:** The Student Service exposes RESTful endpoints that provide student data such as `id`, `name`, and `major`. This service registers itself with Eureka Server for dynamic discovery.
- **Key Points:**
  - Dependency: `spring-boot-starter-web`
  - Exposes `/students/{id}` endpoint to fetch student details.
  - Provides a custom feature for fetching students based on their hobby.

### Unique Feature
- **Feature:** `/students/by-hobby/{hobby}` allows querying students by their hobby, reflecting personal interests.
- **Why Added:** This feature showcases a custom aspect that goes beyond typical functionality. It reflects personal interests, such as "coding" or "gaming", making it more relatable.
- **How it Works:** A custom endpoint was added to the Student Service that filters students based on their hobby field in the data.

---

## Why These Technologies

- **Eureka Server:** Eureka serves as a service registry that allows microservices to register themselves and discover other services without the need for hardcoded IPs or ports. It provides scalability, fault tolerance, and simplified management of service instances.
- **API Gateway:** The API Gateway simplifies routing by providing a centralized entry point for client requests. It abstracts the complexities of calling multiple microservices and aggregates the responses efficiently. It also manages security, such as rate limiting and authentication, and simplifies the client-side communication.

---

## How to Run

### Steps to Run the Project:

1. **Clone the repository**  
   ```bash
   git clone https://github.com/xo-dltkry/eureka/
   cd eureka-server
