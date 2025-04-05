## Advertisement API Documentation

### Add Advertisement

**Endpoint:** `POST /api/ads`

**Headers:**
- `Content-Type: multipart/form-data`

**Body Parameters:**
- `name` (String) - Name of the advertisement
- `description` (String) - Description of the advertisement
- `link` (String) - Link to be associated
- `image` (File) - Optional image file upload

**Response:**
- `201 Created` - Advertisement added successfully
- `500 Internal Server Error` - Error adding advertisement

---

### Get All Advertisements

**Endpoint:** `GET /api/ads`

**Response:**
- `200 OK` - Returns list of advertisements
- `500 Internal Server Error` - Error fetching advertisements

---

### Get Advertisement By ID

**Endpoint:** `GET /api/ads/:id`

**Path Parameter:**
- `id` (Number) - Advertisement ID

**Response:**
- `200 OK` - Returns advertisement object
- `404 Not Found` - Advertisement not found
- `500 Internal Server Error` - Error fetching advertisement

---

### Update Advertisement

**Endpoint:** `PUT /api/ads/:id`

**Headers:**
- `Content-Type: multipart/form-data`

**Path Parameter:**
- `id` (Number) - Advertisement ID

**Body Parameters:**
- `name` (String) - Name of the advertisement
- `description` (String) - Description of the advertisement
- `link` (String) - Link to be associated
- `image` (File or String) - New image file or existing image filename

**Response:**
- `200 OK` - Advertisement updated successfully
- `404 Not Found` - Advertisement not found
- `500 Internal Server Error` - Error updating advertisement

---

### Delete Advertisement

**Endpoint:** `DELETE /api/ads/:id`

**Path Parameter:**
- `id` (Number) - Advertisement ID

**Response:**
- `200 OK` - Advertisement deleted successfully
- `404 Not Found` - Advertisement not found
- `500 Internal Server Error` - Error deleting advertisement
