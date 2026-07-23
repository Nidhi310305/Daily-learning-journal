# JS-05: Modern JavaScript (ES6+)

## 📖 Overview

Modern JavaScript (ES6 and later) introduced several features that make code cleaner, more readable, and easier to maintain. These features are widely used in React and modern web development.

---

## 📚 Topics Covered

### Variables

- `let`
- `const`
- Difference between `var`, `let`, and `const`

---

### Arrow Functions

Traditional Function

```javascript
function greet(name) {
    return `Hello ${name}`;
}
```

Arrow Function

```javascript
const greet = (name) => {
    return `Hello ${name}`;
};
```

Single-line Arrow Function

```javascript
const square = num => num * num;
```

---

### Template Literals

Instead of string concatenation:

```javascript
const name = "Nidhi";
const message = `Hello ${name}`;
```

---

### Destructuring

Objects

```javascript
const user = {
    name: "Nidhi",
    age: 21
};

const { name, age } = user;
```

Arrays

```javascript
const colors = ["Red", "Blue", "Green"];

const [first, second] = colors;
```

---

### Spread Operator

Arrays

```javascript
const arr1 = [1,2,3];
const arr2 = [...arr1,4,5];
```

Objects

```javascript
const user = {
    name:"Nidhi"
};

const updatedUser = {
    ...user,
    age:21
};
```

---

### Rest Parameters

```javascript
function sum(...numbers){
    return numbers.reduce((a,b)=>a+b);
}
```

---

### Default Parameters

```javascript
function greet(name="Guest"){
    return `Hello ${name}`;
}
```

---

### Modules

Export

```javascript
export default greet;
```

Import

```javascript
import greet from "./greet";
```

---

## 💡 Why ES6 Matters

These features:

- Reduce repetitive code
- Improve readability
- Make React components easier to write
- Encourage cleaner programming practices

---

## 🚀 Real-world Applications

- React Components
- API Integration
- State Management
- Object Manipulation
- Modern Web Development

---

## 📝 Key Learnings

- Used `let` and `const` appropriately.
- Learned concise arrow functions.
- Simplified string formatting using template literals.
- Extracted object and array values using destructuring.
- Copied and merged data using the spread operator.
- Used rest parameters for flexible functions.
- Understood default parameters.
- Learned the basics of JavaScript modules.

---

## 📌 Interview Questions

### Q1. Difference between `let`, `const`, and `var`?

- `var` is function-scoped.
- `let` is block-scoped and can be reassigned.
- `const` is block-scoped and cannot be reassigned.

---

### Q2. What is an arrow function?

A shorter syntax for writing functions. It also handles `this` differently from regular functions.

---

### Q3. What is destructuring?

A convenient way to extract values from objects and arrays into variables.

---

### Q4. What is the spread operator?

It copies or expands elements of arrays or properties of objects.

---

## ✅ Progress

- [x] let & const
- [x] Arrow Functions
- [x] Template Literals
- [x] Destructuring
- [x] Spread Operator
- [x] Rest Parameters
- [x] Default Parameters
- [x] Modules

---

**Next Topic:** JS-06-React-Fundamentals.md
