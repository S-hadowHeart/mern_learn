# JavaScript Conditional Statements, Loops & Scope

---

## If Statement

- `if` runs a block **only when the condition is true**.
- If the condition is false and there is **no else**, nothing runs.

```js
let age = 19;

if (age >= 18) {
  console.log("You are allowed to vote");
}
````

**Output:**

```
You are allowed to vote
```

---

## If condition fails (no output case)

```js
let age = 17;

if (age >= 18) {
  console.log("You are allowed to vote");
}
```

* Condition is false
* **No output**, because there is no `else`

---

## If–Else Statement

* `else` runs **when the if condition is false**
* Ensures **some output always happens**

```js
let age = 17;

if (age >= 18) {
  console.log("Allowed");
} else {
  console.log("Not allowed");
}
```

**Output:**

```
Not allowed
```

---

## Else–If Ladder

* Used when there are **multiple conditions**
* Checked **top to bottom**
* First true condition runs, rest are skipped

```js
let signal = "red";

if (signal == "red") {
  console.log("Red => STOP");
}
else if (signal == "yellow") {
  console.log("Yellow => GO Slow");
}
else if (signal == "green") {
  console.log("Green => GO");
}
else {
  console.log("Invalid");
}
```

**Output:**

```
Red => STOP
```

* If `signal = "pink"`
  **Output:**

```
Invalid
```

---

## Scope `{ }`

* `{ }` defines a **scope (block)**
* Code inside `{ }` runs **only if the condition is true**
* Variables declared with `let` or `const` inside `{ }`
  ➜ **cannot be accessed outside**

```js
if (true) {
  let x = 10;
}
// x is NOT accessible here
```

---

## Switch Case

* Alternative to `if–else`
* Best when checking **one value against many options**
* `break` stops execution
* `default` runs if no case matches

```js
let user = "Admin";

switch (user) {
  case "Admin":
    console.log("He is Admin");
    break;

  case "student":
    console.log("He is student");
    break;

  case "Mentor":
    console.log("He is mentor");
    break;

  default:
    console.log("I am Default, who are you?");
}
```

---

## Loops

* Used to **repeat work**
* Types:

  * `for`
  * `while`
  * `do while`
* In modern JS, `map`, `filter`, `forEach` are also used

---

## For Loop (Most Used)

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

**Output:**

```
0
1
2
3
4
```

---

## While Loop

* Runs **while condition is true**

```js
let i = 0;

while (i < 5) {
  console.log(i);
  i++;
}
```

---

## Do–While Loop

* Runs **at least one time**
* Condition checked **after execution**

```js
let i = 0;

do {
  console.log("Hello World");
  i++;
} while (i > 5);
```

**Output:**

```
Hello World
```

---

## Ternary Operator (Short If–Else)

**Syntax:**

```
condition ? trueValue : falseValue
```

```js
isLoggedIn = true;

isLoggedIn
  ? console.log("Home Page")
  : console.log("Login Page");
```

**Output:**

```
Home Page
```

---

## Loosely Typed JavaScript

* JavaScript is **loosely typed**
* Variable type is decided **at runtime**
* `let`, `var`, or even no keyword can work (not recommended)

```js
x = 10;   // works, but bad practice
```

* This behavior is called **loose typing**

---

## Best Practices

* Use `let` or `const`
* Prefer `for` loop for basic repetition
* Use `switch` for fixed values
* Use ternary for **short conditions only**
