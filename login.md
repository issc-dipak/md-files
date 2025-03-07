Dipak-patil



## User Login API Documentation

### Endpoint

```
POST /login
```

### Description
This endpoint allows users to log in using their email and password.

### Request Headers

```
Content-Type: application/json
```

### Request Body

```json
{
  "email": "String",
  "password": "String"
}
```

### Validation Rules
- `email`: Required, must be a valid email format.
- `password`: Required.

### Response

#### Success Response (200 - OK)

```json
{
  "status": "success",
  "message": "Login successful",
  "token": "JWT Token",
  "user": {
    "id": "Number",
    "username": "String",
    "email": "String"
  }
}
```

#### Error Responses

**400 - Bad Request (Validation Error or Incorrect Credentials)**

```json
{
  "error": "Validation error message or Invalid email or password."
}
```

**500 - Internal Server Error**

```json
{
  "error": "Internal Server Error"
}
```

### Authentication & Security
- The password is verified using `bcrypt.compare()`.
- A JSON Web Token (JWT) is generated upon successful login.
- The token expires in `1 hour`.

### Database Information
The user credentials are stored in the `users` table with the following fields:
- `id` (Primary Key, Auto Increment)
- `username` (VARCHAR)
- `email` (VARCHAR, Unique)
- `password` (VARCHAR, Hashed with bcrypt)

### Notes
- Users must provide valid credentials to receive an authentication token.
- The JWT should be included in the Authorization header for subsequent authenticated requests.

### Server Information
The API runs on port `3000` using Express.js and MySQL for database operations.
