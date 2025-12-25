# Arrays in JavaScript 
---

## What is an Array?

- An **array** in JavaScript is a **data structure** that stores an **ordered list of elements**.
- It can store **any data type**:
  - Numbers
  - Strings
  - Booleans
  - Objects
  - Other arrays
- Arrays in JavaScript are a **special type of object**.
- JavaScript arrays come with **built-in methods** to add, remove, and manipulate data.

---

## Homogeneous vs Heterogeneous

- In **other programming languages**:
  - Arrays store the **same type of data** → **Homogeneous**
- In **JavaScript**:
  - Arrays can store **multiple data types** → **Heterogeneous**

```js
let a = [1, 2, "Hello", true, null];
````

---

## Why Do We Need Arrays in JavaScript?

* Grouping related data
* Storing large amounts of data
* Better performance than multiple variables
* Easy to manage and update data
* Better code readability
* Reduces code repetition

---

## How to Create an Array

### 1. Using Array Literal (Most Common)

```js
let a = [1, 2, 3, 4, "Hello", false];
console.log(a);
```

**Output:**

```
[1, 2, 3, 4, "Hello", false]
```

---

### 2. Using Array Constructor

```js
let b = new Array();
console.log(b);
```

**Output:**

```
[]
```

---

### 3. Array with Size

```js
let c = new Array(5);
let d = new Array("abc", "def", "ghi");

console.log(c);
console.log(d);
```

**Output:**

```
[ <5 empty items> ]
["abc", "def", "ghi"]
```

---

## Accessing Array Elements (Indexing)

* Array index starts from **0**
* Last element index = `array.length - 1`

```js
console.log(a[0]);
```

**Output:**

```
1
```

```js
console.log(a[4]);
```

**Output:**

```
Hello
```

---

## Updating Array Elements

```js
a[4] = 5;
console.log(a);
```

---

## Accessing Invalid Index

```js
console.log(a[15]);
```

**Output:**

```
undefined
```

---

## Array Methods

```js
let arr = [1, 2, 3, 4, 5];
```

---

### push() – Add at End

```js
arr.push(6);
arr.push(7, 8);
console.log(arr);
```

**Output:**

```
[1, 2, 3, 4, 5, 6, 7, 8]
```

---

### pop() – Remove Last Element

```js
arr.pop();
console.log(arr);
```

**Output:**

```
[1, 2, 3, 4, 5, 6, 7]
```

---

### shift() – Remove First Element

```js
arr.shift();
console.log(arr);
```

**Output:**

```
[2, 3, 4, 5, 6, 7]
```

---

### unshift() – Add at Start

```js
arr.unshift(9);
console.log(arr);
```

**Output:**

```
[9, 2, 3, 4, 5, 6, 7]
```

---

### shift() and pop() Return Removed Value

```js
let f = arr.shift();
console.log(f);
```

**Output:**

```
9
```

---

## concat() – Merge Arrays

```js
let a1 = [1, 2, 3, 4, 5];
let a2 = [3, 4, 5];
let a3 = a1.concat(a2);

console.log(a1);
console.log(a2);
console.log(a3);
```

**Output:**

```
[1, 2, 3, 4, 5]
[3, 4, 5]
[1, 2, 3, 4, 5, 3, 4, 5]
```

---

## join() – Convert Array to String

```js
let s = a3.join(",");
console.log(s);
```

**Output:**

```
1,2,3,4,5,3,4,5
```

---

## reverse() – Reverse Array

```js
a3.reverse();
console.log(a3);
```

**Output:**

```
[5, 4, 3, 5, 4, 3, 2, 1]
```

---

## indexOf() – Find Index

```js
console.log(a3.indexOf(4));
console.log(a3.indexOf(74));
```

**Output:**

```
1
-1
```

* `-1` means element not found

---

## slice() – Extract Part of Array (Non-Destructive)

```js
let arr1 = [1, 2, 3, 4, 5, 6];
console.log(arr1.slice(2, 5));
```

**Output:**

```
[3, 4, 5]
```

---

## splice() – Add / Remove / Replace (Destructive)

### Add Element

```js
arr1.splice(2, 0, 11);
console.log(arr1);
```

**Output:**

```
[1, 2, 11, 3, 4, 5, 6]
```

---

### Replace Element

```js
arr1.splice(2, 1, 10);
console.log(arr1);
```

**Output:**

```
[1, 2, 10, 3, 4, 5, 6]
```

---

### Insert Multiple Elements

```js
arr1.splice(2, 0, 3, 4, 5, 3);
console.log(arr1);
```

---

## Key Points to Remember

* Arrays are **0-indexed**
* JavaScript arrays are **heterogeneous**
* `slice()` does NOT change original array
* `splice()` DOES change original array
* `push/pop` → end of array
* `shift/unshift` → start of array

```
