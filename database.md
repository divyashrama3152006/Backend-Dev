1. SQL vs NoSQL (Key Differences with Examples)
Feature	SQL Databases	NoSQL Databases
Structure	Table-based (rows & columns)	Document, key-value, graph
Schema	Fixed schema	Flexible schema
Scalability	Vertical scaling	Horizontal scaling
Data type	Structured data	Structured + unstructured
Examples	MySQL, PostgreSQL	MongoDB, Cassandra


SQL → Bank system (fixed structure)
NoSQL → Social media app (dynamic data)

2. CAP Theorem

CAP theorem states that a distributed system can only guarantee two out of three:

C (Consistency) → Same data on all nodes
A (Availability) → System always responds
P (Partition Tolerance) → Works despite network failures

 Why not all three?
Because during a network partition, the system must choose:

Either return correct data (Consistency)
Or keep responding (Availability)

It cannot guarantee both at the same time.

3. When to Prefer MongoDB

Use MongoDB in these cases:

Flexible schema needed
→ Example: User profiles with different fields
Large-scale applications
→ Example: E-commerce platforms handling huge data
Real-time data / fast development
→ Example: Chat apps, IoT systems

4. Why MongoDB Uses BSON

MongoDB uses BSON (Binary JSON) because:

Faster to parse than JSON
Supports more data types (Date, Binary, ObjectId)
Efficient storage and indexing
Better performance for large datasets

 JSON is text-based, BSON is binary → more efficient

5. MongoDB Query
db.students.find({
  GPA: { $gt: 3.5 },
  course: "CS101"
})


GPA > 3.5
Enrolled in "CS101"