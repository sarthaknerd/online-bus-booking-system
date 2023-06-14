# Online Bus Booking System

Group: Java Zedi

## Entities and Relationships

![ER-Diagram](https://github.com/srijan-singh/online-bus-booking-system/blob/main/res/ER.jpeg)

## Entity Tables

### User
- id: integer, primary key
- name: varchar
- email: varchar
- password: varchar

### BusRoute
- id: integer, primary key
- origin: varchar
- destination: varchar

### BusSchedule
- id: integer, primary key
- bus_route_id: integer, foreign key to BusRoute.id
- operator_name: varchar
- operator_email: varchar
- departure_time: timestamp
- arrival_time: timestamp
- price: float

### Booking
- id: integer, primary key
- user_id: integer, foreign key to User.id
- schedule_id: integer, foreign key to BusSchedule.id
- seat_number: integer
- status: varchar

### Cancellation
- id: integer, primary key
- booking_id: integer, foreign key to Booking.id
- user_id: integer, foreign key to User.id
- reason: varchar

### PaymentMethod
- id: integer, primary key
- name: varchar
- description: varchar

### Payment
- id: integer, primary key
- booking_id: integer, foreign key to Booking.id
- amount: float
- payment_method_id: integer, foreign key to PaymentMethod.id

### PaymentTransaction
- id: integer, primary key
- payment_id: integer, foreign key to Payment.id
- transaction_date: timestamp
- transaction_amount: float
- transaction_status: varchar

### Review
- id: integer, primary key
- user_id: integer, foreign key to User.id
- rating: integer
- comment: varchar
