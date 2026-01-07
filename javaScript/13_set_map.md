### What is a Set?
- A `Set` is a **collection of unique values**
- Duplicate values are **automatically removed**
- Order of insertion is preserved

---

### Creating a Set

```js
var emptySet = new Set();
console.log(emptySet.size);
````

**Output:**

```
0
```

---

### Set from an Array

```js
var myArray = [1,2,3,4,2];
var newSet = new Set(myArray);
console.log(newSet);
```

**Output:**

```
Set(4) {1, 2, 3, 4}
```

---

### Adding Values

```js
newSet.add(2); // duplicate → ignored
newSet.add(5);
console.log(newSet);
```

**Output:**

```
Set(5) {1, 2, 3, 4, 5}
```

---

### Checking Value

```js
console.log(newSet.has(9));
```

**Output:**

```
false
```

---

### Clearing a Set

```js
newSet.clear();
console.log(newSet);
```

**Output:**

```
Set(0) {}
```

---

### Practical Example (Filter Long Words)

```js
const words = ["javascript","html","frontend","backend","nodejs","api"];
const result = words.filter(word => word.length > 6);
console.log(result);
```

---

### Set Difference (A − B)

```js
function setDifference(setA, setB) {
  return new Set([...setA].filter(el => !setB.has(el)));
}
```

---

### Other Important Set Methods

| Method        | Description        |
| ------------- | ------------------ |
| add(value)    | Add value          |
| has(value)    | Check value        |
| delete(value) | Remove value       |
| clear()       | Remove all         |
| size          | Number of elements |

---

## JavaScript `Map`

---

### What is a Map?

* A `Map` stores **key → value** pairs
* Keys can be **any data type**
* Maintains insertion order

---

### Creating a Map

```js
let map = new Map();
console.log(map.size);
```

**Output:**

```
0
```

---

### Adding Values to Map

```js
map.set(1, "Mithun");
map.set(2, "Alka");
map.set(3, "Prabir");
map.set(4, "Mico");
map.set(5, "Nico");
```

---

### Getting Values

```js
console.log(map.get(3));
```

**Output:**

```
Prabir
```

---

### Checking & Deleting

```js
console.log(map.has(2)); // true
map.delete(2);
```

---

### Looping Through Map

```js
map.forEach((value, key) => {
  console.log(key, value);
});
```

---

### Convert Array → Map (Correct Way)

```js
const arr = [
  [1,"Mithun"],
  [2,"Alka"],
  [3,"Prabir"],
  [4,"Mico"],
  [5,"Nico"]
];

let map = new Map(arr);
console.log(map);
```

---

### Important Map Methods

| Method         | Description |
| -------------- | ----------- |
| set(key,value) | Add         |
| get(key)       | Read        |
| has(key)       | Check       |
| delete(key)    | Remove      |
| clear()        | Remove all  |
| size           | Count       |

---

## Set vs Map (Quick Difference)

| Feature   | Set           | Map             |
| --------- | ------------- | --------------- |
| Stores    | Values only   | Key–Value       |
| Duplicate | ❌ Not allowed | Keys ❌          |
| Use case  | Unique items  | Structured data |

---


