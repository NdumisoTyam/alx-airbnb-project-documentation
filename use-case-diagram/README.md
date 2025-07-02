usecaseDiagram
    actor Guest
    actor Host
    actor System

    Guest --> (Register)
    Host --> (Register)

    Guest --> (Browse Properties)
    Host --> (List Property)

    Guest --> (Book Property)
    Guest --> (Make Payment)

    System --> (Process Payment)
    System --> (Confirm Booking)

    Guest --> (Write Review)
    Guest --> (Manage Bookings)
    Host --> (Manage Listings)
    Host --> (Manage Bookings)
