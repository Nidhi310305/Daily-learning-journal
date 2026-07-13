# JS-02: Fetch API Basics

> **Topic:** JavaScript Fetch API Fundamentals  
> **Learning Journal:** Daily Learning Journal  
> **Prerequisites:** JavaScript Basics, Promises, async/await

---

# 📌 Learning Objectives

After completing this topic, I should be able to:

- Explain what Fetch API is.
- Understand why Fetch replaced XMLHttpRequest.
- Explain Request and Response objects.
- Understand Promises and async/await.
- Explain how a request travels from the frontend to the backend.
- Understand Response Objects.
- Parse JSON responses using `response.json()`.
- Explain Promise resolution vs rejection.
- Understand Deferred Fetch.

---

# 🌐 What is Fetch API?

The **Fetch API** is a browser-provided JavaScript interface used to make **HTTP requests** and process **HTTP responses**.

It enables JavaScript applications to communicate with servers and retrieve or send resources across a network.

Resources may include:

- JSON data
- Images
- Files
- Text
- API responses

In simple words,

> **Fetch API allows the frontend to communicate with servers over HTTP.**

---

# ❓ Why was Fetch API introduced?

Before Fetch API, developers used **XMLHttpRequest (XHR)**.

Although XHR worked correctly, it had several disadvantages.

## Problems with XMLHttpRequest

- Verbose syntax
- Callback-based programming
- Hard to read
- Difficult error handling
- More manual configuration

Fetch API solves these issues by providing

- Cleaner syntax
- Promise-based programming
- Better readability
- Easy integration with async/await

---

# 📖 Basic Syntax

```javascript
const response = await fetch(url);
```

The `fetch()` function accepts two arguments.

```javascript
fetch(url, options);
```

| Parameter | Description |
|-----------|-------------|
| url | Resource to fetch (Required) |
| options | HTTP method, headers, body etc. (Optional) |

---

# 🔄 How Fetch Works

```text
fetch()

↓

Browser creates HTTP Request

↓

Request travels through the Internet

↓

Server receives Request

↓

Server processes Request

↓

Server sends HTTP Response

↓

Browser receives Response Object

↓

response.json()

↓

JavaScript Object

↓

Display Data on UI
```

---

# 📨 Request Object

The Request Object contains information sent **from the client to the server.**

It includes:

- URL
- HTTP Method
- Headers
- Request Body (optional)

Example

```javascript
fetch("/products", {
    method: "GET"
});
```

---

# 📩 Response Object

After the server responds,

```javascript
const response = await fetch(url);
```

`response` becomes a **Response Object**.

It contains

- Status Code
- Headers
- Body

**Important**

The Response Object **does not directly contain the actual data.**

---

# 🤝 Understanding Promises

Calling

```javascript
fetch(url);
```

does **NOT** return the actual data immediately.

Instead, it immediately returns a **Promise**.

A Promise represents a value that will become available in the future.

```text
fetch()

↓

Promise

↓

Response Object
```

---

# ✅ Promise Resolution vs Rejection

One of the most important Fetch concepts.

### Promise Resolves

The Promise resolves whenever the server sends an HTTP response.

Examples

✅ 200 OK

✅ 201 Created

✅ 404 Not Found

✅ 500 Internal Server Error

Even though 404 and 500 are errors, they are still valid HTTP responses.

---

### Promise Rejects

The Promise rejects only when **no HTTP response is received.**

Examples

- No Internet
- DNS failure
- Network timeout
- Connection failure

---

# ⏳ async and await

Since `fetch()` returns a Promise, we usually use `await`.

```javascript
const response = await fetch(url);
```

`await` pauses **only the current asynchronous function** until the Promise settles.

The rest of the application continues running.

---

# 📦 Response Object

The Response Object contains metadata returned by the server.

It includes

- Status
- Headers
- Body

Example

```javascript
const response = await fetch(url);

console.log(response.status);
console.log(response.headers);
```

---

# 📄 response.json()

Most APIs return data in JSON format.

To convert JSON into a JavaScript object,

```javascript
const data = await response.json();
```

### What does response.json() do?

It

- Reads the response body
- Parses JSON
- Converts JSON into a JavaScript object
- Returns another Promise

Example

Server sends

```json
{
    "name":"Laptop",
    "price":50000
}
```

After

```javascript
const data = await response.json();
```

JavaScript receives

```javascript
{
    name: "Laptop",
    price: 50000
}
```

Now the data can be used inside React.

---

# 📊 HTTP Status Codes

| Status Code | Meaning |
|-------------|----------|
| 200 | Request Successful |
| 201 | Resource Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Resource Not Found |
| 500 | Internal Server Error |

---

# 🕒 Deferred Fetch

Deferred Fetch allows the browser to schedule a request to be sent later.

Instead of sending immediately,

the browser can send it

- after some delay
- when the page closes
- when the user navigates away

### Use Cases

- Analytics
- User activity tracking
- Saving session statistics

---

# 🍕 Pizza Analogy (Memory Trick)

Imagine ordering a pizza.

```text
Order Pizza

↓

fetch()

↓

Restaurant says

"We've received your order."

↓

Promise

↓

Pizza arrives

↓

Response Object

↓

Open Pizza Box

↓

response.json()

↓

Eat Pizza (Use Data)
```

---

# 🧠 Complete Mental Model

```text
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

React UI
```

---

# 💼 Practical Use in My Ephemeral Project

I will use Fetch API to

- Retrieve AI-generated images
- Save generated outfits
- Fetch saved collections
- Communicate with backend APIs
- Display generated recommendations
- Store user preferences

---

# 🎯 Interview Questions

### 1. What is Fetch API?

---

### 2. Why did Fetch replace XMLHttpRequest?

---

### 3. What is the difference between Promise and Response Object?

---

### 4. When does a Promise resolve?

---

### 5. When does a Promise reject?

---

### 6. Why is response.json() required?

---

### 7. Explain the complete Fetch lifecycle.

---

# 📝 Key Takeaways

- Fetch API is the modern interface for making HTTP requests.
- It replaces XMLHttpRequest with a Promise-based approach.
- `fetch()` immediately returns a Promise.
- Promises resolve whenever an HTTP response is received.
- Promises reject only on network failures.
- Response Objects contain metadata.
- `response.json()` converts JSON into JavaScript objects.
- async/await makes asynchronous code easier to read.
- Fetch API is one of the core technologies used in React applications.

---

# ✅ Revision Checklist

- [ ] I can explain Fetch API.
- [ ] I know why Fetch replaced XMLHttpRequest.
- [ ] I understand Request and Response Objects.
- [ ] I understand Promises.
- [ ] I understand async/await.
- [ ] I understand response.json().
- [ ] I understand Promise resolve vs reject.
- [ ] I can explain the complete Fetch workflow.
- [ ] I know where I will use Fetch API in my Ephemeral project.

---

# 📚 Next Topic

➡ **JS-04: HTTP Requests, APIs, JSON & Fetch Workflow**
