# API Design Template: [Service Name]

## 1. Overview
- **Service Description**: [e.g., User Authentication Service]
- **Protocol**: [REST / gRPC / GraphQL]
- **Base URL**: `https://api.example.com/v1`

## 2. Resources & Endpoints

### [Resource Name: e.g. Users]

#### `GET /users/{id}`
- **Description**: Get user details.
- **Authentication**: Bearer Token required.
- **Request Parameters**:
  - `id` (path, required): User ID.
- **Response (200 OK)**:
  ```json
  {
    "id": "string",
    "name": "string",
    "email": "string"
  }
  ```
- **Error Codes**:
  - `404`: User not found.

#### `POST /users`
- **Description**: Create a new user.
- **Payload**:
  ```json
  {
    "name": "string",
    "email": "string"
  }
  ```
- **Response (201 Created)**:
  ```json
  {
    "id": "new-id"
  }
  ```

## 3. Data Models
- **User**: `{ id, name, email, created_at }`

## 4. Considerations
- **Idempotency**: How are retries handled?
- **Pagination**: Default limit, cursor details.
- **Rate Limiting**: Tiered limits for different users.
