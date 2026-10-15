# 🖱️ JavaScript Events

> 🎯 **Learning Objectives**
> - Understand what an event is and how JavaScript responds to it.
> - Handle events using inline attributes, DOM properties, and `addEventListener()`.
> - Use common mouse, keyboard, form, and page events.
> - Use the event object, `preventDefault()`, and `stopPropagation()`.
> - Understand event bubbling and event delegation.
> - Build a simple interactive counter.

---

## 🌟 1. What is an Event?

An **event** is something that happens on a webpage, usually caused by the user or the browser. JavaScript can **listen** for events and **react** to them.

Think of a **doorbell**. 🔔

| Doorbell | JavaScript |
|---|---|
| 👆 Someone presses the bell | The **event** happens (a click) |
| 👂 You are listening for it | The **event listener** waits |
| 🚪 You go and open the door | The **event handler** function runs |

### 🧠 Remember This!

- **Event** = something that happens (click, key press, form submit).
- **Event listener** = code that waits for the event.
- **Event handler** = the function that runs when the event happens.

---

## 💻 2. Your First Event

**📄 `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>First Event</title>
</head>
<body>

    <h1 id="heading">Hello! 👋</h1>
    <button id="btn">Click Me 🚀</button>

    <script src="script.js" defer></script>

</body>
</html>
```

**📄 `script.js`**

```javascript
const button = document.querySelector("#btn");
const heading = document.querySelector("#heading");

button.addEventListener("click", function () {
    heading.textContent = "You clicked the button! 🎉";
});
```

### 🎯 What Happens?

1. The page shows **Hello! 👋**
2. The user clicks the button.
3. The heading changes to **You clicked the button! 🎉**

### 🔍 Explanation

| Code | Purpose |
|---|---|
| `querySelector("#btn")` | Finds the button element |
| `addEventListener("click", ...)` | Listens for a click on the button |
| `function () { ... }` | The handler that runs on click |
| `textContent` | Changes the text of the heading |

### 🧩 Syntax

```javascript
element.addEventListener("eventName", handlerFunction);
```

💡 **Try It Yourself:** Change the event from `"click"` to `"dblclick"` and see what happens.

---

## 📝 3. Three Ways to Handle Events

### 🔴 Method 1: Inline Event Attribute

```html
<button onclick="alert('Hello!')">Click Me</button>
```

Quick for demos, but it mixes JavaScript into HTML, which gets messy in larger projects.

### 🟡 Method 2: DOM Property

```javascript
const button = document.querySelector("#btn");

button.onclick = function () {
    console.log("Clicked!");
};
```

⚠️ An element can hold only **one** handler this way. Assigning `onclick` again **replaces** the earlier one.

### 🟢 Method 3: `addEventListener()` ⭐ (Recommended)

```javascript
const button = document.querySelector("#btn");

button.addEventListener("click", function () {
    console.log("First handler");
});

button.addEventListener("click", function () {
    console.log("Second handler");
});
```

### 📤 Output (after one click)

```text
First handler
Second handler
```

### 📊 Quick Comparison

| Feature | Inline | DOM property | `addEventListener()` |
|---|---|---|---|
| Keeps JS separate from HTML | ❌ No | ✅ Yes | ✅ Yes |
| Multiple handlers on one event | ❌ No | ❌ No | ✅ Yes |
| Can be removed easily | ❌ No | ✅ Yes (set to `null`) | ✅ Yes (`removeEventListener`) |
| Recommended? | ⚠️ Demos only | ⚠️ Simple cases | ✅ Yes |

---

## 🗂️ 4. Common Events

### 🖱️ Mouse Events

| Event | When it happens |
|---|---|
| `click` | Element is clicked |
| `dblclick` | Element is double-clicked |
| `mouseover` | Mouse pointer enters the element |
| `mouseout` | Mouse pointer leaves the element |

