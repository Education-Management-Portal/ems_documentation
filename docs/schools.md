---
sidebar_position: 3
---

# Schools Management

Manage schools and educational institutions in the system.

## Get All Schools

Retrieve a paginated list of all schools with optional filtering.

```bash
GET /schools?lga=Owerri North&page=1&limit=20
```

**Query Parameters:**
- `lga` (optional) - Filter by Local Government Area
- `page` (optional) - Page number (default: 1)  
- `limit` (optional) - Items per page (default: 20, max: 100)
- `search` (optional) - Search schools by name

**Response:**
```json
{
  "success": true,
  "data": [
    {
      "_id": "64f7a8b2e4b0c1234567890a",
      "schoolId": "SCH001", 
      "name": "Government Secondary School Owerri",
      "lga": "Owerri North",
      "createdAt": "2024-09-16T10:30:00Z"
    }
  ],
  "pagination": {
    "currentPage": 1,
    "totalPages": 5,
    "totalItems": 95
  }
}
```

## Create School

Register a new school in the system.

```bash
POST /schools
Authorization: Bearer YOUR_JWT_TOKEN
```

**Request Body:**
```json
{
  "schoolId": "SCH002",
  "name": "Community Secondary School Mbaise", 
  "lga": "Mbaise"
}
```

## Update School

```bash
PUT /schools/SCH001
Authorization: Bearer YOUR_JWT_TOKEN
```

## Delete School

```bash
DELETE /schools/SCH001
Authorization: Bearer YOUR_JWT_TOKEN
```

---