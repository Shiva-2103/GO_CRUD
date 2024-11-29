# GO_CRUD

A Go-based REST API application for managing resources with CRUD (Create, Read, Update, Delete) functionality. This project utilizes Go with Gorilla Mux and integrates PostgreSQL for database operations.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
  
---

## Features

- RESTful API for CRUD operations.
- Integration with PostgreSQL database.
- Built using:
  - [Go](https://golang.org/)
  - [Gorilla Mux](https://github.com/gorilla/mux)
  - [PostgreSQL](https://www.postgresql.org/)

---

## Prerequisites

1. [Go (1.20+)](https://golang.org/doc/install)
2. [PostgreSQL](https://www.postgresql.org/download/)
3. Familiarity with REST APIs and Go programming.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Shiva-2103/GO_CRUD.git
   cd GO_CRUD
   ```
2. Install dependencies:
   ```bash
   go mod tidy
   ```
3.Set up PostgreSQL:
Create a database named cruddb.
Run the following SQL command to set up the required table:
   ```bash
   CREATE TABLE items (
    id SERIAL PRIMARY KEY,
    name TEXT NOT NULL,
    description TEXT,
    price NUMERIC
);
   ```
4. Configure the database connection in the project:
   Edit the database configuration in the middleware/db.go file.

## Usage
1.Start the application:
   ```bash
   go run main.go
   ```
2.The server will start at http://localhost:3000.

## API Endpoints

Base URL:  http://localhost:3000

| Method | Endpoint           | Description         |
|--------|-----------------   |---------------------|
| GET    | `/api/items`       | Get all items       |
| GET    | `/api/items/{id}`  | Get item by ID      |
| POST   | `/api/items`       | Add a new item      |
| PUT    | `/api/items/{id}`  | Update item by ID   |
| DELETE | `/api/items/{id}`  | Delete item by ID   |


## Example Payload for /api/items:
  ```
  {
    "name": "Laptop",
    "description": "A high-end gaming laptop",
    "price": 1200
}
  ```
## Project Structure
  ``` graphql
  GO_CRUD/
├── main.go                # Entry point of the application
├── go.mod                 # Go module file
├── middleware/            # Business logic and database handling
│   ├── db.go              # Database connection
│   ├── handlers.go        # Handlers for API requests
├── router/                # Routes for the application
│   ├── router.go          # Router setup
└── README.md              # Project documentation
  ```






