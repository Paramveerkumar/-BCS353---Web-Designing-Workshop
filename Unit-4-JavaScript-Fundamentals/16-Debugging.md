# 🐞 JavaScript Debugging

> 🎯 **Learning Objectives**
> - Understand what a bug is and what debugging means.
> - Identify the three types of errors: syntax, runtime, and logical.
> - Read and understand common JavaScript error messages.
> - Use `console` methods and the `debugger` statement to find bugs.
> - Use browser DevTools breakpoints and step controls.
> - Handle errors with `try...catch...finally` and `throw`.
> - Follow a systematic approach to find and fix bugs.

---

## 🌟 1. What is Debugging?

A **bug** is a mistake in a program that makes it behave in an unexpected way. **Debugging** is the process of **finding and fixing** those bugs.

Think of a **doctor diagnosing a patient**. 🩺

| Doctor | Programmer |
|---|---|
| Listens to the symptoms | Reads the error message and observes the wrong output |
| Runs tests | Uses `console.log()` and breakpoints |
| Finds the cause | Locates the faulty line |
| Prescribes treatment | Fixes the code |
| Checks recovery | Tests again |

### 🧠 Remember This!

- Every programmer, beginner or expert, writes bugs. 🐛
- Debugging is a **skill** you can learn, not a sign of failure.
- The error message is your **friend**. Always read it fully.

---

## 🚦 2. Three Types of Errors

| Type | When it appears | Example |
|---|---|---|
| 🔴 **Syntax error** | Before the code runs (mistake in the grammar) | Missing bracket or quote |
| 🟠 **Runtime error** | While the code runs | Using a variable that doesn't exist |
| 🟡 **Logical error** | No error message, but the **result is wrong** | Wrong formula or condition |

### 🔴 Syntax Error

JavaScript cannot understand the code, so **nothing in that script runs**.

```javascript
console.log("Hello"
```

### 📤 Output

```text
SyntaxError: missing ) after argument list
```

### 🟠 Runtime Error

The code is valid, but something goes wrong while it runs. The program **stops at that line**.

```javascript
console.log("Start");
console.log(score);
console.log("End");
```

### 📤 Output

```text
Start
ReferenceError: score is not defined
```

`"End"` never prints because the program stopped at the error.

### 🟡 Logical Error: The Sneakiest Bug

```javascript
let a = 10;
let b = 20;

let average = a + b / 2;
console.log(average);
```

### 📤 Output

```text
20
```

There is **no error message**, but the answer should be `15`. Division runs before addition, so the code calculates `10 + (20 / 2)`. The fix is `(a + b) / 2`.

> ⚠️ Logical errors are the hardest to find because JavaScript doesn't complain. You must **notice** the wrong result.

---

## 📖 3. Reading Error Messages

```text
TypeError: Cannot read properties of null (reading 'name')
    at showUser (script.js:5:21)
    at script.js:9:1
```

### 🔍 Anatomy of an Error

| Part | Meaning |
|---|---|
| `TypeError` | The **type** of error |
| `Cannot read properties of null (reading 'name')` | The **message**: what went wrong |
| `script.js:5:21` | The **file, line, and column** where it happened |
| `at showUser ...` | The **stack trace**: the chain of function calls that led here |

💡 Start with the **first line** and the **first line number** of the stack trace.

### 🗂️ Common Error Types

| Error | Meaning | Example | Message |
|---|---|---|---|
| `SyntaxError` | Invalid code structure | `console.log("Hi"` | `missing ) after argument list` |
| `ReferenceError` | Using a variable that doesn't exist | `console.log(x);` | `x is not defined` |
| `TypeError` | Using a value in a wrong way | `let u = null; u.name;` | `Cannot read properties of null (reading 'name')` |
| `TypeError` | Changing a constant | `const n = 5; n = 6;` | `Assignment to constant variable.` |
| `TypeError` | Calling something that isn't a function | `let n = 5; n();` | `n is not a function` |
| `RangeError` | A value outside the allowed range | `new Array(-1)` | `Invalid array length` |
| `RangeError` | Infinite recursion | `function f() { f(); } f();` | `Maximum call stack size exceeded` |

---

## 🖨️ 4. Debugging with `console` Methods

### 🟢 `console.log()`: Your First Tool

The most common technique is printing values to see what is really happening.

```javascript
function sumTo(n) {
    let total = 0;

    for (let i = 1; i < n; i++) {
        total += i;
    }

    return total;
}

console.log(sumTo(5));
```

### 📤 Output

```text
10
```

Expected `15` (1+2+3+4+5), but we got `10`. Let's investigate by printing inside the loop:

