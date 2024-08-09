# E-Commerce API

## Overview

This project is an E-Commerce API built with Go. It provides essential backend functionalities for an online store, including product management, user authentication, and order processing.

## Tech Stack

- **Backend**: Go
- **Database**: MySQL
- **Authentication**: JWT (JSON Web Token)

## Installation

To get started with the project have a MySQL database running, then follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/IbrahimARahman/ecommerce-api.git
    ```
2. Navigate to the project directory:
    ```bash
    cd ecommerce-api
    ```
3. Install the necessary dependencies:
    ```bash
    go mod tidy
    ```
4. Create a .env file in the root directory and set the following environment variables if they differ from the default:
    |Variable|Default|
    | ----- | ----- |
    |PUBLIC_HOST|http://localhost|
    |PORT|8080|
    |DB_USER|root|
    |DB_PASSWORD|mypassword|
    |DB_HOST|127.0.0.1|
    |DB_PORT|3306|
    |DB_NAME|ecom|
    |JWT_EXP|3600 * 24 * 7|
    |JWT_SECRET|not-so-secret-anymore|

5. Install the golang-migrate CLI: https://github.com/golang-migrate/migrate/tree/v4.17.0/cmd/migrate

6. Run the migrations then run the project:
    ```bash
    make migrate-up
    make run
    ```

### Run Tests
```bash
make test
```

## API Endpoints

Here's a brief overview of the available API endpoints:

### User Routes

- `POST /register`: Register a new user
- `POST /login`: Login a user
- `GET /users/{userID}`: Get a specific user (Admin only)

### Product Routes

- `GET /products`: Get all products
- `GET /products/{productID}`: Get a specific product
- `POST /products`: Create a new product (Admin only)

### Order Routes

- `POST /cart/checkout`: Takes cart items and responds with total price and order ID
