## `this` Keyword

```js
console.log(this)
```

* In **Node.js**, it prints `{}` (empty object).
* In **browser console**, it prints a global object (`window`).
* This happens because the **global object is different** in Node.js and browsers.
* Reason will be explained later.

---

## Data Types in JavaScript

### Primitive Data Types

* **Number**: `2`, `3`, `4.5`, `24`
* **String**: `"Hello"` or `'Hello'`
* **Boolean**: `true`, `false`
* **null**: Represents an intentional empty value
  Example: temperature not available
* **undefined**: Variable declared but not assigned
  Example:

  ```js
  let a;
  ```

---

### Non-Primitive Data Types

* **Array**

  ```js
  [1, 2, 3]
  ```
* **Object**

  ```js
  {}
  ```

---

## Variables Declaration

* Use `let` or `const`
* Avoid `var` (scope issues; will be discussed later)
* Prefer `const` as much as possible
  Experienced developers use `const` by default and `let` only when reassignment is needed

---

