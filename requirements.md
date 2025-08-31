# Airbnb Backend Requirements

This document outlines the technical and functional requirements for three key backend features of the Airbnb system: **User Authentication**, **Property Management**, and **Booking System**.

---

## 1. User Authentication

### Functional Requirements

- Users must be able to register with **username, email, and password**.
- The system must validate inputs and prevent duplicate email/username registration.
- Users must be able to log in using email and password.
- Passwords must be stored securely using hashing (e.g., bcrypt).
- Authentication tokens (JWT or session-based) must be generated upon successful login.

### API Endpoints

- **POST** `/api/auth/register`

  - **Input:** `{ "username": "string", "email": "string", "password": "string" }`
  - **Output (201):** `{ "message": "User registered successfully", "user_id": 1 }`
  - **Error (400):** `{ "error": "Invalid or duplicate registration" }`

- **POST** `/api/auth/login`
  - **Input:** `{ "email": "string", "password": "string" }`
  - **Output (200):** `{ "token": "jwt_token", "user_id": 1 }`
  - **Error (401):** `{ "error": "Invalid credentials" }`

### Validation Rules

- Email must follow a valid format.
- Password must be at least 8 characters with letters and numbers.
- Username must be unique and non-empty.

### Performance Criteria

- Registration and login response time < 500ms under normal load.
- Token expiration: 24 hours.

---

## 2. Property Management

### Functional Requirements

- Registered users must be able to **list properties** with details (title, description, location, price, availability).
- Users must be able to **update** or **delete** their own property listings.
- Properties must be retrievable via search and filtering.

### API Endpoints

- **POST** `/api/properties/`

  - **Input:** `{ "title": "string", "description": "string", "location": "string", "price": number, "availability": "boolean" }`
  - **Output (201):** `{ "property_id": 1, "message": "Property created successfully" }`

- **GET** `/api/properties/`

  - **Output (200):** `[ { "property_id": 1, "title": "Cozy Apartment", "price": 100 } ]`

- **PUT** `/api/properties/{id}/`

  - **Input:** `{ "title": "string", "price": number }`
  - **Output (200):** `{ "message": "Property updated successfully" }`

- **DELETE** `/api/properties/{id}/`
  - **Output (204):** No content

### Validation Rules

- Title and description cannot be empty.
- Price must be greater than 0.
- Location must be a valid string.

### Performance Criteria

- Properties retrieval must support pagination.
- Property search results must return within 1s under 1000 requests/minute.

---

## 3. Booking System

### Functional Requirements

- Users must be able to **book available properties** for specific dates.
- The system must prevent **double booking**.
- Users must be able to **view and cancel bookings**.

### API Endpoints

- **POST** `/api/bookings/`

  - **Input:** `{ "user_id": 1, "property_id": 1, "start_date": "YYYY-MM-DD", "end_date": "YYYY-MM-DD" }`
  - **Output (201):** `{ "booking_id": 1, "message": "Booking confirmed" }`
  - **Error (409):** `{ "error": "Property not available" }`

- **GET** `/api/bookings/{user_id}/`

  - **Output (200):** `[ { "booking_id": 1, "property_id": 1, "start_date": "2025-09-01", "end_date": "2025-09-05" } ]`

- **DELETE** `/api/bookings/{id}/`
  - **Output (200):** `{ "message": "Booking cancelled successfully" }`

### Validation Rules

- Dates must follow `YYYY-MM-DD` format.
- End date must be later than start date.
- Property must exist and be available.

### Performance Criteria

- Booking confirmation must complete in < 1s.
- System must handle at least 500 concurrent booking requests without failure.

---

# ✅ Summary

This requirements document defines the expected behavior, validation rules, and performance targets for three critical backend features of the Airbnb project.
