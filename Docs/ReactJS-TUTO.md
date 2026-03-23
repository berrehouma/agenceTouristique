# React.js Essentials for MERN Tourism Platform

## 1. Introduction

React.js is a JavaScript library used to build modern user interfaces.

In the MERN stack architecture:

React -> Express -> MongoDB

- React: frontend UI
- Express: backend API
- MongoDB: database

React helps us build pages using reusable components.

---

# 2. Installation

Create a React project with Vite (recommended):

```bash
npm create vite@latest frontend -- --template react
```

Go to project folder:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

---

# 3. Basic Project Structure

A common React structure:

```text
frontend
|
|-- public
|-- src
|   |-- assets
|   |-- components
|   |-- pages
|   |-- App.jsx
|   `-- main.jsx
|-- package.json
`-- vite.config.js
```

- `main.jsx`: app entry point
- `App.jsx`: main root component
- `components`: reusable UI blocks
- `pages`: screen-level views

---

# 4. Creating a Component

A component is a reusable UI piece.

Example:

```jsx
function Navbar() {
  return <h2>Tourism Platform</h2>
}

export default Navbar
```

Use it in App:

```jsx
import Navbar from "./components/Navbar"

function App() {
  return (
    <div>
      <Navbar />
    </div>
  )
}

export default App
```

---

# 5. JSX Basics

JSX lets us write HTML-like syntax inside JavaScript.

Example:

```jsx
const title = "Welcome to Algeria Trips"

function Hero() {
  return <h1>{title}</h1>
}
```

Rules:

- return one parent element
- use className instead of class
- close all tags (`<img />`, `<input />`)

---

# 6. Props (Passing Data)

Props allow passing data from parent to child component.

Example:

```jsx
function TripCard(props) {
  return <h3>{props.title}</h3>
}

function App() {
  return <TripCard title="Sahara Adventure" />
}
```

---

# 7. State with useState

State stores dynamic data in a component.

Example:

```jsx
import { useState } from "react"

function Counter() {
  const [count, setCount] = useState(0)

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  )
}
```

---

# 8. Events

React handles user actions with event handlers.

Example:

```jsx
function BookingButton() {
  const handleBooking = () => {
    alert("Booking request sent")
  }

  return <button onClick={handleBooking}>Book Now</button>
}
```

Common events:

- onClick
- onChange
- onSubmit

---

# 9. Rendering Lists

Use map to render arrays.

Example:

```jsx
const trips = ["Sahara", "Oran Coast", "Constantine Tour"]

function TripList() {
  return (
    <ul>
      {trips.map((trip, index) => (
        <li key={index}>{trip}</li>
      ))}
    </ul>
  )
}
```

---

# 10. Conditional Rendering

Show elements based on conditions.

Example:

```jsx
function UserStatus({ isLoggedIn }) {
  return <h2>{isLoggedIn ? "Welcome back" : "Please login"}</h2>
}
```

---

# 11. Forms in React

Example input form:

```jsx
import { useState } from "react"

function SearchForm() {
  const [city, setCity] = useState("")

  const handleSubmit = (e) => {
    e.preventDefault()
    console.log(city)
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        placeholder="Search city"
      />
      <button type="submit">Search</button>
    </form>
  )
}
```

---

# 12. API Calls with useEffect

React can fetch backend data.

Example:

```jsx
import { useEffect, useState } from "react"

function Trips() {
  const [trips, setTrips] = useState([])

  useEffect(() => {
    fetch("http://localhost:3000/trips")
      .then((res) => res.json())
      .then((data) => setTrips(data))
      .catch((err) => console.log(err))
  }, [])

  return (
    <div>
      {trips.map((trip) => (
        <p key={trip._id}>{trip.title}</p>
      ))}
    </div>
  )
}
```

---

# 13. React Router (Basic Navigation)

Install router:

```bash
npm install react-router-dom
```

Basic example:

```jsx
import { BrowserRouter, Routes, Route } from "react-router-dom"

function Home() {
  return <h2>Home Page</h2>
}

function TripsPage() {
  return <h2>Trips Page</h2>
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/trips" element={<TripsPage />} />
      </Routes>
    </BrowserRouter>
  )
}

export default App
```

---

# 14. Why React for our Project

React is used in our Tourism SaaS platform because:

- component based architecture
- reusable UI
- fast development with rich ecosystem
- easy integration with Express APIs
- widely used in MERN applications

---

# Conclusion

React.js helps us build dynamic and reusable frontend interfaces.
It makes it easier to manage components, data, forms, and API integration in our tourism platform.
