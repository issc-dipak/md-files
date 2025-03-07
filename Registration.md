## User Registration API Documentation

### Endpoint

```
POST /registration
```

### Description
This endpoint allows users to register by providing a username, email, password, and confirm password.

### Request Headers

```
Content-Type: application/json
```

### Request Body

```json
{
  "username": "String",
  "email": "String",
  "password": "String",
  "confirm_password": "String"
}
```

### Validation Rules
- `username`: Required, must be a non-empty string.
- `email`: Required, must be a valid email format.
- `password`: Required, minimum 4 characters.
- `confirm_password`: Must match the `password` field.

### Response

#### Success Response (201 - Created)

```json
{
  "status": "success",
  "message": "Registration successful",
  "user": {
    "id": "Number",
    "username": "String",
    "email": "String"
  }
}
```

#### Error Responses

**400 - Bad Request**

```json
{
  "error": "Validation error message"
}
```

**400 - User Already Exists**

```json
{
  "error": "User already registered with this email."
}
```

**500 - Internal Server Error**

```json
{
  "error": "Internal Server Error"
}
```

### Database Information
The user data is stored in the `users` table with the following fields:
- `id` (Primary Key, Auto Increment)
- `username` (VARCHAR)
- `email` (VARCHAR, Unique)
- `password` (VARCHAR, Hashed with bcrypt)

### Notes
- Passwords are hashed using `bcrypt` with a salt factor of 5.
- The API returns appropriate error messages in case of validation failures or duplicate email registration.

### Server Information
The API runs on port `3000` using Express.js and MySQL for database operations.