```javascript
function sumTo(n) {
    let total = 0;

    for (let i = 1; i < n; i++) {
        total += i;
        console.log("i =", i, "total =", total);
    }

    return total;
}

sumTo(5);
```

### 📤 Output

```text
i = 1 total = 1
i = 2 total = 3
i = 3 total = 6
i = 4 total = 10
```

The loop **never reaches `i = 5`**. The condition `i < n` stops one step too early.

✅ **Fix:** change it to `i <= n`.

### 🏷️ Label Your Output

```javascript
let name = "Aman";
let age = 20;

console.log(name, age);
console.log({ name, age });
```

### 📤 Output

```text
Aman 20
{ name: 'Aman', age: 20 }
```

Wrapping variables in `{ }` prints their **names and values** together.

### 🧰 Other Useful Console Methods

| Method | Purpose |
|---|---|
| `console.warn("msg")` | Shows a warning (usually yellow) |
| `console.error("msg")` | Shows an error (usually red) |
| `console.table(array)` | Shows an array or object as a **table** |
| `console.time("label")` and `console.timeEnd("label")` | Measures how long code takes |
| `console.assert(condition, "msg")` | Prints a message **only if the condition is false** |

```javascript
console.assert(1 + 1 === 3, "Math is broken!");
```

### 📤 Output

```text
Assertion failed: Math is broken!
```

```javascript
const students = [
    { name: "Aman", marks: 80 },
    { name: "Priya", marks: 92 }
];

console.table(students);
```

**Expected result:** The console shows a neat table with columns `name` and `marks` and one row per student.

---

## 🛑 5. Debugging with Browser DevTools

`console.log()` is useful, but **breakpoints** let you **pause** your program and inspect everything.

### 🚀 How to Set a Breakpoint (Chrome)

1. Open the page and press **F12** (or right-click → **Inspect**).
2. Go to the **Sources** tab.
3. Open your JavaScript file from the left panel.
4. **Click a line number** to set a breakpoint (a blue marker appears).
5. Trigger the code (reload the page or click the button).
6. The program **pauses** on that line.

### 🎮 Step Controls

| Button | Shortcut | Action |
|---|---|---|
| ▶️ **Resume** | F8 | Continue until the next breakpoint |
| ⤵️ **Step over** | F10 | Run the current line and move to the next one |
| ⬇️ **Step into** | F11 | Go **inside** the function being called |
| ⬆️ **Step out** | Shift + F11 | Finish the current function and go back to the caller |

### 🔎 What You Can Inspect While Paused

| Panel | What it shows |
|---|---|
| **Scope** | Current values of all variables |
| **Watch** | Expressions you add (for example `total` or `i * 2`) and their live values |
| **Call Stack** | The chain of functions that led to this line |
| **Breakpoints** | A list of all your breakpoints (you can disable them) |

> 💡 You can also **hover over a variable** in the code while paused to see its value.

### 🔤 The `debugger` Statement

Writing `debugger;` in your code works like a built-in breakpoint.

```javascript
function calculate(a, b) {
    debugger;                  // pauses here when DevTools is open
    let result = a * b;
    return result;
}

calculate(4, 5);
```

> ⚠️ `debugger` only pauses when **DevTools is open**. Remove it before sharing your final code.

---

## 🛡️ 6. Handling Errors with `try...catch...finally`

Instead of letting an error crash the program, you can **catch** it and respond.

```javascript
try {
    console.log("Trying...");
    undefinedFunction();
    console.log("This line is skipped");
} catch (error) {
    console.log("Caught: " + error.name + ": " + error.message);
} finally {
    console.log("Finally always runs");
}

console.log("Program continues ✅");
```

### 📤 Output

```text
Trying...
Caught: ReferenceError: undefinedFunction is not defined
Finally always runs
Program continues ✅
```

### 🔍 Explanation

| Block | Purpose |
|---|---|
| `try` | Code that **might** cause an error |
| `catch (error)` | Runs **only if** an error occurs; `error` holds the details |
| `finally` | Runs **always**, whether or not there was an error (good for cleanup) |

### 🧾 The Error Object

| Property | Meaning |
|---|---|
| `error.name` | Type of error, such as `"ReferenceError"` |
| `error.message` | Description of the problem |
| `error.stack` | The stack trace as text |

### 🚨 Creating Your Own Errors with `throw`

```javascript
function divide(a, b) {
    if (b === 0) {
        throw new Error("Cannot divide by zero");
    }
    return a / b;
}

try {
    console.log(divide(10, 2));
    console.log(divide(10, 0));
} catch (error) {
    console.log("Error: " + error.message);
}
```

### 📤 Output

```text
5
Error: Cannot divide by zero
```

