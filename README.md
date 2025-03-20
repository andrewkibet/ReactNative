# ReactNative
React Native is a popular framework for building mobile applications using JavaScript and React. Here are some steps to get you started:

### Set up your development environment:

Install Node.js and npm (Node Package Manager)
Install React Native CLI or use Expo CLI for an easier setup
### Create a new React Native project:

Using React Native CLI: npx react-native init MyNewProject
Using Expo CLI: npx create-expo-app MyNewProject
### Run your application:

For React Native CLI: npx react-native run-android or npx react-native run-ios
For Expo CLI: npx expo start
### Learn the basics of React Native:

Understand the core components (View, Text, Image, ScrollView, etc.)
Learn about state and props
Get familiar with navigation using libraries like React Navigation
### Build and debug your application:

Use the emulator/simulator to test your app
Debug using React DevTools and other debugging tools
Explore advanced topics:

### Learn about performance optimization
Explore native modules and how to bridge them
Understand the deployment process for both Android and iOS

# MongoDB 
MongoDB is a NoSQL database that stores data in a document-oriented format using JSON-like structures called BSON (Binary JSON). It is designed for high performance, scalability, and flexibility, making it a popular choice for modern web applications.

## **Key Features of MongoDB:**

1.Schema-less (Flexible Schema) – Unlike SQL databases, MongoDB does not require a fixed table schema, allowing you to store different types of data in the same collection.

2.Document-Oriented – Data is stored in BSON documents, which makes it easy to represent complex structures.

3.Scalability – Supports horizontal scaling through sharding (distributing data across multiple servers).

4.High Performance – Faster read/write operations due to its document model.

5.Indexing – Supports indexing to optimize query performance.

6.Aggregation Framework – Provides powerful data processing and transformation capabilities.

7.Replication – Supports data redundancy using Replica Sets to ensure data availability.

MongoDB vs SQL Databases
Feature	MongoDB (NoSQL)	SQL Databases (MySQL, PostgreSQL)
Data Model	Document-based (JSON/BSON)	Table-based (Rows & Columns)
Schema	Flexible (No predefined schema)	Fixed schema (Strict structure)
Scalability	Horizontally scalable (Sharding)	Vertically scalable (Scaling up)
Query Language	MongoDB Query Language (MQL)	SQL (Structured Query Language)
Transactions	Supports ACID transactions (since MongoDB 4.0)	Fully ACID-compliant

## When to Use MongoDB?
    Big Data applications
    E-commerce platforms
    Real-time analytics
    Content management systems
    Mobile and web applications


The **JWT_SECRET** is a secret key used to sign and verify JWT (JSON Web Tokens) for authentication in your backend.

# 🔹 What is JWT (JSON Web Token)?
JWT is a secure way to handle user authentication. When a user logs in:

The server creates a JWT (token) containing user details.

The JWT is signed using the JWT_SECRET to ensure it's not tampered with.

The token is sent to the client (mobile app/browser).

For every request, the client sends the token to the server.

The server verifies the token using the JWT_SECRET.

# 🔹 Why is JWT_SECRET Important?
Prevents hackers from forging valid tokens.

Ensures only the server can verify tokens (since only the server knows the secret key).

If someone modifies a JWT, the verification will fail.

## 🔹 How JWT Works (Example)
1️⃣ Signing a JWT (Creating a Token)
When a user logs in, the server creates a JWT:

js
Copy
Edit
const jwt = require('jsonwebtoken');

const token = jwt.sign(
  { userId: 123, email: "user@example.com" }, // User data
  process.env.JWT_SECRET, // Secret key
  { expiresIn: "1h" } // Expiry time
);

console.log(token);
✅ The token is sent to the user.

2️⃣ Verifying a JWT (Checking Token Validity)
When the user makes a request, the server verifies the token:

js
Copy
Edit
const decoded = jwt.verify(token, process.env.JWT_SECRET);
console.log(decoded); // { userId: 123, email: "user@example.com", iat: 1610000000, exp: 1610003600 }
✅ If the token is valid, the user is authenticated!

🔹 What Happens If JWT_SECRET is Compromised?
If someone steals your JWT_SECRET, they can generate fake tokens and log in as any user.

To fix this, you must change the secret and log out all users.

🔹 Best Practices for JWT_SECRET
✔ Use a long, random key (at least 32 characters).
✔ Don't share it in public repositories (like GitHub).
✔ Store it in .env, never in the code.
✔ Rotate the key if there's a security risk.

🔹 Summary
JWT_SECRET is used to sign and verify JWTs.

It ensures that only the server can validate tokens.

It's essential for secure authentication.



