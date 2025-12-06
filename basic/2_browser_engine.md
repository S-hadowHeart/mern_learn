# Browser Engine – Overview Notes

## Browser as a Software
A web browser is just a software application written in programming languages like C++, C, and Rust.  
It follows well-defined rules (web standards) to understand what each part of a web page is and how it should behave.

To do this, browsers internally separate responsibilities using different **engines**.

---

## How Does a Browser Know What to Do?
When a browser loads a webpage, it divides the work into two main parts:

1. **Layout / Rendering Work**
2. **JavaScript Execution**

These responsibilities are handled by different engines inside the browser.

---

## Rendering (Layout) Engine
The rendering engine decides **how the content looks on the screen**.

It is responsible for:
- Parsing HTML into a DOM (Document Object Model)
- Parsing CSS into CSSOM
- Calculating layout (positions and sizes of elements)
- Painting pixels on the screen

In simple terms, it answers:
> “Where should this element appear and how should it look?”

### Popular Rendering Engines
- **Blink** – Used in Chromium-based browsers (Chrome, Edge, Brave, Opera)
- **WebKit** – Used by Safari (Apple)
- **Gecko** – Used by Mozilla Firefox

---

## JavaScript Engine
The JavaScript engine executes JavaScript code in the browser.

It is responsible for:
- Parsing JavaScript
- Compiling and optimizing code
- Executing scripts
- Managing memory (garbage collection)

It answers:
> “What should happen when this code runs?”

### Popular JavaScript Engines
- **V8** – Chrome, Edge, Node.js
- **JavaScriptCore** – Safari (WebKit)
- **SpiderMonkey** – Firefox (Gecko)

---

## How Rendering and JavaScript Work Together
- HTML and CSS are handled by the **rendering engine**
- JavaScript is handled by the **JavaScript engine**
- JavaScript can modify the DOM and CSS
- Any DOM change triggers the rendering engine to re-calculate layout or repaint

---

## Browser Engine Flow (Simplified)

1. Browser receives HTML, CSS, and JavaScript
2. Rendering engine parses HTML and CSS
3. JavaScript engine executes scripts
4. JavaScript modifies DOM or styles (if needed)
5. Rendering engine updates layout and paints the screen

---

## Programmer’s Code to Browser Rendering
When a developer writes HTML, CSS, and JavaScript:

- HTML defines structure
- CSS defines appearance
- JavaScript defines behavior

The browser engines translate this code into visual output by following the rendering and execution pipeline.

---

## V8 Engine Explained
**V8** is a high-performance JavaScript engine developed by Google.

Key points:
- Written in **C++**
- Converts JavaScript into optimized machine code
- Extremely fast execution
- Used in:
  - Google Chrome
  - Microsoft Edge
  - Node.js (server-side JavaScript)

---

## Node.js and V8
- Node.js uses the **V8 engine** to run JavaScript outside the browser
- Node.js does not include a rendering engine
- It provides APIs for file systems, networking, and OS-level operations

---

## Summary
- A browser is a software with multiple internal engines
- Rendering engines handle layout and visuals
- JavaScript engines handle logic and execution
- Blink, WebKit, and Gecko are major rendering engines
- V8 is a JavaScript engine written in C++
- Node.js uses V8 to run JavaScript without a browser

Understanding browser engines helps developers write better, faster, and more optimized web applications.