### ⚠️ What `try...catch` Cannot Do

- It cannot catch **syntax errors**, because the code never starts running.
- It does not catch errors that happen later inside **asynchronous callbacks** (such as inside `setTimeout`) unless the `try...catch` is inside the callback.
- It should **not hide** bugs. Catch only the errors you can actually handle.

---

## 🧭 7. A Step-by-Step Debugging Strategy

| Step | What to do |
|---|---|
| 1️⃣ **Reproduce** | Find the exact steps that make the bug appear every time |
| 2️⃣ **Read the error** | Note the error type, message, and line number |
| 3️⃣ **Isolate** | Narrow down the problem to the smallest piece of code (comment out other parts) |
| 4️⃣ **Inspect** | Use `console.log()` or breakpoints to check the actual values |
| 5️⃣ **Hypothesise** | Make a guess: "I think `i` is wrong because..." |
| 6️⃣ **Fix** | Change **one thing at a time** |
| 7️⃣ **Test** | Run again, and also test edge cases (empty input, `0`, negative numbers) |

### 🦆 Rubber Duck Debugging

Explain your code **line by line, out loud**, to a rubber duck (or a friend). Very often you spot the bug while explaining it.

---

## 🧰 8. Common Bugs and Quick Fixes

| 🐞 Bug | 🔍 Symptom | ✅ Fix |
|---|---|---|
| Typo in a variable name | `ReferenceError: x is not defined` | Check spelling and capital letters |
| Using `=` instead of `===` in a condition | The `if` block always runs | `if (x === 5)` |
| Off-by-one in loops | Last item missed, or `undefined` printed | Check `<` vs `<=` |
| String instead of number | `"5" + 3` gives `"53"` | Convert with `Number()` |
| Accessing a property of `undefined` or `null` | `TypeError: Cannot read properties of undefined` | Check the value first, or use `?.` |
| Script runs before HTML loads | `Cannot read properties of null` when using `querySelector` | Add `defer` or move the script to the end of `<body>` |
| Wrong operator precedence | Calculation gives a wrong answer | Use parentheses `( )` |
| Missing `return` | Function gives `undefined` | Add `return` |
| Wrong file path in `<script src>` | Nothing happens; 404 in the Network tab | Fix the file name or path |
| Forgot to call the function | Nothing happens | Add `()` |

---

## 🕵️ 9. Find the Bug! (Worked Examples)

### 🐞 Bug 1: The Always-True Condition

```javascript
let x = 3;

if (x = 5) {
    console.log("x is 5");
}

console.log(x);
```

### 📤 Output

```text
x is 5
5
```

**Problem:** `x = 5` **assigns** 5 to `x` and is always truthy. **Fix:** `if (x === 5)`.

### 🐞 Bug 2: The Extra `undefined`

```javascript
const arr = [10, 20, 30];

for (let i = 0; i <= arr.length; i++) {
    console.log(arr[i]);
}
```

### 📤 Output

```text
10
20
30
undefined
```

**Problem:** `<=` goes one step too far. **Fix:** `i < arr.length`.

### 🐞 Bug 3: The Wrong Total

```javascript
let price = "100";
let tax = 18;

console.log(price + tax);
```

### 📤 Output

```text
10018
```

**Problem:** `price` is a string, so `+` joins the text. **Fix:** `Number(price) + tax`, which gives `118`.

### 🐞 Bug 4: The Missing Return

```javascript
function add(a, b) {
    a + b;
}

console.log(add(2, 3));
```

### 📤 Output

```text
undefined
```

**Problem:** The function calculates the sum but never returns it. **Fix:** `return a + b;`.

---

## 🛠️ 10. Good Habits to Prevent Bugs

- 📏 Write **small functions** that do one job.
- 🏷️ Use **meaningful names** (`totalMarks`, not `tm`).
- 🧪 **Test as you go.** Don't write 100 lines before running.
- 🔒 Use `const` by default and `let` when needed, and avoid `var`.
- ⚖️ Use `===` instead of `==`.
- 🧹 Use a **linter** such as ESLint, which warns about mistakes while you type.
- 📝 Add comments for tricky logic.
- 💾 Use **version control** (Git) so you can go back to working code.

---

## 🧪 11. Practice Tasks

