# JS-04: HTTP Requests and API Workflow

## 📅 Date
2026-07-18

---

# 🎯 Learning Objectives

- Understand what HTTP is.
- Learn the client-server architecture.
- Understand APIs and API Endpoints.
- Learn how HTTP requests and responses work.
- Understand JSON and why it is used.
- Learn `JSON.stringify()` and `response.json()`.
- Understand Request Body and Response Body.
- Connect the complete workflow to real-world React applications.

---

# 🌐 What is HTTP?

**HTTP (HyperText Transfer Protocol)** is a communication protocol that defines the rules for exchanging information between a client and a server.

Think of HTTP as the **language** that both the client and server understand.

### Restaurant Analogy 🍽️

```
Customer (Frontend)

      │
      │ "I'd like a Pizza"
      ▼

Waiter (HTTP)

      │
      ▼

Kitchen (Backend)

      │
      ▼

Pizza (Response)
```

The waiter doesn't cook the food.

The waiter simply carries messages between the customer and the kitchen.

HTTP works exactly the same way.

---

# Client vs Server

## Client

The client is the application requesting data.

Examples:

- React App
- Browser
- Mobile App

## Server

The server processes requests and sends responses.

It usually communicates with:

- Database
- Authentication
- Business Logic
- AI Models

---

# What is an API?

API stands for

**Application Programming Interface**

An API is a bridge that allows two software applications to communicate.

The frontend never directly talks to the database.

Instead,

```
Frontend

↓

API

↓

Backend

↓

Database
```

---

# API Endpoint

An endpoint is a specific URL where an API provides a service.

Examples

```
GET /users

GET /products

POST /login

POST /generate-image

GET /saved-outfits
```

Each endpoint performs a different task.

---

# HTTP Request

A Request is information sent from the client to the server.

A request contains:

- URL
- HTTP Method
- Headers
- Request Body (optional)

Example

```
POST /generate-image
```

Request Body

```json
{
    "prompt": "Elegant royal blue saree with silver embroidery"
}
```

---

# HTTP Response

A Response is what the server sends back.

It contains:

- Status Code
- Headers
- Response Body

Example

```json
{
    "image": "generated-image-url"
}
```

---

# Request Body

The Request Body contains data sent to the server.

Usually used with

- POST
- PUT
- PATCH

Example

```javascript
fetch("/api", {
    method: "POST",
    body: JSON.stringify(data)
});
```

---

# Response Body

The Response Body contains data returned from the server.

Example

```json
{
    "username":"Nidhi",
    "theme":"dark"
}
```

---

# JSON

JSON stands for

**JavaScript Object Notation**

It is the most common format used to exchange data over HTTP.

Example

```json
{
    "name":"Nidhi",
    "age":20
}
```

---

# JSON.stringify()

`JSON.stringify()` converts a JavaScript object into a JSON string.

Example

```javascript
const user = {
    name:"Nidhi",
    age:20
};

const json = JSON.stringify(user);
```

Output

```text
'{"name":"Nidhi","age":20}'
```

Why?

HTTP cannot directly send JavaScript objects.

They must first become strings.

---

# response.json()

`response.json()` does two things:

1. Reads the response body.
2. Parses JSON into a JavaScript object.

Example

```javascript
const response = await fetch(url);

const data = await response.json();
```

After parsing,

```javascript
console.log(data.name);
```

works normally.

---

# Complete API Workflow

```
React Component

↓

fetch()

↓

HTTP Request

↓

API Endpoint

↓

Backend

↓

Database / AI Model

↓

JSON Response

↓

Response Object

↓

response.json()

↓

JavaScript Object

↓

React UI Updates
```

---

# HTTP Methods

## GET

Retrieve data.

Example

```
GET /products
```

---

## POST

Create new data.

Example

```
POST /generate-image
```

---

## PUT

Replace an entire resource.

Example

```
PUT /profile
```

---

## PATCH

Update part of an existing resource.

Example

```
PATCH /profile
```

---

## DELETE

Remove data.

Example

```
DELETE /saved-outfit/23
```

---

# Fetch API vs HTTP vs API

Many beginners confuse these terms.

| Concept | Purpose |
|----------|----------|
| Fetch API | JavaScript interface used to send requests |
| HTTP | Communication protocol |
| API | Service provided by backend |
| Endpoint | Specific API URL |
| JSON | Data exchange format |

---

# Visual Difference

```
React

↓

Fetch API

↓

HTTP

↓

API Endpoint

↓

Backend

↓

Database
```

---

# Ephemeral Project Example

User enters:

> "Create a royal blue silk saree with silver embroidery."

React creates

```javascript
const prompt = {
    outfit: "...description..."
};
```

↓

`JSON.stringify(prompt)`

↓

HTTP POST Request

↓

`/generate-image`

↓

Backend

↓

LLM enhances prompt

↓

Image Generation Model

↓

Generated Image

↓

JSON Response

↓

`response.json()`

↓

React displays generated outfit.

---

# Interview Questions

## Q1. What is HTTP?

HTTP is a communication protocol that defines the rules for communication between clients and servers.

---

## Q2. What is an API?

An API is an interface that enables different software applications to communicate.

---

## Q3. What is an API Endpoint?

A specific URL that provides a particular API service.

---

## Q4. Why is JSON used?

Because JSON is lightweight, human-readable, and supported by almost every programming language.

---

## Q5. What does `JSON.stringify()` do?

Converts a JavaScript object into a JSON-formatted string.

---

## Q6. What does `response.json()` do?

Reads the response body, parses the JSON, and returns a Promise that resolves to a JavaScript object.

---

## Q7. Difference between Request Body and Response Body?

**Request Body** contains data sent **to** the server.

**Response Body** contains data returned **from** the server.

---

# Key Takeaways

- HTTP defines the communication rules.
- APIs expose services to clients.
- Endpoints are specific API URLs.
- Fetch API sends HTTP requests.
- JSON is the standard data exchange format.
- `JSON.stringify()` converts objects into strings.
- `response.json()` converts JSON strings back into JavaScript objects.
- Understanding the complete request-response lifecycle is essential for modern frontend development.

---

# Revision Checklist

- [ ] I know what HTTP is.
- [ ] I understand Client vs Server.
- [ ] I know what an API is.
- [ ] I understand API Endpoints.
- [ ] I know how Requests and Responses work.
- [ ] I understand Request Body and Response Body.
- [ ] I know why JSON is used.
- [ ] I can explain `JSON.stringify()`.
- [ ] I can explain `response.json()`.
- [ ] I can explain the complete API workflow from React to Backend and back.
