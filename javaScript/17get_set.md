# Getters and Setters in JavaScript

---

## What are Getters and Setters?

* **Getters (`get`)** are used to **read/access** a property
* **Setters (`set`)** are used to **update/modify** a property
* They help **control access** to class members
* Mostly used with **private properties (`#`)**

---

## Why Do We Need Getters & Setters?

* To **apply rules/validation** while accessing data
* To **protect private data**
* To achieve **encapsulation**
* To keep class logic **secure and clean**

---

## Example 1: Using Methods (Traditional Way)

```js
class Product {
  #rating;

  getRating() {
    return this.#rating;
  }

  setRating(r) {
    if (r < 0) return;
    this.#rating = r;
  }
}

const p = new Product();
p.setRating(19);
console.log(p.getRating());
```

### Output:

```
19
```

---

## Example 2: Using Getter & Setter Keywords (Property Style)

```js
class Product {
  #rating;

  get gRating() {
    return this.#rating;
  }

  set sRating(r) {
    if (r < 0) return;
    this.#rating = r;
  }
}

const p = new Product();
p.sRating = 10;       // looks like property, works like method
console.log(p.gRating);
```

### Output:

```
10
```

---

## Key Difference Between Methods & Getter/Setter

| Method Style        | Getter/Setter Style |
| ------------------- | ------------------- |
| `p.setRating(10)`   | `p.sRating = 10`    |
| `p.getRating()`     | `p.gRating`         |
| Looks like function | Looks like property |
| More verbose        | Cleaner & readable  |

---

## Important Rules ⚠️

* Getters **cannot take parameters**
* Setters **must take exactly one parameter**
* Getter & setter names can be different
* Getter/setter **don’t need parentheses**

---

## Validation Example (Rule Enforcement)

```js
set sRating(r) {
  if (r > 5) {
    console.log("Rating cannot exceed 5");
    return;
  }
  this.#rating = r;
}
```

---

## Real-World Use Case 🏦 (Bank Example)

```js
class BankAccount {
  #balance = 0;

  get balance() {
    return this.#balance;
  }

  set deposit(amount) {
    if (amount <= 0) return;
    this.#balance += amount;
  }
}

const acc = new BankAccount();
acc.deposit = 5000;
console.log(acc.balance);
```

---


