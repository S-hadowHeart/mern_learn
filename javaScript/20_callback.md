## Higher-Order Function (HOF) – Mini Reminder

* A **Higher-Order Function** is a function that:

  * **takes another function as an argument**, or
  * **returns a function**

* The function **passed as an argument** is called a **Callback function**

---

### Example

```js
function h(x, fn) {
  // h → Higher-Order Function
  // fn → Callback Function
  console.log(x * x);
  fn();
}

h(10, function () {
  console.log("done with callback");
});
```

**Output**

```
100
done with callback
```

---

### Why callbacks are used

* To run code **after** some task is completed
* Common in:

  * event handling
  * timers (`setTimeout`)
  * array methods (`map`, `forEach`)
  * async operations

---

## Callback Hell

* When callbacks are **nested inside callbacks**
* Code becomes:

  * hard to read
  * hard to debug
  * hard to maintain

### Example idea (not full code)

```js
doTask1(() => {
  doTask2(() => {
    doTask3(() => {
      doTask4(() => {
        // callback hell
      });
    });
  });
});
```

---

## Inversion of Control

* You **lose control** over execution flow
* You trust another function/library to call your callback correctly
* This is a major problem with heavy callback usage

---

## Solution

* **Promises** (and later `async/await`)
* Promises help:

  * avoid callback hell
  * regain control over execution
  * write cleaner async code

(We’ll cover Promises later.)

---

