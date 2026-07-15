# JS-03: HTTP Requests and API Workflow

> **Topic:** Understanding HTTP Communication, APIs, JSON and the Complete Request-Response Lifecycle
> **Learning Journal:** Daily Learning Journal
> **Prerequisites:** JavaScript Fundamentals, Fetch API Basics

---

# 📌 Learning Objectives

After completing this topic, I should be able to:

- Explain what HTTP is.
- Differentiate between HTTP and API.
- Understand API Endpoints.
- Explain the Request-Response Cycle.
- Understand how JSON is used in communication.
- Explain the complete Fetch workflow.
- Understand how frontend and backend communicate.
- Relate these concepts to real-world React applications.

---

# 🌐 What is HTTP?

HTTP (**HyperText Transfer Protocol**) is a communication protocol that defines the rules for exchanging data between a client and a server.

Think of HTTP as the **language** both the frontend and backend use to communicate.

HTTP defines:

- Request Methods (GET, POST, PUT, PATCH, DELETE)
- Headers
- Request Body
- Response Body
- Status Codes

Without HTTP, browsers and servers would not know how to understand each other.

---

# 💡 Real World Analogy

Imagine ordering food from a restaurant.

**Customer**
→ Frontend (React)

**Waiter**
→ HTTP

**Kitchen**
→ Backend

The waiter follows restaurant rules.

Similarly, HTTP follows communication rules between frontend and backend.

---

# 🏗 Client-Server Architecture

```text
Client (Frontend)

↓

HTTP Request

↓

Server (Backend)

↓

Database

↓

HTTP Response

↓

Client
```

---

# 🤝 What is an API?

API stands for **Application Programming Interface**.

An API is a collection of endpoints that allow applications to communicate with one another.

The frontend never directly talks to the database.

Instead,

```text
Frontend

↓

API

↓

Backend

↓

Database
```

The API acts as an interface exposing services provided by the backend.

---

# 📍 What is an API Endpoint?

An API endpoint is a specific URL that performs a particular task.

Examples

```text
GET     /products

GET     /saved-outfits

POST    /saved-outfits

PATCH   /saved-outfits/15

DELETE  /saved-outfits/15
```

Each endpoint performs a specific operation.

Example

```text
/api/products
```

returns products.

Whereas

```text
/api/saved-outfits
```

returns the user's saved outfits.

---

# 🌍 Complete Request Lifecycle

Suppose a user opens the Products page.

The workflow becomes

```text
User opens page

↓

React Component

↓

fetch("/api/products")

↓

Browser creates HTTP Request

↓

Request sent over Internet

↓

API Endpoint

↓

Backend

↓

Database

↓

JSON Response

↓

Browser receives Response

↓

response.json()

↓

JavaScript Object

↓

React updates UI

↓

Products displayed
```

---

# 📦 Understanding JSON

JSON stands for

**JavaScript Object Notation**

It is a lightweight format used to exchange structured data between systems.

Example

```json
{
    "name":"Laptop",
    "price":50000,
    "stock":120
}
```

Although it looks similar to JavaScript objects, JSON is simply **text**.

---

# JavaScript Object vs JSON

### JavaScript Object

```javascript
const product = {
    name: "Laptop",
    price: 50000
};
```

---

### JSON

```json
{
    "name":"Laptop",
    "price":50000
}
```

| JavaScript Object | JSON |
|-------------------|------|
| Exists inside JavaScript | Data format |
| Can contain functions | Cannot contain functions |
| Used in code | Used for communication |

---

# JSON.stringify()

Before sending JavaScript objects to the server, they must be converted into JSON.

```javascript
const user = {
    username: "kitten"
};

JSON.stringify(user);
```

Result

```json
{
    "username":"kitten"
}
```

**Purpose**

Converts a JavaScript object into a JSON-formatted string for transmission over HTTP.

---

# response.json()

After receiving a response,

```javascript
const response = await fetch(url);

const data = await response.json();
```

`response.json()`:

- Reads the response body
- Parses JSON
- Converts JSON into a JavaScript object
- Returns a Promise

---

# HTTP Request Structure

```text
HTTP Request

Method

URL

Headers

Body (Optional)
```

Example

```http
POST /saved-outfits

Content-Type: application/json

{
    "name":"Royal Blue Saree"
}
```

---

# HTTP Response Structure

```text
Status Code

Headers

Body
```

Example

```http
200 OK

Content-Type: application/json

{
    "message":"Saved Successfully"
}
```

---

# HTTP Methods

| Method | Purpose | Example |
|---------|----------|---------|
| GET | Retrieve Data | Load Products |
| POST | Create Data | Save Outfit |
| PUT | Replace Entire Resource | Replace User Profile |
| PATCH | Update Partial Resource | Edit Outfit Description |
| DELETE | Remove Resource | Delete Outfit |

---

# Request vs Response

## Request

Client → Server

Contains

- URL
- Method
- Headers
- Request Body

---

## Response

Server → Client

Contains

- Status Code
- Headers
- Response Body

---

# Practical Example (Ephemeral Project)

Suppose a user creates a new outfit.

### Step 1

React creates

```javascript
const outfit = {
    name: "Royal Blue Saree",
    occasion: "Wedding"
};
```

---

### Step 2

Convert to JSON

```javascript
JSON.stringify(outfit);
```

---

### Step 3

Fetch sends POST request

```javascript
await fetch("/api/saved-outfits", {
    method: "POST",
    body: JSON.stringify(outfit)
});
```

---

### Step 4

Backend receives

```http
POST /saved-outfits
```

---

### Step 5

Backend stores data inside the database.

---

### Step 6

Backend returns

```json
{
    "message":"Outfit Saved Successfully"
}
```

---

### Step 7

React reads

```javascript
const result = await response.json();
```

---

### Step 8

User sees

```text
✅ Outfit Saved Successfully
```

---

# Complete Communication Diagram

```text
React Frontend

↓

Fetch API

↓

HTTP Request

↓

API Endpoint

↓

Backend

↓

Database

↓

JSON Response

↓

Response Object

↓

response.json()

↓

JavaScript Object

↓

React State Update

↓

UI Re-render
```

---

# 💼 Practical Use in My Ephemeral Project

I will use HTTP and APIs to

- Save generated outfits
- Retrieve saved collections
- Fetch AI-generated recommendations
- Upload user images
- Display fashion suggestions
- Store user preferences

---

# 🎯 Interview Questions

### What is HTTP?

---

### What is an API?

---

### What is an API Endpoint?

---

### Difference between HTTP and API?

---

### Difference between JSON and JavaScript Object?

---

### Why do we use JSON.stringify()?

---

### What does response.json() do?

---

### Explain the complete request-response cycle.

---

# 📝 Key Takeaways

- HTTP is the communication protocol between client and server.
- APIs expose services that clients can access.
- API endpoints perform specific tasks.
- JSON is the standard format for exchanging structured data.
- JSON.stringify() converts JavaScript objects into JSON strings.
- response.json() converts JSON responses into JavaScript objects.
- Fetch API uses HTTP to communicate with backend APIs.
- React displays data after parsing the server response.

---

# ✅ Revision Checklist

- [ ] I can explain HTTP.
- [ ] I know the role of APIs.
- [ ] I understand API Endpoints.
- [ ] I understand Request and Response.
- [ ] I understand JSON.
- [ ] I know the difference between JSON and JavaScript Objects.
- [ ] I know when to use JSON.stringify().
- [ ] I know what response.json() does.
- [ ] I can explain the complete communication workflow.

---

# 📚 Next Topic

➡ **JS-05: Fetch Request Methods, Request Body & Headers**
