## Closures in JavaScript

### What is a Closure?

A **closure** is the combination of a function bundled together with references to its **lexical environment** (surrounding scope).

In simple words:

* A closure allows an inner function to **access variables of its outer function**, even after the outer function has finished executing.
* Closures are created **every time a function is created**, at function creation time.

---

## Scope Basics (Before Closures)

### Example 1: Local Scope

```js
function one() {
  let score = 0;
  console.log(score);
}

one();
console.log(score);
```

**Output:**

```
0
ReferenceError: score is not defined
```

Explanation: `score` is local to `one()` and cannot be accessed outside.

---

### Example 2: Global vs Local Scope

```js
let score = 4;
function one() {
  let score = 0;
  console.log(score);
}

one();
console.log(score);
```

**Output:**

```
0
4
```

Local variables shadow global variables.

---

### Example 3: Multiple Functions with Same Variable Name

```js
let score = 4;
function one() {
  let score = 0;
  console.log(score);
}
function two() {
  let score = 3;
  console.log(score);
}

one();
two();
console.log(score);
```

**Output:**

```
0
3
4
```

Each function has its own scope.

---

### Example 4: Function Accessing Global Variable

```js
let score = 4;
function three() {
  console.log(score);
}

three();
```

**Output:**

```
4
```

Functions can access variables from outer (global) scope.

---

## Lexical Scope

### Example: Inner Function Accessing Outer Variable

```js
function outerFunc() {
  let outerVar = "I am at scope level 1";

  function innerFunc() {
    console.log(outerVar);
  }

  innerFunc();
}

outerFunc();
```

**Output:**

```
I am at scope level 1
```

Inner functions can access outer variables.

---

### Inner Scope Is Not Accessible Outside

```js
function outerFunc() {
  let outerVar = "I am at scope level 1";

  function innerFunc() {
    let innerVar = "I am at scope level 2";
    console.log(outerVar);
  }

  console.log(innerVar);
  innerFunc();
}

outerFunc();
```

**Output:**

```
ReferenceError: innerVar is not defined
```

Explanation:

* Outer → Inner access is allowed
* Inner → Outer access is NOT allowed

Real-life analogy:

* A child can take ice cream from an adult
* An adult cannot take ice cream from a child

This behavior is called **lexical scoping**.

---

## Deep Lexical Scope Example

```js
const myGlobalValue = 0;

function func() {
  const val1 = 1;
  console.log(myGlobalValue);

  function innerOfFunc() {
    const val2 = 2;
    console.log(val2, val1, myGlobalValue);

    function innerOfInnerFunc() {
      const val3 = 3;
      console.log(val3, val2, val1, myGlobalValue);
    }

    innerOfInnerFunc();
  }

  innerOfFunc();
}

func();
```

**Output:**

```
0
2 1 0
3 2 1 0
```

Each inner function has access to all outer scopes.

---

## Closures (Main Concept)

### Basic Closure Example

```js
function superFunc() {
  let outerValue = "I am outer";

  function minorFunction() {
    console.log(outerValue);
  }

  minorFunction();
}

superFunc();
```

**Output:**

```
I am outer
```

The inner function remembers `outerValue`. This memory is called a **closure**.

---

### Closure with setTimeout (Real-Life Example)

```js
const errorMessage = "File not found";

setTimeout(function callback() {
  console.log(errorMessage);
}, 1000);
```

Even after the outer code finishes, the callback still remembers `errorMessage`.

---

### Closure in Loops

```js
let pageCount = 0;
const items = [2, 4, 5, 7, 8];

items.forEach(function iterator(num) {
  pageCount++;
  console.log(num);
});

console.log("Page Count:", pageCount);
```

**Output:**

```
2
4
5
7
8
Page Count: 5
```

The callback function forms a closure over `pageCount`.

---

## Key Takeaways

* Closures allow functions to remember outer variables
* Lexical scope defines how variable access works
* Closures are created at function creation time
* Common use cases:

  * Callbacks
  * setTimeout / setInterval
  * Data hiding
  * Function factories

Closures are one of the most powerful features of JavaScript.
