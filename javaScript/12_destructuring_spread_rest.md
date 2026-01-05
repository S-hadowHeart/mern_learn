## JavaScript Arrays & Arguments

---

## Array Type

```js
let newArray = [1,2,3,5];
console.log(typeof newArray);
````

**Output:**

```
object
```

➡️ In JavaScript, **arrays are objects**

---

## Combining Arrays

```js
const oneArray = [1,2,3,4];
const twoArray = [5,6,7,8];
```

### Using concat()

```js
const threeArray = oneArray.concat(twoArray);
```

✔️ Returns a **new flat array**

---

### Array inside Array (❌ not merged)

```js
const threeArray = [oneArray, twoArray];
console.log(threeArray);
```

**Output:**

```
[[1,2,3,4],[5,6,7,8]]
```

---

### Using Spread Operator (✅ best way)

```js
const threeArray = [...oneArray, ...twoArray];
console.log(threeArray);
```

**Output:**

```
[1,2,3,4,5,6,7,8]
```

---

## Functions & Arguments Object

```js
function testOne() {
  console.log(arguments);
}
testOne(1,2,4,5,6);
```

* `arguments` is an **array-like object**
* Available only in **normal functions**
* Functions are also **objects** in JS

---

## Array Creation (Wrong vs Correct)

❌ Wrong:

```js
var newArrayTwo = new Array[1,2,4,5];
```

✅ Correct:

```js
var newArrayTwo = new Array(1,2,4,5);
```

---

## Convert arguments → Array

### Using `Array.from()`

```js
function manyArguments() {
  var args = Array.from(arguments);
  var finalArr = args.map(e => e);
  console.log(finalArr);
}

manyArguments(1,2,3);
manyArguments(1,2,3,4,5,6,7);
```

---

## Rest Operator (`...args`) – Modern Way ✅

```js
function manyArgumentv2(...args) {
  console.log(typeof args); // object
  let finalArr = args.map(e => e);
  console.log(finalArr);
}

manyArgumentv2(1,2,3,4);
```

* `args` is a **real array**
* Works with **arrow functions**
* Cleaner & preferred approach

---

