---
sidebar_position: 2
---

# Authentication

The Educational Management API uses **JWT (JSON Web Tokens)** for authentication. All protected endpoints require a valid JWT token in the Authorization header.

## Getting Your Token

### Admin Login

```bash
POST /auth/admin/login
```

**Request Body:**
```json
{
  "email": "admin@edu-management.gov.ng",
  "password": "your-secure-password"
}
```

**Response:**
```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "64f7a8b2e4b0c1234567890a",
    "email": "admin@edu-management.gov.ng",
    "role": "admin"
  }
}
```

## Using the Token

Include the JWT token in the Authorization header for all protected endpoints:

```bash
Authorization: Bearer YOUR_JWT_TOKEN
```

### Example Request

```bash
curl -X GET "https://api.edu-management.gov.ng/v1/schools" \
  -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
```

## Token Expiration

- Tokens are valid for **24 hours**
- After expiration, you'll receive a `401 Unauthorized` response
- Use the refresh endpoint or re-authenticate to get a new token

## Security Best Practices

- ✅ Store tokens securely (not in localStorage for production)
- ✅ Use HTTPS in production
- ✅ Implement token refresh logic
- ✅ Never expose tokens in URLs or logs

---