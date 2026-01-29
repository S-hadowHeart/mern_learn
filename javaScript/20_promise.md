## Promise

* A **Promise** is a **built-in class** in JavaScript.
* Using it, we can create a **Promise object**.
* A Promise represents a value that may be:

  * available **now**
  * available **later**
  * or **never**

---

## Promise States

A Promise always stays in **one** of these states:

1. **Pending**
   Initial state (neither success nor failure)

2. **Fulfilled**
   Operation completed successfully → `resolve(value)`

3. **Rejected**
   Operation failed → `reject(error)`

> Once settled (fulfilled or rejected), the state **cannot change**.

---

## Creating a Promise

```js
function createPromise() {
  return new Promise(function exec(resolve, reject) {
    // async code usually goes here
    setTimeout(function () {
      console.log("timer done");
      resolve("10");     // success
      // reject("11");   // failure
    }, 3000);
  });
}
```

---

## Using the Promise

```js
console.log("start");

let x = createPromise();
console.log("got a new promise");
console.log("got a new promise");

x.then(function (value) {
  console.log("Promise done", value);
})
.catch(function (value) {
  console.log("Handled", value);
})
.finally(function () {
  console.log("Finally");
});
```

---

## Output Order (Conceptual)

```
start
got a new promise
got a new promise
(timer delay...)
timer done
Promise done 10
Finally
```

---

## Why Promises Are Better Than Callbacks

* **Better readability**
* Avoids **callback hell**
* Clear **success / failure handling**
* Acts as a **placeholder** for a future value

---

## Promise as a Placeholder

```js
let x = createPromise();
```

* `x` does NOT contain the final value immediately
* It contains a **promise object**
* The actual value comes later via `.then()`

---

## Event Loop & Execution Flow (Important)

### What happens internally?

1. **Call Stack**

   * Executes synchronous code first

2. **setTimeout**

   * Goes to **Web APIs**
   * Callback moves to **Callback Queue**

3. **Promise (`then / catch`)**

   * Goes to **Microtask Queue**

4. **Priority**

   ```
   Microtask Queue (Promises)  →  Callback Queue (setTimeout)
   ```

Promises always execute **before** normal callbacks.

---

## Why Promises Have Higher Priority

* Promise handlers (`then`, `catch`) are placed in the **Microtask Queue**
* Microtasks are executed:

  * after the current call stack
  * **before** the callback queue

---

## Heavy Loop Example

```js
for (let i = 0; i < 1000000000000; i++) {
  // blocking code
}
```

* Blocks the **call stack**
* Promise resolution waits
* JS is **single-threaded**

---

## Summary (Quick Revision)

* Promise is a **class**
* `new Promise((resolve, reject) => {})`
* States: `pending → fulfilled / rejected`
* `.then()` → success
* `.catch()` → error
* `.finally()` → always runs
* Promises use **microtask queue**
* Higher priority than callbacks

---