```javascript
const box = document.querySelector("#box");

box.addEventListener("mouseover", function () {
    box.style.backgroundColor = "lightgreen";
});

box.addEventListener("mouseout", function () {
    box.style.backgroundColor = "white";
});
```

**Expected result:** The box turns green when the mouse is over it and white when the mouse leaves.

### ⌨️ Keyboard Events

| Event | When it happens |
|---|---|
| `keydown` | A key is pressed down |
| `keyup` | A key is released |

```javascript
document.addEventListener("keydown", function (event) {
    console.log("Key pressed: " + event.key);
});
```

### 📤 Output (pressing A, then Enter)

```text
Key pressed: a
Key pressed: Enter
```

> 💡 The old `keypress` event is deprecated. Use `keydown` instead.

### 📋 Form Events

| Event | When it happens |
|---|---|
| `input` | The value changes (fires on **every** keystroke) |
| `change` | The value is committed (for a text box, when it loses focus) |
| `submit` | A form is submitted |
| `focus` | An element receives focus |
| `blur` | An element loses focus |

```html
<input type="text" id="nameInput" placeholder="Type your name">
<p id="preview"></p>
```

```javascript
const nameInput = document.querySelector("#nameInput");
const preview = document.querySelector("#preview");

nameInput.addEventListener("input", function () {
    preview.textContent = "Hello, " + nameInput.value + "!";
});
```

**Expected result:** As you type, the paragraph updates instantly.

### 🌐 Page Events

| Event | When it happens |
|---|---|
| `DOMContentLoaded` | The HTML has been loaded and parsed |
| `load` | The whole page, including images, has loaded |

```javascript
document.addEventListener("DOMContentLoaded", function () {
    console.log("Page is ready ✅");
});
```

💡 When you use `<script src="script.js" defer>`, the script already runs after the HTML is parsed, so you usually don't need `DOMContentLoaded`.

---

## 📦 5. The Event Object

The browser passes an **event object** to your handler. It contains details about the event.

```javascript
const button = document.querySelector("#btn");

button.addEventListener("click", function (event) {
    console.log(event.type);
    console.log(event.target);
});
```

### 📤 Output

```text
click
<button id="btn">Click Me 🚀</button>
```

### 🔍 Useful Properties

| Property | Meaning |
|---|---|
| `event.type` | The type of event, such as `"click"` |
| `event.target` | The element that **triggered** the event |
| `event.currentTarget` | The element the listener is **attached to** |
| `event.key` | The key pressed (keyboard events) |
| `event.clientX` / `event.clientY` | Mouse position (mouse events) |

---

## 🛑 6. Preventing Default Behaviour

Some elements have built-in behaviour. A form reloads the page when submitted, and a link navigates away. `preventDefault()` stops that.

```html
<form id="loginForm">
    <input type="text" id="username" placeholder="Username">
    <button type="submit">Login</button>
</form>
<p id="message"></p>
```

```javascript
const form = document.querySelector("#loginForm");
const message = document.querySelector("#message");

form.addEventListener("submit", function (event) {
    event.preventDefault();   // stop the page from reloading

    const username = document.querySelector("#username").value;
    message.textContent = "Welcome, " + username + "! ✅";
});
```

**Expected result:** After typing a name and submitting, the message appears and the page does **not** reload.

---

## 🫧 7. Event Bubbling

When an event happens on an element, it first runs that element's handlers, then **bubbles up** to its parent, then the grandparent, and so on.

Think of a **bubble rising in water**. 🫧

```html
<div id="outer">
    <button id="inner">Click Me</button>
</div>
```

```javascript
document.querySelector("#outer").addEventListener("click", function () {
    console.log("Div clicked");
});

document.querySelector("#inner").addEventListener("click", function () {
    console.log("Button clicked");
});
```

### 📤 Output (clicking the button)

```text
Button clicked
Div clicked
```

### 🔍 Explanation

- The click happens on the button, so the button's handler runs first.
- The event then bubbles up to the `div`, so its handler runs too.

