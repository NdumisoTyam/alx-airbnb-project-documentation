# 📘 Backend Feature Specifications

---

## 🔐 1. User Authentication

### ✅ Functional Requirements
- Users must be able to register with a unique email and password.
- Users must log in to access authenticated routes.
- Passwords must be securely hashed (e.g., bcrypt).

### 🔧 API Endpoints

| Method | Endpoint            | Description          |
|--------|---------------------|----------------------|
| POST   | `/api/auth/register` | Register a new user  |
| POST   | `/api/auth/login`    | Log in a user        |

### 📥 Input Specifications

- `email`: string, required, unique, valid format  
- `password`: string, required, min 8 characters

### 📤 Output (Success)

```json
{
  "user": {
    "id": "123",
    "email": "user@example.com"
  },
  "token": "JWT_TOKEN_HERE"
}
```

### ❌ Output (Error)

```json
{
  "error": "Invalid credentials"
}
```

### ✅ Validation Rules

- Unique email  
- Minimum password length: 8 characters  
- JWT token returned on login

### ⚙️ Performance Criteria

- Response time: ≤ 500ms  
- Password hashing using bcrypt (≥ 10 salt rounds)  
- Login rate limit: 5 attempts/minute/IP

---

## 🏠 2. Property Management

### ✅ Functional Requirements

- Hosts can add, update, delete, and view properties.
- Each property must include title, location, price, and availability.

### 🔧 API Endpoints

| Method | Endpoint                  | Description        |
|--------|---------------------------|--------------------|
| POST   | `/api/properties`         | Add a new property |
| GET    | `/api/properties/:id`     | Get property by ID |
| PUT    | `/api/properties/:id`     | Update property    |
| DELETE | `/api/properties/:id`     | Delete property    |
| GET    | `/api/properties?city=CT` | Filter by location |

### 📥 Input Specifications

- `title`: string, required  
- `description`: string, optional  
- `price`: number, required  
- `location`: string, required  
- `available_dates`: array of date ranges  
- `images`: array of image URLs (optional)

### 📤 Output Example

```json
{
  "id": "prop123",
  "title": "Modern Loft in Cape Town",
  "price": 1200,
  "location": "Cape Town",
  "hostId": "host789"
}
```

### ✅ Validation Rules

- Title and location are required  
- Price must be a positive number  
- Only property owner can modify or delete

### ⚙️ Performance Criteria

- Search/filter results: ≤ 1s  
- Create/update/delete operations: ≤ 800ms

---

## 📅 3. Booking System

### ✅ Functional Requirements

- Guests can book a property for specific dates.
- System validates date availability.
- Bookings are confirmed only after payment.

### 🔧 API Endpoints

| Method | Endpoint                  | Description           |
|--------|---------------------------|-----------------------|
| POST   | `/api/bookings`           | Create new booking    |
| GET    | `/api/bookings/:id`       | Get booking by ID     |
| GET    | `/api/users/:id/bookings` | List bookings by user |

### 📥 Input Specifications

- `propertyId`: string, required  
- `guestId`: string, required  
- `checkIn`: ISO date, required  
- `checkOut`: ISO date, required  
- `paymentMethod`: string (e.g., "card"), required

### 📤 Output Example

```json
{
  "bookingId": "b123",
  "propertyId": "p456",
  "guestId": "u789",
  "checkIn": "2025-07-20",
  "checkOut": "2025-07-25",
  "status": "confirmed"
}
```

### ✅ Validation Rules

- Check-in date must be before check-out date  
- Property must be available for the date range  
- Payment must be successful before confirmation

### ⚙️ Performance Criteria

- Availability check: ≤ 300ms  
- Booking and payment combined: ≤ 2s  
- Prevent duplicate bookings with idempotency logic

---
