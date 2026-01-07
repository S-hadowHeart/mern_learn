## Try and Catch (Exception Handling in JavaScript)

---

### What is Exception Handling?

* Exception handling is a way to **handle errors** that occur while a program is running.
* JavaScript uses **`try`, `catch`, and `finally`** to handle errors safely.
* It prevents the program from **crashing** when an error occurs.

---

## Types of Errors in JavaScript

### Syntax Errors

* Errors due to **wrong syntax**
* Code will **not run at all**
* **Cannot be handled** using try–catch

```js
if (true {
  console.log("error");
}
```

---

### Runtime Errors

* Errors that occur **during execution**
* **Can be handled** using try–catch

```js
console.log(a); // a is not defined
```

---

## Important Rule

👉 **Only runtime errors can be handled using try–catch**

---

## `try` Statement

* Contains **risky code**
* JavaScript checks this block for errors
* If an error occurs → control moves to `catch`

```js
try {
  // code to test
}
```

---

## `catch` Statement

* Executes **only if an error occurs in try**
* Receives the error object

```js
catch (err) {
  // error handling code
}
```

---

## Basic Syntax

```js
try {
  // risky code
} catch (err) {
  // error handling
}
```

---

## try–catch–finally

* `finally` runs **always**
* Runs whether error occurs or not
* Used for cleanup tasks

```js
try {
  // code
} catch (err) {
  // handle error
} finally {
  // always runs
}
```

---

## Example 1: Handling Runtime Error

```js
try {
  let x = undefined;
  console.log(x[0]);
} catch (err) {
  console.log("Error handled:", err);
} finally {
  console.log("Finally always gets executed");
}

console.log("End");
```

### Output:

```
Error handled: TypeError
Finally always gets executed
End
```

---

## Example 2: Variable Not Defined

```js
try {
  console.log("hello");
  console.log(a); // error
  console.log("ending try");
} catch (err) {
  console.log("Handled:", err);
} finally {
  console.log("finally");
}
```

### Output:

```
hello
Handled: ReferenceError
finally
```

---

## Key Points to Remember 

* `try` must always be followed by `catch` or `finally`
* `catch` runs **only if error occurs**
* `finally` runs **always**
* Syntax errors cannot be caught
* Runtime errors can be caught

---

## When to Use Try–Catch?

* Accessing variables that may not exist
* Working with APIs
* Parsing JSON
* DOM manipulation
* Async operations

---

## Summary 

* `try` → test risky code
* `catch` → handle error
* `finally` → cleanup code
* Prevents app crashes
* Improves stability & debugging

---
