# TABLE RELATIONSHIPS

Users → Customers (One-to-One)

Each registered user can have one customer profile
Links via user_id foreign key
Enables tracking of both authentication and detailed customer information

Customers → Reservations (One-to-Many)

One customer can make multiple reservations
customer_id links reservations to specific customers
Tracks full reservation history per customer

Customers → Contact Messages (One-to-Many)

Customers can send multiple contact messages
-- Optional relationship via customer_id
Allows tracking of all customer communications

Customers → Customer Preferences (One-to-One)

Each customer has a single preferences record
Stores personalized customer settings and preferences

CRITICAL CONSTRAINTS:

Email validation across users and contact messages
Date validation in reservations
Price and capacity constraints in rooms
Session token and expiration management

RECOMMENDED IMPLEMENTATION CONSIDERATIONS:

Use prepared statements for security
Implement database-level encryption for sensitive fields
Create regular backup procedures
Set up proper indexing for performance
Implement soft delete where possible

POTENTIAL FUTURE EXTENSIONS:

Add loyalty program tracking
Implement more detailed customer segmentation
Create advanced reporting tables