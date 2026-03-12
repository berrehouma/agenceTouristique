# Express.js Essentials for MERN Tourism Platform

## 1. Introduction

Express.js is a minimal web framework for **Node.js** used to build web servers and APIs.

In the MERN stack architecture:

React → Express → MongoDB

- React: frontend
- Express: backend API
- MongoDB: database

Express handles requests from the client, processes them, and returns responses.

---

# 2. Installation

Initialize a Node.js project:

```
npm init -y
```

Install Express:

```
npm install express
```

---

# 3. Creating a Basic Server

Create a file called:

```
server.js
```

Example:

```js
const express = require("express")

const app = express()

const PORT = 3000

app.listen(PORT, () => {
 console.log("Server running on port 3000")
})
```

Run the server:

```
node server.js
```

---

# 4. Routes

Routes define how the server responds to client requests.

Example route:

```js
app.get("/", (req, res) => {
 res.send("API is running")
})
```

Open in browser:

```
http://localhost:3000
```

---

# 5. HTTP Methods

Express supports common HTTP methods used in REST APIs.

| Method | Purpose |
|------|------|
GET | retrieve data |
POST | create data |
PUT | update data |
DELETE | remove data |

Example:

```js
app.get("/trips", (req,res)=>{
 res.send("List of trips")
})
```

---

# 6. Middleware

Middleware functions run before the request reaches the route.

Example:

```js
app.use(express.json())
```

This allows the server to read **JSON data** sent by the client.

---

# 7. Receiving Data from Client

When a client sends data (for example from a form or frontend application), it can be accessed using:

```
req.body
```

Example:

```js
app.post("/trips",(req,res)=>{

 const trip = req.body

 res.json(trip)

})
```

---

# 8. Route Parameters

Parameters allow dynamic values in URLs.

Example:

```
/trips/:id
```

Example code:

```js
app.get("/trips/:id",(req,res)=>{

 const id = req.params.id

 res.send("Trip id: " + id)

})
```

---

# 9. Query Parameters

Used for filtering or pagination.

Example request:

```
/trips?page=1&limit=10
```

Example code:

```js
app.get("/trips",(req,res)=>{

 const page = req.query.page

 res.send(page)

})
```

---

# 10. Project Structure (Recommended)

A simple structure for Express backend:

```
backend
│
├── server.js
├── models
├── routes
├── controllers
└── config
```

This structure helps keep the project organized and scalable.

---

# 11. Why Express for our Project

Express is used in our Tourism SaaS platform because:

- lightweight and fast
- easy to build REST APIs
- integrates well with MongoDB
- widely used in MERN stack applications

---

# Conclusion

Express.js provides a simple and flexible way to build backend APIs.  
It allows handling requests, managing routes, processing data, and connecting with databases such as MongoDB.