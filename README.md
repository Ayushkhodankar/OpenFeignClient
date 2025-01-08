# OpenFeign: A Declarative REST Client

OpenFeign is an open-source project initially developed by Netflix and now maintained by the open-source community. It simplifies the process of writing web services by providing a declarative approach to REST API consumption using the `FeignClient` interface.

## Features
- **Declarative REST Client:** Write cleaner and more maintainable code by declaring interfaces.
- **Integration Friendly:** Ideal for consuming third-party APIs and microservice endpoints.
- **Dynamic Implementation:** Automatically creates dynamic implementations for declared `FeignClient` interfaces.

## Dependencies
To use OpenFeign in your project, add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-openfeign</artifactId>
</dependency>
```

## Project Overview
This project demonstrates the use of OpenFeign in a microservice architecture with the following components:

### Microservices
1. **Employee Service**
    - Manages employee-related data and operations.
2. **Address Service**
    - Handles address-related information for employees.

## Getting Started
### Prerequisites
- Java Development Kit (JDK 8 or above)
- Maven
- Spring Boot

### Steps to Run the Project
1. Clone this repository.
2. Navigate to each service directory and build the project using:
    ```bash
    mvn clean install
    ```
3. Run each service using:
    ```bash
    mvn spring-boot:run
    ```
4. Test the endpoints using tools like Postman or cURL.

## How OpenFeign Works
1. Declare a `@FeignClient` interface with the desired REST API endpoints.
2. OpenFeign dynamically generates the implementation at runtime.
3. Use the client as a Spring Bean in your services to make API calls effortlessly.

### Example `FeignClient` Declaration
```java
@FeignClient(name = "address-service", url = "http://localhost:8081")
public interface AddressClient {
    @GetMapping("/addresses/{id}")
    Address getAddressById(@PathVariable("id") Long id);
}
```

### Benefits
- Reduces boilerplate code for REST API calls.
- Simplifies integration between microservices.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---
Developed with ❤️ for simplifying microservice communication.
