# Airbnb Clone – Use Case Diagram

This use case diagram illustrates the interactions between **users (Guest, Host, Admin, Payment Gateway)** and the **Airbnb Clone system**. It highlights the main features and functionalities identified in Task 0.

---

## Key Actors

- **Guest** – Registers, logs in, searches properties, makes bookings, and payments.
- **Host** – Manages properties (create, update, delete, set availability).
- **Admin** – Manages the system (approve users/properties, handle disputes, monitor activities).
- **Payment Gateway** – Processes and verifies payments securely.

---

## Main Use Cases

1. **User Authentication**

   - Register new account
   - Login to the system
   - Manage profile

2. **Property Management (Host)**

   - Add/Edit/Delete property
   - Manage availability
   - View bookings for owned properties

3. **Booking System (Guest)**

   - Search properties by filters (location, price, date)
   - View property details
   - Create booking
   - Cancel booking

4. **Payments**

   - Make payment for booking
   - Verify payment
   - Request refund (if applicable)

5. **Admin Management**
   - Approve or suspend users
   - Approve or remove property listings
   - Handle reports and disputes

---

## Diagram

Below is the exported **use case diagram**:

![Use Case Diagram](./use-case-diagram.png)

---

## Notes

- The diagram was created with **Draw.io**.
- It captures all key system interactions.
- Relationships:
  - Solid lines = actor interactions
  - “Include” = mandatory relationships (e.g., Booking → Payment)
  - “Extend” = optional/conditional actions (e.g., Refund extends Payment)
