# User Service  

![Build](https://img.shields.io/badge/Build-Passing-brightgreen.svg) ![License](https://img.shields.io/github/license/aditya-madhav-bits/user-service)  

The **User Service** is responsible for managing user information within the system. It includes functionalities for creating, updating, retrieving, and managing user statuses.  

## Features ✨  
- **User Registration**: Create new users.  
- **User Retrieval**: Fetch user details by ID, authentication ID, or associated account ID.  
- **User Updates**: Modify user information or status.  
- **User List**: Retrieve all registered users.  

## API Endpoints 📡  

### Base URL: `/api/users`  

---

### 1. Register a User  
- **Endpoint**: `POST /api/users/register`  
- **Request Body**:  
  ```json
  {
    "authId": "auth_123",
    "name": "John Doe",
    "email": "john.doe@example.com",
    "phone": "1234567890",
    "address": "123 Main Street",
    "status": "ACTIVE"
  }
  ```  
- **Response**:  
  ```json
  {
    "status": "SUCCESS",
    "message": "User registered successfully.",
    "data": {
      "id": 1,
      "authId": "auth_123",
      "name": "John Doe"
    }
  }
  ```  

---

### 2. Retrieve All Users  
- **Endpoint**: `GET /api/users`  
- **Response**:  
  ```json
  [
    {
      "id": 1,
      "authId": "auth_123",
      "name": "John Doe",
      "email": "john.doe@example.com",
      "status": "ACTIVE"
    },
    {
      "id": 2,
      "authId": "auth_456",
      "name": "Jane Smith",
      "email": "jane.smith@example.com",
      "status": "INACTIVE"
    }
  ]
  ```  

---

### 3. Retrieve User by Authentication ID  
- **Endpoint**: `GET /api/users/auth/{authId}`  
- **Path Variable**:  
  - `{authId}`: The authentication ID of the user.  
- **Response**:  
  ```json
  {
    "id": 1,
    "authId": "auth_123",
    "name": "John Doe",
    "email": "john.doe@example.com",
    "status": "ACTIVE"
  }
  ```  

---

### 4. Retrieve User by ID  
- **Endpoint**: `GET /api/users/{userId}`  
- **Path Variable**:  
  - `{userId}`: The ID of the user.  
- **Response**:  
  ```json
  {
    "id": 1,
    "authId": "auth_123",
    "name": "John Doe",
    "email": "john.doe@example.com",
    "status": "ACTIVE"
  }
  ```  

---

### 5. Retrieve User by Account ID  
- **Endpoint**: `GET /api/users/accounts/{accountId}`  
- **Path Variable**:  
  - `{accountId}`: The account ID linked to the user.  
- **Response**:  
  ```json
  {
    "id": 1,
    "authId": "auth_123",
    "name": "John Doe",
    "email": "john.doe@example.com",
    "status": "ACTIVE"
  }
  ```  

---

### 6. Update User Information  
- **Endpoint**: `PUT /api/users/{id}`  
- **Path Variable**:  
  - `{id}`: The ID of the user.  
- **Request Body**:  
  ```json
  {
    "name": "John A. Doe",
    "email": "john.doe@updated.com",
    "phone": "0987654321",
    "address": "456 Another Street"
  }
  ```  
- **Response**:  
  ```json
  {
    "status": "SUCCESS",
    "message": "User information updated successfully."
  }
  ```  

---

### 7. Update User Status  
- **Endpoint**: `PATCH /api/users/{id}`  
- **Path Variable**:  
  - `{id}`: The ID of the user.  
- **Request Body**:  
  ```json
  {
    "status": "INACTIVE"
  }
  ```  
- **Response**:  
  ```json
  {
    "status": "SUCCESS",
    "message": "User status updated successfully."
  }
  ```  

---

## Installation 🚀  

1. Clone the repository:  
   ```bash
   git clone https://github.com/aditya-madhav-bits/user-service.git
   cd user-service
   ```  

2. Configure the application:  
   Update the `application.yml` file with necessary configurations (e.g., database, authentication).  

3. Build and run the application:  
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```  

4. Access the service at `http://localhost:8080/api/users`.  

---

## Contribution Guidelines 🤝  

Contributions are welcome! Fork the repository, create a feature branch, and submit a pull request.  

--- 
