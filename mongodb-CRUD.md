1. Advantages of using Mongoose over native MongoDB driver

Mongoose provides:

Schema-based structure → Define fields, types, validation
Validation built-in → Required, min/max, custom rules
Middleware (hooks) → Run logic before/after operations
Easy relationships → Using populate()
Cleaner code → More readable than native driver

 Native MongoDB driver is flexible but requires more manual work.

2. Difference: findOneAndUpdate() vs updateOne()
Feature	findOneAndUpdate()	updateOne()
Returns document	✅ Yes (updated doc)	❌ No (only result info)
Use case	When you need updated data	When just updating is enough
Options	Can return old/new doc	Limited options

 Example:

Model.findOneAndUpdate({ name: "Divya" }, { age: 22 }, { new: true })
Model.updateOne({ name: "Divya" }, { age: 22 })
3. Purpose of Middleware in Mongoose

Middleware (hooks) in Mongoose are functions that run before or after database operations.

 Types:

Pre middleware → Before action (e.g., save)
Post middleware → After action

 Use cases:

Password hashing before saving
Logging operations
Validation or modification of data
4. Pagination in Mongoose

Pagination is implemented using skip() and limit():

const page = 1;
const limit = 10;

Model.find()
  .skip((page - 1) * limit)
  .limit(limit);

 Explanation:

skip() → skips previous records
limit() → number of records per page
5. Embedding vs Referencing in MongoDB
🔹 Embedding (Nested documents)

 Store data inside one document

Use when:

Data is related and small
Read operations are frequent

Example: User with address inside same document

🔹 Referencing (Using ObjectId)

 Store data in separate collections

Use when:

Data is large
Needs reuse across multiple documents
Relationships are complex

Example: Users and Orders in separate collectionss