## Browser Engines

A browser is also just a software program.  
To display a webpage, it must understand:
- How to layout content
- How to render it visually
- How to run JavaScript

Browser internals consist of two main engines:
1. **Layout (Rendering) Engine**
2. **JavaScript Engine**

---

### Layout (Rendering) Engines
Responsible for:
- Parsing HTML and CSS
- Creating the DOM and CSSOM
- Calculating layout
- Painting pixels to the screen

Examples:
- **Blink** (Chromium, Chrome, Edge, Opera)
- **WebKit** (Safari, iOS browsers)
- **Gecko** (Mozilla Firefox)

---

## JavaScript Engines
Responsible for:
- Executing JavaScript code
- Managing memory
- Compiling and optimizing JS

Examples:
- **V8 Engine** (Chrome, Node.js) – written in C++
- SpiderMonkey (Firefox)
- JavaScriptCore (Safari)

---

## Why Programmers Need Browser Engines
- They convert programmer's HTML, CSS, and JS into visual webpages.
- They interpret code, calculate layout, and handle interactivity.

---

## V8 Engine, Node.js, Chrome
- V8 is Google's high-performance JS engine.
- Written in C++.
- Node.js uses V8 to run JavaScript outside the browser.
