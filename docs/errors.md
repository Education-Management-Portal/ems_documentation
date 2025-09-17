---
sidebar_position: 5
---

# Error Handling

The API uses conventional HTTP response codes and returns error details in JSON format.

## HTTP Status Codes

- `200` - OK: Request successful
- `201` - Created: Resource created successfully  
- `400` - Bad Request: Invalid request data
- `401` - Unauthorized: Invalid or missing authentication
- `403` - Forbidden: Insufficient permissions
- `404` - Not Found: Resource not found
- `409` - Conflict: Resource already exists
- `500` - Internal Server Error: Server error

## Error Response Format

All errors return a consistent JSON structure:

```json
{
  "success": false,
  "error": "Error Type",
  "message": "Human-readable error message",
  "details": "Additional error details (optional)"
}
```

## Common Errors

### Authentication Errors

```json
{
  "success": false,
  "error": "Unauthorized",
  "message": "Invalid authentication credentials"
}
```

### Validation Errors

```json
{
  "success": false,
  "error": "Bad Request", 
  "message": "Invalid input data provided",
  "details": "Email is required"
}
```

### File Upload Errors

```json
{
  "success": false,
  "error": "Bad Request",
  "message": "Invalid file type. Please upload an Excel file (.xlsx or .xls)."
}
```

## Error Handling Best Practices

1. **Always check the `success` field** before processing data
2. **Display user-friendly messages** from the `message` field  
3. **Log technical details** from the `details` field for debugging
4. **Implement retry logic** for 5xx errors
5. **Handle token expiration** by re-authenticating on 401 errors