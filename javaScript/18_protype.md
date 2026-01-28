## JavaScript Prototypes 

### What you see in the console

```js
let myHeros = ["Thor", "Spiderman"]
```

When you log `myHeros` in the browser console, you see:

* Array values
* `length`
* `[[Prototype]]: Array`

  * Inside this, many array methods
  * At the end: `[[Prototype]]: Object`

If you create a plain object:

```js
let myNewObj = {}
```

You will see:

* `[[Prototype]]: Object`
* But **Object does not have another prototype inside it** (it is the base)

---

## What is a Prototype?

In JavaScript, **everything is an object** (or behaves like one).

A **prototype** is a hidden object from which another object inherits properties and methods.

* Arrays inherit from `Array.prototype`
* Objects inherit from `Object.prototype`
* Strings inherit from `String.prototype`

This is how JavaScript provides built‑in methods like `map`, `length`, `trim`, etc.

---

## Prototype with Strings

```js
let yourName = "mico"
yourName.length
yourName.__proto__
```

Even though `yourName` looks like a primitive, JavaScript temporarily converts it into a `String` object so it can access methods.

```js
let yourNameTwo = "mico       "
yourNameTwo.length
```

---

## Goal: Create a Custom `trueLength()` Method

We want a method that returns string length **after trimming spaces**, like a framework utility.

Instead of calling `trim()` manually every time, we attach a method to `String.prototype`.

```js
String.prototype.trueLength = function () {
  return this.trim().length
}

"mico        ".trueLength()
"pista       ".trueLength()
```

### Why does this work?

* `this` refers to the string on which the method is called
* JavaScript automatically binds the correct context

---

## Prototypes with Objects and Arrays

```js
let heroPower = {
  thor: "hammer",
  spiderman: "sling",
  getSpidermanPower: function () {
    console.log(`spidy power is ${this.spiderman}`)
  }
}
```

### Adding a method to **all objects**

```js
Object.prototype.mico = function () {
  console.log("mico is present in all objects")
}

heroPower.mico()
myHeros.mico()
```

This works because:

* Arrays and functions ultimately inherit from `Object.prototype`

---

## Giving Power Only to Arrays

```js
Array.prototype.heyMico = function () {
  console.log("Mico says HI")
}

myHeros.heyMico()      // works
heroPower.heyMico()   // error
```

Why?

* Objects do not inherit from `Array.prototype`

---

## Prototype-based Inheritance

```js
const User = {
  name: "top name",
  email: "top@gmail.com"
}

const Teacher = {
  classes: true
}

const TeachingSupport = {
  isAvailable: false
}

const TAAssistant = {
  makeAssignment: "JS Assignment",
  fulltime: true
}
```

Suppose `TeachingSupport` has many properties and you want them inside `TAAssistant`.

---

## Old Way (Not Recommended)

```js
const TAAssistant = {
  makeAssignment: "JS Assignment",
  fulltime: true,
  __proto__: TeachingSupport
}

TAAssistant.isAvailable
```

Works, but not clean or recommended.

---

## Modern & Recommended Way

```js
Object.setPrototypeOf(TAAssistant, TeachingSupport)
```

This approach:

* Is explicit
* Improves readability
* Preferred in modern JavaScript

---

## Prototype Chain Summary

```
Array → Array.prototype → Object.prototype → null
String → String.prototype → Object.prototype → null
Object → Object.prototype → null
```

---

## Key Takeaways

* Prototype is JavaScript’s inheritance mechanism
* Methods are shared via prototypes, not copied
* Modifying `Object.prototype` affects everything (use carefully)
* Custom utilities like `trueLength()` are built using prototypes
* `this` refers to the calling object in prototype methods

---

## Final Example

```js
String.prototype.trueLength = function () {
  console.log(`True length is ${this.trim().length}`)
}

"mico        ".trueLength()
"pista       ".trueLength()
```

Each call correctly identifies its own string using `this`.
