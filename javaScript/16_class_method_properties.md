=

# Static Methods in JavaScript

---

## What is a Static Method?

* A **static method belongs to the class**, not to the object
* It is defined using the `static` keyword
* Cannot be accessed using an object (instance)
* Accessed **directly using the class name**

---

## Correct Syntax

```js
class Hello {
  password = "mico";

  static custom() {
    console.log("Calling custom method");
  }
}
```

---

## Accessing Static Method ❌ (Wrong)

```js
const p = new Hello();
p.custom();
```

### Output:

```
TypeError: p.custom is not a function
```

➡️ Because **static methods are not part of the object**

---

## Accessing Static Method ✅ (Correct)

```js
Hello.custom();
```

### Output:

```
Calling custom method
```

---

## Accessing Normal Property

```js
console.log(p.password);
```

### Output:

```
mico
```

➡️ Instance properties are accessed using objects

---

## Why Do We Need Static Methods?

* Utility/helper functions
* Logic that is **common to all objects**
* Does **not depend on object data**
* Improves code organization

### Example:

```js
class MathUtils {
  static add(a, b) {
    return a + b;
  }
}

MathUtils.add(2, 3); // 5
```

---

# Abstraction

---

## What is Abstraction?

* Abstraction means **hiding internal details**
* Showing **only essential features**
* User does **not care how it works internally**

---

## Real-World Example: Bank 🏦

When you:

* Withdraw money
* Check balance

You **don’t know**:

* Database logic
* Security checks
* Server communication

➡️ You only see **simple actions**

---

## Abstraction Example in JavaScript

```js
class BankAccount {
  #balance = 10000; // private field

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const acc = new BankAccount();
acc.deposit(2000);
console.log(acc.getBalance());
```

---

## Trying to Access Private Data ❌

```js
console.log(acc.#balance);
```

### Output:

```
SyntaxError: Private field '#balance' must be declared
```

---

## Why Do We Need Abstraction?

* Improves **security**
* Reduces **complexity**
* Makes code **easy to use**
* Protects internal logic

---

# Public vs Private

---

## Public Members

* Accessible everywhere
* Default in JavaScript

```js
class Demo {
  value = 10;
}
```

---

## Private Members

* Accessible **only inside the class**
* Declared using `#`

```js
class Demo {
  #secret = "hidden";
}
```

---

## Example: Public vs Private

```js
class Product {
  name = "Phone";      // public
  #rating = 5;         // private
}

const p = new Product();
console.log(p.name);    // ✅ works
console.log(p.rating); // ❌ undefined
```

---

## `#secret` Example

```js
p.rating = 10;
console.log(p.rating);
```

### Output:

```
10
```

➡️ This creates a **new public property**
➡️ It does NOT affect the private `#rating`

---

## Summary 🚀

* `static` → class-level method
* Static methods accessed via **class name**
* Abstraction hides internal logic
* Public → accessible everywhere
* Private (`#`) → accessible only inside class
* Security & clean design matter more than tools

