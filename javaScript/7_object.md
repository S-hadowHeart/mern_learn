
# Objects in JavaScript

---

## What Are Objects?

- An **object** is an entity that has:
  - **Properties** (data / attributes)
  - **Methods** (behavior / actions)
- Objects represent **real-world entities**.

### Real-Life Examples
- Car
- Pen
- Bicycle
- Chair
- Glass
- Keyboard
- Monitor

---

## Object = Properties + Behavior

### Example: Car Object

**Properties (Data):**
- Name
- Manufacturer
- Fuel Capacity

**Behavior (Methods):**
- Start
- Stop
- Accelerate


Car 1:
Name: Honda City
Manufacturer: Honda
Fuel Capacity: 40

Car 2:
Name: Seltos
Manufacturer: Kia
Fuel Capacity: 50


* Objects are **not differentiated by behavior**
* Objects are **differentiated by properties**

---

## Object Structure

* Objects store data in **key : value** pairs
* Keys and values are separated by a **colon (`:`)**

```js
let car = {
  name: "Honda City",
  manufacturer: "Honda",
  fuelCapacity: 40
};
```

---

## Variables vs Objects

### Variables

* Store **only one value**
* Simple and limited
* Example:

```js
let name = "ABC";
let age = 20;
```

---

### Objects

* Store **multiple values** under one name
* Can store different data types
* Better data organization

```js
let person = {
  firstName: "ABC",
  lastName: "XYZ",
  age: 20
};
```

---

## Why Do We Need Objects?

* Variables can hold only **one value**
* Objects can hold **multiple values of multiple data types**
* Reduce the need for many variables
* Improve code organization and readability
* Essential for building real-world applications
* Core concept behind modern web development

---

## Creating Objects

### 1. Object Literal (Most Common)

```js
let obj = { id: 101, name: "Mico", salary: 10000 };
console.log(obj);
```

**Output:**

```
{ id: 101, name: 'Mico', salary: 10000 }
```

---

### 2. Using `new Object()`

```js
let emp = new Object();
console.log(emp);

emp.id = 102;
emp.name = "Bakage";

console.log(emp);
```

**Output:**

```
{}
{ id: 102, name: 'Bakage' }
```

---

### 3. Constructor Function

```js
function Emp(i, n, s) {
  this.id = i;
  this.name = n;
  this.salary = s;
}

const e = new Emp(103, "Aho", 12000);
console.log(e);
```

**Output:**

```
{ id: 103, name: 'Aho', salary: 12000 }
```

---

## Accessing Object Properties

### Dot Notation

```js
console.log(emp.id);
```

### Bracket Notation

```js
console.log(emp["name"]);
```

**Output:**

```
102
Bakage
```

---

## Adding / Updating Values

```js
console.log(emp);

emp.salary = 15000;
console.log(emp);
```

**Output:**

```
{ id: 102, name: 'Bakage' }
{ id: 102, name: 'Bakage', salary: 15000 }
```

* Same syntax is used to **update existing values**

---

## Deleting a Property

```js
delete emp.id;
console.log(emp);
```

---

## Object Methods

```js
let emp = {
  id: 101,
  name: "Anya",
  age: 24
};
```

---

### `Object.keys()`

```js
let keys = Object.keys(emp);
console.log(keys);
```

**Output:**

```
["id", "name", "age"]
```

---

### `Object.values()`

```js
let values = Object.values(emp);
console.log(values);
```

**Output:**

```
[101, "Anya", 24]
```

---

### `Object.entries()`

```js
let entries = Object.entries(emp);
console.log(entries);
```

**Output:**

```
[
  ["id", 101],
  ["name", "Anya"],
  ["age", 24]
]
```

---

## `Object.freeze()`

* Prevents:

  * Updating
  * Adding
  * Deleting properties

```js
Object.freeze(emp);

emp.id = 100;
emp.address = "random";
delete emp.name;

console.log(emp);
```

* Object remains unchanged

---

## `Object.seal()`

* Allows:

  * Updating existing properties
* Prevents:

  * Adding new properties
  * Deleting properties

```js
Object.seal(emp);

emp.id = 100;      // allowed
emp.address = ""; // not allowed
delete emp.name;  // not allowed
```

---

## `Object.assign()` – Copy Object

```js
let o = Object.assign({}, emp);
console.log(o);
```

* Creates a **shallow copy**
* Original object remains unchanged

---

## Key Takeaways

* Objects store **related data together**
* Properties are stored as **key : value**
* Objects are fundamental to JavaScript
* Used everywhere: APIs, UI components, databases
* Mastering objects = mastering JavaScript


