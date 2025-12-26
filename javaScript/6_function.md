# Functions in JavaScript

---

## What is a Function?

- A **function** is a block of code that performs a **specific task**.
- Functions help us **organize**, **structure**, and **reuse** code.
- Instead of writing the same logic again and again, we write it **once** and reuse it.
- Functions make code:
  - More efficient
  - Modular
  - Readable
  - Easy to update and maintain

---

## Types of Functions in JavaScript

- **Built-in functions**  
  Example: `console.log()`, `alert()`, `parseInt()`
- **User-defined functions**  
  Functions created by developers

---

## Functions as First-Class Citizens

In JavaScript, functions are **first-class citizens**, which means:

- Functions can be stored in variables
- Functions can be passed as arguments to other functions
- Functions can be returned from other functions

---

## Advantages of Using Functions

- **Code Reusability**  
  Write once, use many times
- **Avoid Code Duplication**
- **Problem Decomposition**  
  Break large problems into smaller tasks
- **Better Readability**
- **Easy Testing & Debugging**  
  Functions can be tested independently
- **Better Performance & Memory Management**

---

## When Should You Use Functions?

- When a task needs to be performed **multiple times**
- To organize code into **logical units**
- To improve **readability and maintainability**
- To handle **asynchronous tasks**  
  (HTTP requests, timers, events, etc.)

---

## Function Declaration – Basic Syntax

```
function functionName() {
  // function body
}
```

### Parts:

* `function` keyword
* Function name
* Parentheses `()`
* Function body `{ }`

---

## Calling a Function

* Calling a function means **executing** it
* Use function name followed by `()`

```js
function greet() {
  console.log("Hi there");
  console.log("How are you?");
}

greet();
```

**Output:**

```
Hi there
How are you?
```

---

## Function with Parameters & Arguments

* **Parameter** → Variable in function definition
* **Argument** → Actual value passed during function call

```js
function sqr(x) {   // x is parameter
  console.log(x * x);
}

sqr(8);            // 8 is argument
```

**Output:**

```
64
```

---

## Return Statement

```js
function sqx(x) {
  return x * x;
}

let a = sqx(8);
console.log(a);
```

**Output:**

```
64
```

### Important Notes:

* `return` sends a value back to the caller
* Writing only `return;` → returns `undefined`
* No return statement → also returns `undefined`
* Code after `return` is **not executed**

---

## Function Without Parameters & Return

* Parameters and return are **optional**
* Used when we only want to perform an action

```js
function sayHello() {
  console.log("Hello World");
}

sayHello();
```

---

## Function Returning a Value

* Functions may return values **with or without parameters**

```js
function getRandom() {
  return Math.random();
}
```

---

## Function with One Parameter

```js
function displayMsg(msgToBeDisplayed) {
  console.log(msgToBeDisplayed);
}

displayMsg("Helloooooooooo");
displayMsg("Hiiiii");
```

---

## Default Parameters

* Default values are used when no argument is passed

```js
function displayMsg(msg = "I am human ig") {
  console.log(msg);
}

displayMsg("hohoho");
displayMsg();
```

**Output:**

```
hohoho
I am human ig
```

---

### Default Parameters – Left to Right Rule

```js
function add(x, y = 2) {
  console.log(x + y);
}

add(1, 3);
add(1);
```

**Output:**

```
4
3
```

❌ Incorrect usage:

```js
function add(x = 2, y) {
  console.log(x + y);
}

add(1, 3); // works
add(1);    // y is undefined → NaN
```

---

## Function with Two Parameters

```js
function multiply(a, b) {
  return a * b;
}

multiply(2, 5);
```

---

## Array as an Argument

```js
function add([num1, num2]) {
  return num1 + num2;
}

let num = [10, 40];
let res = add(num);
console.log(res);
```

**Output:**

```
50
```

---

## Function with Unlimited Parameters

### Using `arguments` object

```js
function add() {
  let sum = 0;
  for (let i = 0; i < arguments.length; i++) {
    sum += arguments[i];
  }
  return sum;
}

let result = add(1, 2, 3, 4, 5);
console.log(result);
```

**Output:**

```
15
```

---

## Arrow Functions

* Introduced in **ES6 (2015)**
* Shorter syntax for function expressions
* Also called **fat arrow functions**

### Syntax Examples

```js
// 1. Single parameter, single return
const square = x => x * x;

// 2. Multiple parameters
const add = (x, y) => x + y;

// 3. Multiple statements
const sum = (x, y) => {
  console.log(`Adding ${x} and ${y}`);
  return x + y;
};

// 4. Returning an object
const sumAndDifference = (x, y) => ({
  sum: x + y,
  difference: x - y
});
```

```js
let output1 = square(5);
console.log(output1);
```

**Output:**

```
25
```

---

## Arrow Function Rules

* Parentheses optional for **single parameter**
* Parentheses required for **multiple parameters**
* No `return` needed for single expression
* `return` required for multiple statements
* Object return must be wrapped in `()`

---

## Why Use Arrow Functions?

* Very concise syntax
* Cleaner and more readable code
* Automatic return for expressions
* No own `this` binding
* Perfect for:

  * `map()`
  * `filter()`
  * `reduce()`

---

## Anonymous Functions

* Functions **without a name**
* Usually assigned to variables
* Arrow functions are anonymous by default

```js
let x = function () {
  console.log("hi");
};

x();
```

**Output:**

```
hi
```

---

## IIFE (Immediately Invoked Function Expression)

* Function that runs **immediately after creation**
* IIFE is called self-invoking function

```js
(function execute() {
  console.log("named");
})();
```

**Output:**

```
named
```

---

## Key Takeaways

* Functions improve code structure
* JavaScript functions are first-class citizens
* Parameters & return are optional
* Arrow functions are modern & concise
* Anonymous & IIFE functions are widely used

