# Airbnb Clone – Features and Functionalities

This document outlines the **core features and functionalities** required for the backend of the Airbnb Clone project. The diagram included (`features-functionalities.png`) was created using **Draw.io** to visualize all major components.

---

## Key Features

### 1. User Authentication & Authorization

- User Registration (sign up with email & password)
- User Login (JWT-based authentication)
- Role Management (admin, host, guest)
- Password Encryption (bcrypt)

### 2. User Profile Management

- View and update personal details
- Upload profile photo
- Manage verification status

### 3. Property Management (Host Side)

- Add new properties with details (title, description, location, amenities, price, images)
- Edit or delete property listings
- Manage availability (calendar system)

### 4. Booking System (Guest Side)

- Search properties (location, price, date filters)
- View property details
- Create booking reservations
- Manage bookings (update/cancel)

### 5. Payments

- Secure payment processing via third-party API (Stripe/PayPal)
- Payment verification
- Refunds and cancellations

### 6. Admin Panel (System Management)

- Monitor users, properties, and bookings
- Approve or suspend listings
- Handle disputes and reports

---

## Supporting Features

- Notifications (booking confirmations, reminders)
- Reviews & Ratings for properties
- Secure data handling and validation
- Logging & error handling

---

## Diagram

Below is the high-level visualization of these features:

![Features and Functionalities](./features-functionalities.png)

---
