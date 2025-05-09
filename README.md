# airbnb-clone-project
# Team Roles
  Business analyst (BA)
      Understands customer’s business processes
      Translates customer business needs into requirements
    A business analyst dives deep into a customer’s workflows and analyzes stakeholder feedback to help clients formulate their wants and align a customer’s vision with what a development team is producing. They translate an abstract product idea into a set of tangible requirements.

  Product owner (PO)
      Holds responsibility for a product vision and evolution
      Makes sure the final product meets customer requirements
    Holding more responsibility for a product’s success than any other development team member, a product owner is a decision-maker. Balancing both business needs and market trends, they define a business strategy, shape up the product vision, make sure it satisfies customer needs, and manage a product backlog. Associated mainly with flexible Agile environments, a product owner is particularly useful in scenarios where requirements and workflows frequently change.

The responsibilities of a BA and a PO sound quite similar. What’s the difference between the two, and is there a need for both in one project?

The critical difference is that a product owner provides the vision of a product without diving deep into how it is technically implemented, while a business analyst bridges the gap between a customer and a team, being a bit more on the technical side. So, a PO is more customer-oriented, while a BA is often more focused on the technicalities of the project. Professional business analysts are usually qualified to take over some of a product owner’s tasks, like managing the product backlog and modeling workflows, among other responsibilities.

In outsourcing scenarios, a product owner can be someone from the client’s side, a startup founder, for example. They possess deep domain expertise but might lack technical knowledge. They can work in tandem with business analysts to fine-tune product requirements.

# Technology Stack
1. Django
Purpose: Django is a high-level Python web framework used for building web applications rapidly.

In a project: It helps developers build RESTful APIs or full-stack web apps, handling everything from URL routing to database models and user authentication.

2. PostgreSQL
Purpose: PostgreSQL is an open-source relational database management system (RDBMS).

In a project: It stores and manages structured data (like user records, sensor data, logs), and integrates well with Django via libraries like psycopg2.

3. GraphQL
Purpose: GraphQL is a query language for APIs and a runtime for executing those queries.

In a project: It allows clients (like front-end apps) to fetch only the data they need, making APIs faster and more flexible compared to traditional REST APIs.

# Database Design
1. User
Fields:

id: Unique identifier

name: Full name of the user

email: Email address (used for login)

password_hash: Encrypted password

role: Indicates if the user is a host or guest

Relationships:

A user can list multiple properties (if a host).

A user can make multiple bookings (if a guest).

A user can leave multiple reviews.

2. Property
Fields:

id: Unique property ID

title: Name or headline of the listing

description: Details about the property

location: Geographic location/address

price_per_night: Cost per night in currency

Relationships:

A property is owned by one user (host).

A property can have multiple bookings.

A property can have multiple reviews.

3. Booking
Fields:

id: Unique booking ID

user_id: The guest who made the booking

property_id: The property being booked

start_date: Check-in date

end_date: Check-out date

Relationships:

A booking is made by one user (guest).

A booking is linked to one property.

A booking may result in one payment.

4. Review
Fields:

id: Unique review ID

user_id: User who wrote the review

property_id: Property being reviewed

rating: Numeric score (e.g., 1–5 stars)

comment: Text of the review

Relationships:

A review is written by one user.

A review is linked to one property.

5. Payment
Fields:

id: Unique payment ID

booking_id: Related booking

amount: Total amount paid

payment_method: Card, PayPal, etc.

status: Paid, Pending, Failed

Relationships:

A payment is linked to one booking.

A payment may be used to verify booking confirmation.