- [ ] 🟢 **Beginner:** Write code that causes a `ReferenceError` on purpose, then read and explain the message.
- [ ] 🟢 **Beginner:** Open DevTools and run `console.log("Hello")` in the Console tab.
- [ ] 🟡 **Intermediate:** This code should print 1 to 5 but prints 1 to 4. Find and fix the bug: `for (let i = 1; i < 5; i++) console.log(i);`
- [ ] 🟡 **Intermediate:** Use `console.table()` to display an array of three objects.
- [ ] 🔵 **Practice:** Set a breakpoint in a loop that adds numbers, and step through it, watching the `total` variable change.
- [ ] 🔵 **Practice:** Write a function `safeParse(text)` that uses `try...catch` and returns `null` if `JSON.parse(text)` fails.
- [ ] 🔴 **Challenge:** Write a `divide(a, b)` function that **throws** an error if `b` is `0`, and call it inside `try...catch`.
- [ ] 🔴 **Challenge:** Take any earlier program you wrote, deliberately introduce 3 different bugs, and ask a friend to find them.

---

## 🎤 12. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a bug?**

**Answer:** A bug is a mistake or flaw in a program that makes it behave incorrectly or unexpectedly.

**Q2. What is debugging?**

**Answer:** Debugging is the process of finding, understanding, and fixing bugs in a program.

**Q3. What are the types of errors in JavaScript?**

**Answer:** Syntax errors, runtime errors, and logical errors.

**Q4. What is a syntax error?**

**Answer:** An error caused by code that breaks the language's grammar rules, such as a missing bracket. The script does not run at all.

**Q5. How can you open the browser's developer tools?**

**Answer:** Press F12 (or Ctrl+Shift+I), or right-click the page and choose Inspect.

### 🟡 Intermediate Questions

**Q6. What is the difference between a runtime error and a logical error?**

**Answer:** A runtime error happens while the code runs and stops the program with an error message. A logical error produces no error message, but the program gives wrong results.

**Q7. Which type of error is the hardest to find, and why?**

**Answer:** Logical errors, because JavaScript does not report them. The program runs normally but gives incorrect output.

**Q8. What do `ReferenceError` and `TypeError` mean?**

**Answer:** A `ReferenceError` occurs when you use a variable that does not exist. A `TypeError` occurs when a value is used in a way its type does not allow, such as reading a property of `null` or calling a non-function.

**Q9. What is a stack trace?**

**Answer:** A list of the function calls that led to an error, showing the file names and line numbers, with the most recent call first.

**Q10. What is a breakpoint?**

**Answer:** A marker on a line of code that pauses execution there, so you can inspect variables and step through the code.

**Q11. What is the difference between Step Over and Step Into?**

**Answer:** Step Over runs the current line (including any function call on it) and moves to the next line. Step Into enters the function being called on that line.

**Q12. What is the `debugger` statement?**

**Answer:** A statement that acts as a breakpoint in the code, pausing execution when the developer tools are open.

### 🔵 Practical Questions

**Q13. What are the purposes of `try`, `catch`, and `finally`?**

**Answer:** `try` holds code that might fail, `catch` handles the error if one occurs, and `finally` runs regardless of whether an error occurred.

**Q14. How do you create your own error?**

**Answer:** Using the `throw` statement, for example `throw new Error("Something went wrong");`.

**Q15. What is the output of the following code?**

```javascript
try {
    console.log("A");
    undefinedFunction();
    console.log("B");
} catch (e) {
    console.log("C");
} finally {
    console.log("D");
}
```

**Answer:** `A`, `C`, `D` on separate lines. `B` is skipped because the error occurs first.

**Q16. Can `try...catch` catch a syntax error?**

**Answer:** No. Syntax errors are detected before the code runs, so the script never starts and no `try...catch` can handle them.

**Q17. How would you find why `sumTo(5)` returns `10` instead of `15`?**

**Answer:** Add `console.log` inside the loop (or set a breakpoint) to print `i` and `total` on each iteration. You would see that the loop stops before reaching `5`, which shows the condition `i < n` should be `i <= n`.

**Q18. What is `console.table()` used for?**

**Answer:** It displays arrays or objects in the console as a readable table.

---

## 🏆 13. Key Takeaways

- 🐞 Debugging is finding and fixing bugs, and every programmer does it.
- 🚦 There are three error types: **syntax** (code won't run), **runtime** (crashes while running), and **logical** (wrong result, no error).
- 📖 Read error messages carefully: the type, the message, and the line number.
- 🖨️ `console.log()`, `console.table()`, and `console.assert()` help you see what is really happening.
- 🛑 Breakpoints and step controls in DevTools let you pause and inspect your code.
- 🛡️ Use `try...catch...finally` and `throw` to handle errors gracefully.
- 🧭 Follow a method: reproduce, isolate, inspect, hypothesise, fix, and test.
- 🦆 Explaining your code aloud often reveals the bug.

---

### 🚀 Keep Practising!

> 💡 **Remember:** A bug is not a failure. It is a puzzle, and solving it makes you a better programmer.

**Happy Coding! 💻✨**
