# Product Management API

## Overview
The **Product Management API** is a RESTful service built with **Spring Boot** and **MongoDB** to facilitate seamless product management. It supports essential CRUD (Create, Read, Update, Delete) operations, ensuring efficient handling of product data with robust validation and error handling.

## Key Features
- Full CRUD operations for managing products.
- MongoDB integration for persistent and scalable storage.
- Structured exception handling and validation mechanisms.
- Comprehensive unit and integration testing.
- API testing with **Postman**.
- Database exploration using **MongoDB Compass** or **MongoDB shell**.

## Tech Stack
- **Spring Boot** - Backend Framework
- **MongoDB** - NoSQL Database
- **Maven** - Dependency Management
- **Postman** - API Testing
- **MongoDB Compass** - Database Visualization Tool

## Project Structure
```
product-management-api/
│── src/
│   ├── main/
│   │   ├── java/com/example/productapi/
│   │   │   ├── controller/
│   │   │   ├── model/
│   │   │   ├── repository/
│   │   │   ├── service/
│   │   │   ├── exception/
│   ├── resources/
│   │   ├── application.properties
│── pom.xml
│── README.md
```

## Installation & Setup

### Prerequisites
- Java 17+
- Spring Boot
- MongoDB (Local or Cloud)
- Postman

### Steps to Run
1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-username/product-management-api.git
   cd product-management-api
   ```
2. **Configure MongoDB** (Modify `application.properties` if needed)
   ```properties
   spring.data.mongodb.uri=mongodb://localhost:27017/productdb
   ```
3. **Build and Run the Application**
   ```sh
   mvn clean install
   mvn spring-boot:run
   ```

## API Endpoints

### 1. Create a Product
- **Endpoint:** `POST /api/products`
- **Request Body:**
  ```json
  {
    "name": "Wireless Mouse",
    "description": "Ergonomic wireless mouse with USB receiver",
    "price": 29.99,
    "quantity": 100,
    "category": "Electronics"
  }
  ```
- **Response:** Returns the created product with a unique ID.

### 2. Retrieve All Products
- **Endpoint:** `GET /api/products`
- **Response:** Returns an array of stored products.

### 3. Retrieve a Product by ID
- **Endpoint:** `GET /api/products/{id}`
- **Response:** Returns a single product.

### 4. Update a Product
- **Endpoint:** `PUT /api/products/{id}`
- **Request Body:**
  ```json
  {
    "price": 24.99,
    "quantity": 150
  }
  ```
- **Response:** Returns the updated product details.

### 5. Delete a Product
- **Endpoint:** `DELETE /api/products/{id}`
- **Response:** Returns a confirmation of successful deletion.

## Testing with Postman
1. Import the provided **Postman collection**.
2. Execute API requests in order:
   - Create a product
   - Fetch all products
   - Retrieve a product by ID
   - Update a product
   - Delete a product

## MongoDB Verification

### Using MongoDB Compass
1. Connect to the database.
2. Inspect the `productdb` collection.
3. Confirm data persistence.

### Using MongoDB Shell
```sh
mongo
use productdb
db.products.find().pretty()
```

## Exception Handling
| Error Scenario       | HTTP Status Code |
|----------------------|-----------------|
| Invalid Product ID   | 404 Not Found    |
| Invalid Input Data   | 400 Bad Request  |

## Testing Strategy
- **Unit Tests** - Validate service and controller layers.
- **Integration Tests** - Verify end-to-end API functionality.

## Video Demonstration
📽 **Demo Video:** *[Insert Link Here]*

### Includes:
- Running the application.
- API testing in **Postman**.
- MongoDB verification.
- Overview of code structure.

## Challenges & Solutions
| Challenge                  | Solution |
|----------------------------|----------|
| Database connection issues | Used the correct MongoDB URI. |
| Validation errors          | Implemented DTO and validation annotations. |
| Exception handling         | Used `@ControllerAdvice` for centralized error handling. |

## Conclusion
This API provides a structured and efficient approach to product management, leveraging **Spring Boot** and **MongoDB** while ensuring best practices in backend development.

**Author:** Ayush Mahale

