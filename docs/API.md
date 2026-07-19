> ⚠️ **Internal Engineering Document**
>
> This API Design Document defines all REST API endpoints for the WorkVerse MVP.
> It specifies request methods, request bodies, response bodies, authentication requirements, and error handling.
> This document acts as the backend implementation guide.

# 🌐 API Design Document

# WorkVerse

**Version:** 1.0

**Project:** WorkVerse

**Founder:** Mahammed Sirajuddin

**Prepared By:** WorkVerse Engineering Team

**Status:** Planning Phase

**Date:** July 2026

---

# 📑 Table of Contents

1. API Overview
2. Authentication
3. User APIs
4. Role APIs
5. Task APIs
6. Progress APIs
7. Certificate APIs
8. AI Mentor APIs
9. Response Format
10. Error Handling
11. API Security
12. Future APIs

---

# 1. API Overview

The WorkVerse backend follows the REST API architecture.

## Base URL

```

/api/v1

```

## Response Format

Every API returns JSON.

Example:

```json
{
  "success": true,
  "message": "Operation successful",
  "data": {}
}
```

---

# 2. Authentication APIs

## Google Login

### POST

```

/auth/google

```

Purpose

Authenticate users using Google OAuth.

Request

```json
{
  "googleToken": "token"
}
```

Success Response

```json
{
  "success": true,
  "token": "JWT_TOKEN",
  "user": {}
}
```

Error Codes

- 400 Bad Request
- 401 Unauthorized
- 500 Internal Server Error

---

# 3. User APIs

## Get Profile

### GET

```

/users/profile

```

Authentication

Required

Response

```json
{
  "name": "",
  "email": "",
  "college": "",
  "xp": 250,
  "level": 3,
  "dailyStreak": 8
}
```

---

## Update Profile

### PUT

```

/users/profile

```

Purpose

Update student profile.

---

# 4. Role APIs

## Get All Roles

### GET

```

/roles

```

Response

```json
[
  {
    "roleName": "Full Stack Developer"
  },
  {
    "roleName": "Backend Developer"
  },
  {
    "roleName": "SOC Analyst"
  }
]
```

---

## Get Role Details

### GET

```

/roles/:id

```

Returns complete information about the selected role.

---

# 5. Task APIs

## Get Tasks

### GET

```

/tasks/:roleId

```

Returns all tasks for the selected role.

---

## Get Single Task

### GET

```

/tasks/details/:taskId

```

---

## Submit Task

### POST

```

/tasks/submit

```

Request

```json
{
  "taskId": "",
  "solution": ""
}
```

Response

```json
{
  "score": 90,
  "feedback": "Excellent work!"
}
```

---

# 6. Progress APIs

## Get Progress

### GET

```

/progress

```

Response

```json
{
  "xp": 420,
  "level": 5,
  "completedTasks": 14,
  "dailyStreak": 10
}
```

---

# 7. Certificate APIs

## Get Certificates

### GET

```

/certificates

```

Returns all earned certificates.

---

## Download Certificate

### GET

```

/certificates/download/:certificateId

```

Downloads the selected certificate.

---

# 8. AI Mentor APIs

## Ask AI Mentor

### POST

```

/ai/chat

```

Request

```json
{
  "question": "Explain REST API"
}
```

Response

```json
{
  "answer": "REST APIs are..."
}
```

---

## Chat History

### GET

```

/ai/history

```

Returns previous AI conversations.

---

# 9. Standard Response Format

## Success

```json
{
  "success": true,
  "message": "Request successful",
  "data": {}
}
```

---

## Error

```json
{
  "success": false,
  "message": "Something went wrong",
  "error": {}
}
```

---

# 10. Error Handling

Common HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | Success |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

# 11. API Security

Every API must follow these rules:

- HTTPS only
- JWT Authentication
- Input Validation
- Data Sanitization
- Protected Routes
- Rate Limiting
- Secure Error Messages

Sensitive APIs require a valid JWT.

---

# 12. Future APIs

Future versions may include:

- Recruiter APIs
- Company APIs
- College APIs
- Notification APIs
- Payment APIs
- Leaderboard APIs
- Achievement APIs
- Resume APIs
- Interview APIs

---

# 📌 API Design Principles

Every API must be:

- RESTful
- Secure
- Consistent
- Easy to understand
- Versioned
- Scalable

---

# 📌 Engineering Philosophy

The WorkVerse API is designed to provide a clean separation between frontend and backend.

Every endpoint has a single responsibility and follows predictable request and response formats to simplify frontend integration and future maintenance.