---
sidebar_position: 4
---

# Certificate Management

Upload and manage student certificates and examination results.

## Upload BEC Certificates

Upload Excel files containing BEC (Basic Education Certificate) results.

```bash
POST /certificates/bec
Authorization: Bearer YOUR_JWT_TOKEN
Content-Type: multipart/form-data
```

**Request:**
- File: Excel file (.xlsx or .xls) containing certificate data
- Maximum file size: 10MB

**Excel Format Requirements:**

Your Excel file should have these columns:
- `Exam No.` - Student examination number
- `Name` - Student full name  
- `Sex` - M or F
- `Age` - Student age
- `School` - School name
- Subject columns with CA and Exam scores

**Response:**
```json
{
  "success": true,
  "message": "Successfully imported all 150 records!",
  "totalRecords": 150,
  "validRecords": 150,
  "duplicatesSkipped": 0,
  "processedCount": 150,
  "errorCount": 0
}
```

## Get Certificate by Exam Number

```bash
GET /certificates/bec/BEC2024001
Authorization: Bearer YOUR_JWT_TOKEN
```

## Search Results

```bash
GET /search/results?examNumber=BEC2024001&certificateType=bec
```

**Query Parameters:**
- `examNumber` - Student exam number
- `name` - Student name (partial match)
- `certificateType` - Type of certificate (bec, waec, neco, jamb)
- `examYear` - Examination year
- `schoolId` - School identifier

---