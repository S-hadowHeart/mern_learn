## JavaScript Regular Expressions (Regex)

---

## What is Regex?
- Regex (Regular Expression) is used to **search, match, replace, or validate text**
- Very powerful for **string manipulation**

---

## Creating a Regular Expression

### 1. Using RegExp Constructor
```js
let pattern = "man";
let regExOne = new RegExp(pattern);
````

### 2. Using Flags

```js
let flag = "gi"; // g = global, i = case-insensitive
let regExTwo = new RegExp(pattern, flag);
```

### 3. Using Literal Syntax (Most Common)

```js
let regExThree = /man/gi;
```

---

## Flags Explained

| Flag | Meaning                        |
| ---- | ------------------------------ |
| g    | Global (match all occurrences) |
| i    | Case-insensitive               |
| m    | Multiline                      |

---

## Test String

```js
const strToCheck =
  "ironman is friend of spiderman and batman coming to spiderman home on new year";
```

---

## test()

* Returns `true` or `false`
* Checks if pattern exists

```js
const result = regExThree.test(strToCheck);
console.log(result); // true
```

---

## match()

* Returns an **array of matched values**
* Returns `null` if no match

```js
const anotherResult = strToCheck.match(regExThree);
console.log(anotherResult);
// ["man", "man", "man"]
```

---

## replace()

* Replaces matched text
* Returns a **new string**

```js
const oneMoreResult = strToCheck.replace(regExThree, "p-w");
console.log(oneMoreResult);
```

---

## Real-World Example: URL Cleanup

```js
const webUrl = "https://ironman.com/tony%20star";
```

### Replace specific pattern

```js
const usableUrl = webUrl.replace(/%20/, "-");
console.log(usableUrl);
```

### Replace any encoded value (% followed by two digits)

```js
const usableUrl2 = webUrl.replace(/%\d\d/, "-");
console.log(usableUrl2);
```

---

## Common Regex Patterns

| Pattern | Meaning         |
| ------- | --------------- |
| \d      | Any digit (0–9) |
| \D      | Non-digit       |
| \w      | Word character  |
| \s      | Whitespace      |
| .       | Any character   |
| +       | One or more     |
| *       | Zero or more    |

---

## Regex Practice & Reference

* 🔗 **regexr.com**
* Community-tested patterns
* Live testing & explanations

---

## Key Takeaways 🚀

* Use `/pattern/flags` for cleaner regex
* `test()` → boolean check
* `match()` → extract matches
* `replace()` → modify strings
* Regex is essential for **validation, parsing & sanitization**


