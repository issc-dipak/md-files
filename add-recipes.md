Dipak-patil



## Recipe Management API Documentation

### Add Recipe

#### Endpoint
```
POST /add-recipe
```

#### Description
This endpoint allows users to add a new recipe with an image.

#### Request Headers
```
Content-Type: multipart/form-data
```

#### Request Body
```json
{
  "title": "String",
  "pre_time": "String",
  "cook_time": "String",
  "ingredients": "String",
  "description": "String",
  "add_image": "File (optional)"
}
```

#### Response
**201 - Created**
```json
{
  "status": "success",
  "message": "Recipe added successfully",
  "recipe": {
    "id": "Number",
    "title": "String",
    "pre_time": "String",
    "cook_time": "String",
    "ingredients": "String",
    "description": "String",
    "add_image": "String"
  }
}
```

**400 - Bad Request**
```json
{
  "error": "Validation error message"
}
```

**500 - Internal Server Error**
```json
{
  "error": "Internal Server Error"
}
```

---

### Fetch All Recipes

#### Endpoint
```
GET /api/recipes
```

#### Description
Retrieves all recipes from the database.

#### Response
**200 - OK**
```json
[ {
  "id": "Number",
  "title": "String",
  "pre_time": "String",
  "cook_time": "String",
  "ingredients": "String",
  "description": "String",
  "add_image": "String"
} ]
```

**500 - Internal Server Error**
```json
{
  "message": "Error fetching recipes"
}
```

---

### Fetch Recipe by ID

#### Endpoint
```
GET /api/recipes/:id
```

#### Description
Retrieves a specific recipe by ID.

#### Response
**200 - OK**
```json
{
  "id": "Number",
  "title": "String",
  "pre_time": "String",
  "cook_time": "String",
  "ingredients": "String",
  "description": "String",
  "add_image": "String"
}
```

**404 - Not Found**
```json
{
  "message": "Recipe not found"
}
```

**500 - Internal Server Error**
```json
{
  "message": "Error fetching recipe"
}
```

---

### Update Recipe

#### Endpoint
```
PUT /api/recipes/:id
```

#### Description
Updates a specific recipe by ID.

#### Request Headers
```
Content-Type: multipart/form-data
```

#### Request Body
```json
{
  "title": "String",
  "description": "String",
  "ingredients": "String",
  "steps": "String",
  "image": "File (optional)"
}
```

#### Response
**200 - OK**
```json
{
  "message": "Recipe updated successfully"
}
```

**500 - Internal Server Error**
```json
{
  "message": "Error updating recipe"
}
```

---

### Delete Recipe

#### Endpoint
```
DELETE /api/recipes/:id
```

#### Description
Deletes a specific recipe by ID.

#### Response
**200 - OK**
```json
{
  "message": "Recipe deleted successfully"
}
```

**500 - Internal Server Error**
```json
{
  "message": "Error deleting recipe"
}
```

---

### Notes
- Recipes can include an image uploaded via `multipart/form-data`.
- Ensure valid data is provided to prevent errors.
- The API is running on port `3000` using Express.js and MySQL.
