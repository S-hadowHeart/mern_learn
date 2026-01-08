# Classes and Objects in JavaScript

---

## What is a Class?

* A **class** is a **blueprint** for creating objects.
* It defines:

  * **Properties** (data / variables)
  * **Methods** (behavior / functions)
* Classes help organize and structure code.
* Introduced in **ECMAScript 6 (ES6)**.

---

## Why Use Classes?

* **Object-Oriented Programming (OOP)**
* **Reusability** – write once, use many times
* **Abstraction** – hide internal details
* **Encapsulation** – bind data + methods together
* **Modularity** – clean and maintainable code

---

## Basic Class Syntax

```js
class Product {
  // properties (data members)
  name;
  price;
  rating;

  // methods (member functions)
  display() {
    console.log("Displaying the current product");
  }
}

const p = new Product();
console.log(p);
p.display();
```

### Output:

```
Product { name: undefined, price: undefined, rating: undefined }
Displaying the current product
```

---

## Constructor in Class

* A **constructor** is a special method.
* Automatically called when `new` keyword is used.
* Used to initialize object properties.
* ❌ Only **one constructor** allowed per class.

```js
class Product {
  constructor() {
    console.log("Calling constructor");
  }

  display() {
    console.log("Displaying product");
  }
}

const p = new Product();
```

### Output:

```
Calling constructor
Displaying product
```

---

## Constructor with Parameters & `this`

```js
class Product {
  constructor(n, p, r) {
    this.name = n;
    this.price = p;
    this.rating = r;
  }

  display() {
    console.log("This refers to:", this);
    console.log(this.name, this.price, this.rating);
  }
}

const p = new Product("iPhone", 100000, 5);
p.display();
```

### Why `this`?

* `new` creates an **empty object**
* `this` refers to **that newly created object**
* Properties are attached using `this.property`

---

## Return Behavior in Constructor

* Returning **primitive** → ignored
* Returning **object** → replaces `this`

```js
class Product {
  constructor() {
    return { x: 0, y: 20 };
  }
}

const p = new Product();
console.log(p);
```

### Output:

```
{ x: 0, y: 20 }
```

---

## Accessing Properties

```js
console.log(p.name);
```

---

# Function Constructor (Before ES6)

```js
function Product(n, p, r) {
  this.name = n;
  this.price = p;
  this.rating = r;
}

const q = new Product("MacBook", 150000, 5);
console.log(q);
```

---

## Return Rules in Function Constructor

* `return 10` → ignored
* `return {}` → returned
* no return → `this` returned

---

## `this` Keyword in JavaScript

* `this` refers to the **calling context**
* Different from other languages

Example without `new`:

```js
let x = {
  p: Product
};

x.p("AirPods", 20000, 5);
console.log(x);
```

### Output:

```
{ p: ƒ, name: 'AirPods', price: 20000, rating: 5 }
```

---

## Function Constructor Variations

### Function Expression (Works)

```js
const Product = function (n, p, r) {
  this.name = n;
  this.price = p;
  this.rating = r;
};

const p = new Product("Phone", 50000, 4);
```

---

### Arrow Function Constructor ❌ (Does NOT work)

```js
const Product = (n, p, r) => {
  this.name = n;
};

const p = new Product("iPhone", 100000, 5);
```

### Output:

```
TypeError: Product is not a constructor
```

❌ Arrow functions **do not have their own `this`**

---

## `this` with Normal Method

```js
let obj = {
  x: 10,
  fun() {
    console.log(this.x);
  }
};

obj.fun();
```

### Output:

```
10
```

---

## `this` with Arrow Method

```js
let obj = {
  x: 10,
  fun: () => {
    console.log(this.x);
  }
};

obj.fun();
```

### Output:

```
undefined
```

➡️ Arrow functions take `this` from **outer scope**, not object.

---

## Arrow Function Inside Method (Works)

```js
let obj = {
  x: 10,
  fun() {
    let y = {
      gun: () => {
        console.log(this.x);
      }
    };
    y.gun();
  }
};

obj.fun();
```

### Output:

```
10
```

---

## Summary 

* Class = blueprint
* Object = instance of class
* `constructor()` initializes data
* `this` refers to calling context
* Arrow functions ❌ don’t bind `this`
* Use **classes / normal functions** for constructors
