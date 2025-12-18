## JavaScript Operators

---

## 1. Arithmetic Operators

Used for mathematical operations.

| Operator | Meaning             |
| -------- | ------------------- |
| `+`      | Addition            |
| `-`      | Subtraction         |
| `*`      | Multiplication      |
| `/`      | Division            |
| `%`      | Modulus (remainder) |
| `**`     | Exponent            |
| `++`     | Increment           |
| `--`     | Decrement           |

Example:

```js
let a = 10;
let b = 3;
a + b;   // 13
a % b;   // 1
```

---

## 2. Assignment Operators

Used to assign values.

| Operator | Meaning             |
| -------- | ------------------- |
| `=`      | Assign              |
| `+=`     | Add and assign      |
| `-=`     | Subtract and assign |
| `*=`     | Multiply and assign |
| `/=`     | Divide and assign   |
| `%=`     | Modulus and assign  |

Example:

```js
let x = 5;
x += 2;  // 7
```

---

## 3. Comparison Operators

Return **boolean** (`true` or `false`).

| Operator | Meaning               |
| -------- | --------------------- |
| `==`     | Equal to              |
| `===`    | Strict equal          |
| `!=`     | Not equal             |
| `!==`    | Strict not equal      |
| `>`      | Greater than          |
| `<`      | Less than             |
| `>=`     | Greater than or equal |
| `<=`     | Less than or equal    |

---

## Difference Between `==` and `===`
### Difference Table

| Feature         | `==` | `===` |
| --------------- | ---- | ----- |
| Type check      | No   | Yes   |
| Type conversion | Yes  | No    |
| Recommended     | No   | Yes   |

Use `===` always (best practice).

---

## 4. Logical Operators

Used with boolean values.

| Operator | Meaning     |   |            |
| -------- | ----------- | - | ---------- |
| `&&`     | Logical AND |   |            |
| `        |             | ` | Logical OR |
| `!`      | Logical NOT |   |            |

Example:

```js
true && false  // false
true || false  // true
!true          // false
```

---

## 5. Bitwise Operators

Operate on bits.

| Operator | Meaning     |    |
| -------- | ----------- | -- |
| `&`      | AND         |    |
| `        | `           | OR |
| `^`      | XOR         |    |
| `~`      | NOT         |    |
| `<<`     | Left shift  |    |
| `>>`     | Right shift |    |

---

## 6. Ternary Operator

Short form of if-else.

```js
condition ? value1 : value2;
```

Example:

```js
let result = age >= 18 ? "Adult" : "Minor";
```

---

## 7. String Operators

| Operator | Meaning              |
| -------- | -------------------- |
| `+`      | String concatenation |
| `+=`     | Append string        |

Example:

```js
"Hello" + " World"  // "Hello World"
```

---
