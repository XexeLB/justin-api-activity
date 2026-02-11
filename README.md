# RESTful API Activity – Justin Jhade Permejo

---

## 1. Environment Variables

### Why use `.env` instead of putting settings in the code?

- Keeps secret information safe (database URLs, passwords, API keys).
- Allows changing settings without editing the main code.
- Supports different configurations for development and production.
- Prevents sensitive data from being uploaded to GitHub.
- Makes the project more secure and professional.

Using `.env` is a standard best practice in real-world applications.

---

## 2. Resource Naming

### Why use `/rooms` instead of `/room`?

- `/rooms` represents a collection of rooms.
- `/rooms/101` represents one specific room.
- REST APIs commonly use plural nouns.
- Makes endpoints predictable and easy to understand.
- Improves consistency across the API.

This follows RESTful design standards.

---

## 3. Status Codes

### When do we use `201` vs `200`?

- **200 OK**
  - When retrieving data (GET)
  - When updating data (PUT/PATCH)
  - When a request is successful

- **201 Created**
  - When creating a new resource (POST)

Using correct status codes clearly communicates what happened.

---

### Why send `404` instead of empty data?

- `404 Not Found` means the resource does not exist.
- An empty array means the request worked, but no results were found.
- These are different situations.
- Proper status codes make debugging easier.

Example:
- Non-existing room → `404`
- Search with no matches → `200` with empty array

---

## 4. Error Handling

### Common HTTP Error Codes

- `400 Bad Request` – Invalid or missing data.
- `401 Unauthorized` – Not authenticated.
- `403 Forbidden` – No permission.
- `404 Not Found` – Resource not found.
- `500 Internal Server Error` – Server issue.

### Standard Error Response Format

```json
{
  "success": false,
  "message": "Room not found"
}
```

Always return errors in a consistent format.

---

## 5. Data Modeling Decisions

### Why Embed [Review / Tag / Log]?

- They belong directly to the parent item.
- They are small and dependent data.
- They are always retrieved with the parent.
- Embedding improves read performance.
- Keeps related data together.

---

### Why Reference [Chef / User / Guest]?

- They exist independently.
- They may connect to many items.
- Avoids data duplication.
- Updating one record updates all references.
- Keeps documents lighter and scalable.

---

## Conclusion

This RESTful API follows best practices by:

- Using environment variables for security.
- Following proper REST naming conventions.
- Using correct HTTP status codes.
- Implementing consistent error handling.
- Choosing embedding and referencing appropriately.

These practices make the API clean, scalable, and professional.
# justin-api-activity

