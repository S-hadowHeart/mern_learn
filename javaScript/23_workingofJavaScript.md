## JavaScript Execution Process

JavaScript code is executed using **Execution Contexts**.

### What is an Execution Context?

An execution context is an environment where JavaScript code is **evaluated and executed**.

Every execution context has **two phases**:

1. **Memory Creation Phase**
2. **Execution Phase**

---

## Types of Execution Context

1. **Global Execution Context (GEC)**
2. **Function Execution Context (FEC)**

---

## Example Code

```js
var a = 10;
var b = 20;

function sum() {
  var c = a + b;
  return c;
}

var c = sum();
```

---

## Step 1: Global Execution Context (GEC)

When the program starts, JavaScript creates the **Global Execution Context**.

### GEC has two parts:

* **Memory Phase**
* **Execution Phase**

---

### Memory Creation Phase (Hoisting)

JavaScript scans the entire program first and allocates memory.

| Variable / Function | Value               |
| ------------------- | ------------------- |
| a                   | undefined           |
| b                   | undefined           |
| sum                 | function definition |
| c                   | undefined           |

(No code is executed yet)

---

### Execution Phase

Now JavaScript executes code line by line.

```js
a = 10
b = 20
```

* `a` → 10
* `b` → 20

```js
c = sum()
```

* Function `sum()` is called
* A **new Function Execution Context** is created

---

## Step 2: Function Execution Context (FEC)

For `sum()` function:

### Memory Phase (inside function)

| Variable | Value     |
| -------- | --------- |
| c        | undefined |

---

### Execution Phase (inside function)

```js
c = a + b; // 10 + 20 = 30
return c;
```

* Function returns `30`
* Function Execution Context is **removed from Call Stack**

---

## Back to Global Context

```js
var c = sum();
```

* `c` gets value `30`
* Program finishes execution

---

## Call Stack

* Call Stack manages execution contexts
* **LIFO (Last In, First Out)**

### Call Stack Flow:

1. Global Execution Context pushed
2. `sum()` context pushed
3. `sum()` finishes → popped
4. Global context finishes → popped

---

## JavaScript is Single-Threaded

* Executes **one statement at a time**
* Cannot execute two lines simultaneously
* Uses **Event Loop + Web APIs** for async behavior

---

## Scopes in JavaScript

### 1. Global Scope

* Variables declared outside functions
* Accessible everywhere

```js
var x = 10;
```

---

### 2. Local Scope (Function Scope)

* Variables declared inside functions
* Accessible only inside that function

```js
function test() {
  var a = 10;
}
```

---

### 3. Lexical Scope

* Inner functions can access variables of outer functions
* Outer functions **cannot** access inner variables

```js
function outer() {
  let x = 10;

  function inner() {
    console.log(x);
  }

  inner();
}
```

---

## Working of JavaScript Functions (Example)

```js
var vari1 = 1;

one();
two();
console.log(vari1);

function one() {
  var a = 10;
  console.log(a);
}

function two() {
  var b = 20;
  console.log(b);
}
```

### Output

```
10
20
1
```

### Explanation

* `vari1` is global
* `a` and `b` are local to their functions
* Each function has its **own execution context**

---

## Key Takeaways (Quick Revision)

* JavaScript executes code using **Execution Context**
* Every context has:

  * Memory Phase
  * Execution Phase
* Functions create **new execution contexts**
* Call Stack manages execution order
* JavaScript is **single-threaded**
* Lexical scope allows inner → outer access

---
