# Rust Web Server with Actix

This project demonstrates a web server built in Rust using the Actix Web framework. It includes functionalities for managing tasks and user authentication. (For now, I've not implemented an actual Database and authentication feature but shortly it will be added as well)

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Endpoints](#endpoints)
- [Technical Keywords](#technical-keywords)
- [Contribution](#contribution)
- [License](#license)

## Introduction

This web server is implemented in Rust using the Actix Web framework. It provides a basic task management system and user authentication. The database is handled in memory and persisted to a JSON file for simplicity.

## Features

- Create, read, update, and delete tasks
- User registration and login
- In-memory database with persistence to a JSON file
- CORS support for cross-origin requests

## Technologies Used

- **Rust**: A systems programming language known for performance and safety.
- **Actix Web**: A powerful, pragmatic, and extremely fast web framework for Rust.
- **Serde**: A framework for serializing and deserializing Rust data structures efficiently and generically.
- **Reqwest**: An ergonomic HTTP client for Rust.
- **Actix CORS**: Middleware for handling Cross-Origin Resource Sharing.

## Getting Started

### Prerequisites

- Rust: Ensure you have Rust installed on your machine. You can download it from [here](https://www.rust-lang.org/tools/install).

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/shravanandoria/Rust_GPT4.git
   cd Rust_GPT4
   ```

2. Build the project:
   ```sh
   cargo build
   ```

3. Run the server:
   ```sh
   cargo run
   ```

The server will start running on `127.0.0.1:8080`.

## Endpoints

### Task Management

- **Create Task**: `POST /task`
  - Request Body: `{ "id": u64, "name": String, "completed": bool }`
  - Response: `200 OK`

- **Read All Tasks**: `GET /task`
  - Response: `200 OK` with a JSON array of tasks

- **Read Task by ID**: `GET /task/{id}`
  - Response: `200 OK` with the task details, or `404 Not Found`

- **Update Task**: `PUT /task`
  - Request Body: `{ "id": u64, "name": String, "completed": bool }`
  - Response: `200 OK`

- **Delete Task**: `DELETE /task/{id}`
  - Response: `200 OK`

### User Management

- **Register User**: `POST /register`
  - Request Body: `{ "id": u64, "username": String, "password": String }`
  - Response: `200 OK`

- **Login User**: `POST /login`
  - Request Body: `{ "username": String, "password": String }`
  - Response: `200 OK` on success, or `502 Bad Gateway` on failure

## Technical Keywords

- **Actix Web**: A web framework for Rust, known for its speed and scalability.
- **CORS**: Actix CORS middleware is used to handle Cross-Origin Resource Sharing.
- **Mutex**: A synchronization primitive that can be used to protect shared data from being simultaneously accessed by multiple threads. Here, it's used to ensure thread-safe access to the in-memory database.
- **Serde**: A Rust library for serializing and deserializing data structures efficiently.
- **Reqwest**: A Rust HTTP client library.

## Contribution

Contributions are welcome! Please open an issue or submit a pull request for any improvements or additions.