### ✋ Stopping the Bubble

```javascript
document.querySelector("#inner").addEventListener("click", function (event) {
    event.stopPropagation();
    console.log("Button clicked");
});
```

### 📤 Output (clicking the button)

```text
Button clicked
```

The `div` handler no longer runs.

---

## 🎯 8. Event Delegation

Instead of adding a listener to **every** item, add **one** listener to the parent and use `event.target` to find which child was clicked. It works because of bubbling, and it also works for items added later.

```html
<ul id="list">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

```javascript
const list = document.querySelector("#list");

list.addEventListener("click", function (event) {
    if (event.target.matches("li")) {
        console.log("You clicked: " + event.target.textContent);
    }
});
```

### 📤 Output (clicking the third item)

```text
You clicked: JavaScript
```

---

## ❌ 9. Removing and Limiting Listeners

### 🧹 `removeEventListener()`

You must pass the **same function reference** that you added. An anonymous function cannot be removed.

```javascript
function sayHi() {
    console.log("Hi!");
}

button.addEventListener("click", sayHi);
button.removeEventListener("click", sayHi);   // works because it is the same function
```

### 1️⃣ Run Only Once

```javascript
button.addEventListener("click", function () {
    console.log("This runs only once");
}, { once: true });
```

---

## 🔢 10. Mini Project: Counter App

**📄 `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Counter</title>
</head>
<body>

    <h2>Counter: <span id="count">0</span></h2>
    <button id="decrease">➖ Decrease</button>
    <button id="reset">🔄 Reset</button>
    <button id="increase">➕ Increase</button>

    <script src="script.js" defer></script>

</body>
</html>
```

**📄 `script.js`**

```javascript
let count = 0;
const countDisplay = document.querySelector("#count");

function updateDisplay() {
    countDisplay.textContent = count;
}

document.querySelector("#increase").addEventListener("click", function () {
    count++;
    updateDisplay();
});

document.querySelector("#decrease").addEventListener("click", function () {
    count--;
    updateDisplay();
});

