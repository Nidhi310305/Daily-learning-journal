# 2026-07-03 — JavaScript Fundamentals (Day 1)

**Domain:** Web Development

**Topic:** JavaScript Fundamentals

**Tools:** JavaScript (ES6+), React (Conceptual Integration)

**Type:** Conceptual Learning with Practical Examples

---

## Learning Objectives

* Understand the basic structure of JavaScript programs.
* Learn how variables and primitive data types are used.
* Explore arithmetic and comparison operators.
* Build a foundation for React development.

---

## Topics Studied

* Code Structure
* Variables (`let` and `const`)
* Primitive & Reference Data Types
* Basic Operators
* Comparison Operators
* JavaScript in React Applications

---

## Key Concepts

### Code Structure

A JavaScript program consists of executable statements. Although Automatic Semicolon Insertion (ASI) exists, explicitly using semicolons improves readability and consistency.

### Variables

Variables provide named storage for application data.

* `let` is used when values may change.
* `const` is used for values that remain constant after initialization.

### Data Types

Reviewed the primary JavaScript data types:

* Number
* String
* Boolean
* Array
* Object
* `null`
* `undefined`

Special attention was given to the distinction between `null` (intentional absence of a value) and `undefined` (value not yet assigned).

### Operators

Studied arithmetic, assignment, increment/decrement, compound assignment, and comparison operators.

Emphasis was placed on using strict equality (`===`) instead of loose equality (`==`) to avoid unintended type coercion.

---

## Practical Work

* Practiced variable declaration using `let` and `const`.
* Created examples using different JavaScript data types.
* Implemented arithmetic and compound assignment operations.
* Compared values using relational and equality operators.
* Connected JavaScript comparison logic with conditional rendering in React.

---

## React Connection

Explored how JavaScript concepts directly support React development.

Example:

```jsx
{imageCount > 0 && <GenerateButton />}
```

This reinforced how conditional expressions determine component rendering within a React application.

---

## Challenges

* Understanding JavaScript's automatic type coercion.
* Differentiating between `==` and `===`.
* Distinguishing the use cases of `null` and `undefined`.

---

## Quick Revision Notes

* JavaScript executes statements sequentially.
* Use `const` by default; use `let` when reassignment is required.
* Prefer `===` over `==`.
* `null` represents an intentional empty value.
* `undefined` indicates that no value has been assigned.
* JavaScript expressions drive conditional rendering in React.

---

## Resources

### Related Project

* Ephemeral (React + Vite)

### Key Technologies

* JavaScript (ES6+)
* React
* Vite

---

## Next Steps

* Functions
* Return Statements
* Arrow Functions
* Import & Export
* Objects and Arrays
* Build the first React component (`Navbar.jsx`)

---

## Reflection

This session established the JavaScript fundamentals required for React development. Beyond learning syntax, the focus was on understanding how variables, operators, and comparisons influence application logic and user interface rendering. These concepts provide the foundation for building interactive React components and progressing toward the Ephemeral project.
