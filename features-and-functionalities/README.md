# alx-airbnb-project-documentation

```mermaid
graph TD
  A["Airbnb Backend System"]

  A --> B1["User Management"]
  B1 --> B2["Register - Guest or Host"]
  B1 --> B3["Login - JWT, OAuth"]
  B1 --> B4["Profile Management"]

  A --> C1["Property Listings"]
  C1 --> C2["Add/Edit/Delete Listings"]
  C1 --> C3["Amenities and Availability"]

  A --> D1["Search and Filter"]
  D1 --> D2["Search by Location"]
  D1 --> D3["Price Range"]
  D1 --> D4["Guests and Amenities"]
  D1 --> D5["Pagination"]

  A --> E1["Booking System"]
  E1 --> E2["Create Booking"]
  E1 --> E3["Cancel Booking"]
  E1 --> E4["Booking Status Tracking"]

  A --> F1["Payments"]
  F1 --> F2["Stripe or PayPal Integration"]
  F1 --> F3["Guest Payments"]
  F1 --> F4["Host Payouts"]

  A --> G1["Reviews"]
  G1 --> G2["Guest Review"]
  G1 --> G3["Linked to Booking"]
  G1 --> G4["Host Response"]

  A --> H1["Notifications"]
  H1 --> H2["Email Alerts"]
  H1 --> H3["In-App Notifications"]

  A --> I1["Admin Dashboard"]
  I1 --> I2["Manage Users"]
  I1 --> I3["Manage Listings"]
  I1 --> I4["Manage Bookings"]
  I1 --> I5["Manage Payments"]
