# alx-airbnb-project-documentation

```mermaid
graph TD
  A[Airbnb Backend System]
  
  A --> B[User Management]
  B --> C[Register (Guest/Host)]
  B --> D[Login (JWT, OAuth)]
  B --> E[Profile Management]

  A --> F[Property Listings]
  F --> G[Add/Edit/Delete Listings]
  F --> H[Set Amenities & Availability]

  A --> I[Search & Filter]
  I --> J[Location]
  I --> K[Price Range]
  I --> L[Guests & Amenities]
  I --> M[Pagination]

  A --> N[Booking System]
  N --> O[Create Booking]
  N --> P[Cancel Booking]
  N --> Q[Booking Status]

  A --> R[Payments]
  R --> S[Stripe / PayPal]
  R --> T[Guest Payment]
  R --> U[Host Payout]

  A --> V[Reviews]
  V --> W[Guest Reviews]
  V --> X[Linked to Booking]
  V --> Y[Host Response]

  A --> Z[Notifications]
  Z --> ZA[Email Notifications]
  Z --> ZB[In-app Notifications]

  A --> AA[Admin Dashboard]
  AA --> AB[User Management]
  AA --> AC[Booking Management]
  AA --> AD[Payments Oversight]
  AA --> AE[Listings Moderation]
