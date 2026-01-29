## `async` Function

* An `async` function **always returns a Promise**
* Even if you return a normal value, JavaScript wraps it in a Promise

```js
async function consume() {
  return 10;
}

console.log(consume());
// Promise { fulfilled: 10 }
```

---

## What is `await`?

* `await` **pauses execution inside an async function**
* It waits until the Promise is **resolved or rejected**
* It **does NOT block** the main thread or other code
* Can be used **only inside async functions**

---

## Creating a Promise

```js
function createPromise() {
  return new Promise(function exec(resolve, reject) {
    setTimeout(function () {
      console.log("timer done");
      resolve(10);
    }, 3000);
  });
}
```

---

## Using `await`

```js
async function consume() {
  console.log("inside function");

  const response = await createPromise();
  console.log("response is", response);
}

console.log("start");
consume();
console.log("end");
```

### Output Order

```
start
inside function
end
(timer delay...)
timer done
response is 10
```

* `await` pauses **only `consume()`**
* Other code continues to run

---

## Handling Rejected Promises (try–catch)

```js
async function consume() {
  try {
    const response = await createPromise();
    console.log("response is", response);
  } catch (error) {
    console.log("error handled", error);
  }
}
```

---

## `fetch()` (Runtime Environment Function)

* `fetch()` is provided by the **browser / runtime**
* Used to make HTTP requests
* Returns a **Promise**

---

## Fetch Example (Promise style)

```js
fetch("https://type.fit/api/quotes")
  .then(function (response) {
    return response.json();
  })
  .then(function (value) {
    console.log(value);
  })
  .catch(function (err) {
    console.log("error", err);
  });
```

---

## Fetch Example (async / await – cleaner)

```js
async function getQuotes() {
  try {
    const response = await fetch("https://type.fit/api/quotes");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.log("error", error);
  }
}

getQuotes();
```

---

## Key Takeaways (Quick Reminder)

* `async` → always returns a Promise
* `await` → waits for Promise result
* `await` pauses **function**, not whole program
* Use `try-catch` for error handling
* `fetch()` → returns a Promise
* `async/await` = cleaner Promise syntax

---

