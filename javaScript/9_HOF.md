# Higher Order Functions (HOF)

---

## What is a Higher Order Function?

- A **Higher Order Function** is a function that:
  - **Takes another function as an argument**, OR
  - **Returns a function**
- This concept is possible because **functions are first-class citizens** in JavaScript.

---

## First-Class vs Higher-Order Functions

### First-Class Functions
- Functions that are treated like normal values
- Can be:
  - Stored in variables
  - Passed as arguments
  - Returned from other functions

👉 If a function **does NOT take or return another function**, it is just a **first-class function**

---

### Higher Order Functions
- Functions that **operate on other functions**

---

## Example 1: Passing a Function as an Argument

```js
const powerTwo = (n) => {
  return n ** 2;
};

function powerCube(powerTwo, n) {
  return powerTwo(n) * n;
}

console.log(powerCube(powerTwo, 3));
````

**Output:**

```
27
```

* `powerCube` is a **higher-order function**
* `powerTwo` is passed as an argument

---

## Example 2: Returning a Function

```js
function sayHello() {
  return () => {
    console.log("Hello World");
  };
}

let guessValue = sayHello();
guessValue();
```

**Output:**

```
Hello World
```

* `sayHello` returns a function
* This makes it a **higher-order function**

---

## Example 3: Function Returning Function Returning Function

```js
const higherOrder = n => {
  const oneFun = m => {
    const twoFun = p => {
      return m + n + p;
    };
    return twoFun;
  };
  return oneFun;
};

console.log(higherOrder(2)(3)(4));
```

**Output:**

```
9
```

* This is called **function currying**
* Each function remembers previous values (**closure**)

---

## Higher Order Functions with Arrays

### Example: Summing Array Elements

```js
const myNums = [2, 3, 4, 5];

const sumArray = arr => {
  let total = 0;
  arr.forEach(function (element) {
    total += element;
  });
  return total;
};

console.log(sumArray(myNums));
```

**Output:**

```
14
```

* `forEach()` is a **higher-order function**
* It takes a function as an argument

---

## Built-in Higher Order Functions

Common array HOFs:

* `map()`
* `filter()`
* `reduce()`
* `forEach()`
* `find()`
* `some()`
* `every()`

---

## Higher Order Functions with Timers

### `setInterval()`

```js
function oneMoreHello() {
  console.log("Hello World!", Math.random());
}

setInterval(oneMoreHello, 1000);
```

* Executes function **every 1 second**
* `setInterval` is a **higher-order function**

---

### `setTimeout()`

```js
setTimeout(oneMoreHello, 2000);
```

* Executes function **once after 2 seconds**
* Also a **higher-order function**

---

## Why Use Higher Order Functions?

* Cleaner and shorter code
* Better abstraction
* Reusability of logic
* Functional programming style
* Easier debugging and maintenance

---

## Real-World Examples

* Event listeners
* Array methods
* Callbacks
* Promises
* Async / Await
* React hooks

---

