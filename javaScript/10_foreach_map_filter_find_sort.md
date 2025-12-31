## forEach, map, filter, reduce & other Array HOFs

---

## forEach()

- Used to **iterate over array elements**
- Does **not return anything**
- Mainly used for **side effects** (logging, updating UI, etc.)

```js
let arr = [2, 3, 4];

arr.forEach(function (element, index, arr) {
  console.log(index, element, arr);
});

arr.forEach((element, index, arr) => {
  console.log("arrow:", index, element, arr);
});
````

---

## Example: forEach with strings

```js
const heros = ["ironman", "captain", "tony", "batman", "spiderman"];

heros.forEach((el) => {
  console.log(el.toUpperCase());
});
```

---

## map()

* Used to **transform array elements**
* **Returns a new array**
* Original array remains unchanged

```js
arr.map(function (element, index, arr) {
  console.log(element, index, arr);
});

heros.map((h) => h.toUpperCase());
```

⚠️ Use `map()` when you **need a new array**

---

## Difference: forEach vs map

| forEach          | map                      |
| ---------------- | ------------------------ |
| No return value  | Returns new array        |
| Used for actions | Used for transformations |
| Cannot chain     | Can chain                |

---

## filter()

* Used to **filter elements based on condition**
* Returns a **new array**

```js
console.log(heros);

const herosWithMan = heros.filter((h) => {
  return h.endsWith("man");
});

console.log(herosWithMan);
```

---

## reduce()

* Used to **reduce array to a single value**
* Commonly used for **sum, total, calculations**

```js
const cartBill = [20, 30, 50];

const sumOfCartBill = cartBill.reduce(
  (prev, curr) => prev + curr,
  0
);

console.log(sumOfCartBill);
```

---

## every()

* Checks if **all elements satisfy condition**
* Returns `true` or `false`

```js
const gameScore = [200, 100, 320, 310, 250, 150, "2"];

const gameScoreCheck = gameScore.every(
  (v) => typeof v === "number"
);

console.log("check:", gameScoreCheck);
```

---

## find()

* Returns **first element** that matches condition
* Stops once found

```js
const above200 = gameScore.find(
  (score) => score > 200
);

console.log(above200);
```

---

## Other Important Array Methods

### findIndex()

* Returns index of first matching element
* Returns `-1` if not found

```js
gameScore.findIndex(score => score > 300);
```

---

### some()

* Checks if **at least one element** matches condition

```js
gameScore.some(score => score > 300);
```

---

### sort()

* Sorts array **in-place**
* Converts values to strings by default

```js
const nums = [10, 5, 40, 25];
nums.sort((a, b) => a - b);
console.log(nums);
```

---

## Key Takeaways

* `forEach()` → perform action
* `map()` → transform data
* `filter()` → select data
* `reduce()` → compute result
* `every()` → all true?
* `some()` → at least one true?
* `find()` → first match

---