document.querySelector("#reset").addEventListener("click", function () {
    count = 0;
    updateDisplay();
});
```

### 🎯 What Happens?

1. The page shows **Counter: 0**.
2. Each click on **Increase** adds 1; each click on **Decrease** subtracts 1.
3. **Reset** sets the counter back to 0.

### 🔍 Understanding the Code

- The `count` variable stores the current number.
- Each button has its own click listener.
- `updateDisplay()` is a reusable function that refreshes the page text.

---

## ⚠️ 11. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| `addEventListener("click", sayHi())` | `addEventListener("click", sayHi)`. Don't call the function |
| Writing `"onclick"` in `addEventListener` | Use `"click"` (no `on`) |
| Script runs before the HTML exists, so the element is `null` | Add `defer` or place the script at the end of `<body>` |
| Using `keypress` | Use `keydown` |
| Trying to remove an anonymous function | Store the function in a named variable first |
| Forgetting `preventDefault()` on a form | Call `event.preventDefault()` to stop the page reload |
| Confusing `input` and `change` | `input` fires on every change; `change` fires when the value is committed |

---

## 🧪 12. Practice Tasks

- [ ] 🟢 **Beginner:** Create a button that shows an `alert("Hello!")` when clicked, using `addEventListener()`.
- [ ] 🟢 **Beginner:** Change a heading's text when a button is clicked.
- [ ] 🟡 **Intermediate:** Make a box change colour when the mouse enters and reset when it leaves.
- [ ] 🟡 **Intermediate:** Show whatever the user types in a text box live in a paragraph below it.
- [ ] 🔵 **Practice:** Create a form that shows a welcome message on submit without reloading the page.
- [ ] 🔵 **Practice:** Log the name of any key the user presses.
- [ ] 🔴 **Challenge:** Build a to-do list where clicking an item crosses it out, using event delegation on the `<ul>`.
- [ ] 🔴 **Challenge:** Add a dark-mode toggle button that switches the page background and text colour.

---

## 🎤 13. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is an event in JavaScript?**

**Answer:** An event is an action or occurrence on a webpage, such as a click, key press, or form submission, that JavaScript can respond to.

**Q2. What is an event handler?**

**Answer:** A function that runs when a particular event occurs.

**Q3. What is an event listener?**

**Answer:** Code that waits for a specific event on an element and calls a handler when it happens. It is added with `addEventListener()`.

**Q4. Name some common events.**

**Answer:** `click`, `dblclick`, `mouseover`, `mouseout`, `keydown`, `keyup`, `input`, `change`, `submit`, `focus`, `blur`, and `load`.

**Q5. What is the syntax of `addEventListener()`?**

**Answer:** `element.addEventListener("eventName", handlerFunction);`

### 🟡 Intermediate Questions

**Q6. What are the three ways to handle events?**

**Answer:** Inline event attributes (like `onclick`), DOM properties (like `element.onclick = ...`), and `addEventListener()`.

**Q7. Why is `addEventListener()` preferred?**

**Answer:** It keeps JavaScript separate from HTML, lets you attach multiple handlers to the same event, and gives more control through options and `removeEventListener()`.

**Q8. What is the event object?**

**Answer:** An object passed automatically to the handler that contains details about the event, such as `type`, `target`, and `key`.

**Q9. What is the difference between `event.target` and `event.currentTarget`?**

**Answer:** `event.target` is the element that actually triggered the event, while `event.currentTarget` is the element to which the listener is attached.

**Q10. What does `preventDefault()` do?**

**Answer:** It stops the browser's default action for an event, for example preventing a form from reloading the page on submit.

**Q11. What is the difference between the `input` and `change` events?**

**Answer:** `input` fires every time the value changes (every keystroke), while `change` fires when the value is committed, for example when a text box loses focus.

**Q12. What is the difference between `keydown` and `keyup`?**

**Answer:** `keydown` fires when a key is pressed down, and `keyup` fires when the key is released.

### 🔵 Practical Questions

**Q13. What is event bubbling?**

**Answer:** When an event occurs on an element, it first runs that element's handlers and then propagates upward to its parent elements.

**Q14. How do you stop event bubbling?**

**Answer:** By calling `event.stopPropagation()` inside the handler.

**Q15. What is event delegation?**

**Answer:** Attaching a single listener to a parent element and using `event.target` to handle events from its children. It reduces the number of listeners and works for dynamically added elements.

**Q16. How do you remove an event listener?**

**Answer:** Use `removeEventListener()` with the same event name and the same function reference that was used in `addEventListener()`. Anonymous functions cannot be removed this way.

**Q17. What is wrong with this code?**

```javascript
button.addEventListener("click", sayHi());
```

**Answer:** `sayHi()` is called immediately and its return value is passed to the listener. It should be `button.addEventListener("click", sayHi);`.

**Q18. How can you make a listener run only once?**

**Answer:** Pass the option `{ once: true }` as the third argument to `addEventListener()`.

---

## 🏆 14. Key Takeaways

- 🖱️ An event is something that happens on the page; a handler is the function that responds.
- ✅ Use `addEventListener("click", handler)` instead of inline attributes.
- 🗂️ Common events include `click`, `keydown`, `input`, `submit`, and `DOMContentLoaded`.
- 📦 The event object gives details such as `event.target` and `event.key`.
- 🛑 `preventDefault()` stops default browser behaviour, like a form reload.
- 🫧 Events bubble up from child to parent; `stopPropagation()` stops this.
- 🎯 Event delegation uses one parent listener to handle many children.
- ⚠️ Pass the function itself (`sayHi`), not its result (`sayHi()`).

---

### 🚀 Keep Practising!

> 💡 **Remember:** Events are what turn a static page into a living, interactive experience.

**Happy Coding! 💻✨**
