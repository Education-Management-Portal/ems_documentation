---
sidebar_position: 1
---

# Getting Started

Welcome to the **Educational Management API Documentation**! This comprehensive API enables you to manage schools, students, and certificates for Imo State's educational system.

## What you'll need

- **Node.js** version 16 or above
- **Valid API credentials** (contact admin for access)
- **Basic understanding** of REST APIs and HTTP methods

## Quick Start

### 1. Authentication

First, authenticate to get your JWT token:

```bash
curl -X POST "https://api.edu-management.gov.ng/v1/auth/admin/login" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "your-email@example.com",
    "password": "your-password"
  }'
```

### 2. Make Your First API Call

Use the JWT token to fetch schools:

```bash
curl -X GET "https://api.edu-management.gov.ng/v1/schools" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

### 3. Upload Certificate Data

Upload Excel files with student data:

```bash
curl -X POST "https://api.edu-management.gov.ng/v1/certificates/bec" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN" \
  -F "file=@certificates.xlsx"
```

## Key Features

- 🏫 **School Management** - Create, read, update, and delete schools
- 👨‍🎓 **Student Management** - Manage student records and information  
- 📜 **Certificate Processing** - Upload and process certificate data via Excel
- 🔍 **Advanced Search** - Search across all certificate types
- 💳 **Payment Integration** - Handle payments for certificate services
- 📄 **PDF Generation** - Generate downloadable certificates

## API Base URLs

- **Production**: `https://api.edu-management.gov.ng/v1`
- **Development**: `http://localhost:3000/api`

## Support

Need help? Contact us at [support@edu-management.gov.ng](mailto:support@edu-management.gov.ng)

---