# Airbnb Clone Backend — Requirement Specifications

This document details the **technical and functional requirements** for core backend features of the Airbnb Clone project.  
It includes API endpoints, input/output specifications, validation rules, and performance criteria.

---

## 1. User Authentication

**Objective:** Enable secure registration, login, and profile management for users (guests, hosts, and admins).

### API Endpoints
| Endpoint               | Method | Description |
|------------------------|--------|-------------|
| `/api/auth/register`   | POST   | Register a new user |
| `/api/auth/login`      | POST   | Authenticate a user and return JWT |
| `/api/auth/profile`    | GET    | Retrieve current user profile |
| `/api/auth/profile`    | PUT    | Update user profile |

### Input Specifications
- **Register**
  ```json
  {
    "first_name": "string, required",
    "last_name": "string, required",
    "email": "string, required, valid email, unique",
    "password": "string, required, min 8 chars",
    "role": "enum ['guest','host']"
  }
