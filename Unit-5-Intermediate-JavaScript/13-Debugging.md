# 🐞 Debugging in JavaScript

## 📌 What is Debugging?

**Debugging** is the process of finding, understanding, and fixing errors (bugs) in a program.

In simple words, debugging means identifying **why your code is not working as expected and correcting the problem.**

💡 Example: If your calculator shows `25` instead of `15`, debugging helps you discover what went wrong.

---

## 🎯 1. Why Is Debugging Important?

- 🐛 Find and fix programming errors.
- 🔍 Understand unexpected program behavior.
- ✅ Improve code reliability.
- 🛠️ Make programs easier to maintain.
- 🚀 Save time during development.

---

## ⚠️ 2. Types of Errors in JavaScript

JavaScript errors are commonly explained using three categories.

### 1️⃣ Syntax Error

A syntax error occurs when code violates JavaScript's grammatical rules.

❌ Incorrect code:

```javascript
console.log("Hello Students!"
```

The closing parenthesis is missing.

✅ Correct code:

```javascript
console.log("Hello Students!");
```

**Output:**

```text
Hello Students!
```

### 2️⃣ Runtime Error

A runtime error occurs while the program is executing.

```javascript
let student = null;

console.log(student.name);
```

**Result:** A `TypeError` occurs because we are trying to access `name` on `null`.

✅ Correct code:

```javascript
let student = null;

if (student !== null) {
    console.log(student.name);
} else {
    console.log("Student details are unavailable.");
}
```

**Output:**

```text
Student details are unavailable.
```

### 3️⃣ Logical Error

A logical error occurs when the program runs but produces an incorrect result.

❌ Incorrect code:

```javascript
let length = 5;
let width = 3;

let area = length + width;

console.log(area);
```

**Output:**

```text
8
```

The code executes, but the formula for the area of a rectangle is incorrect.

✅ Correct code:

```javascript
let length = 5;
let width = 3;

let area = length * width;

console.log(area);
```

**Output:**

```text
15
```

💡 **Remember:** Logical errors are often harder to find because JavaScript may not display any error message.

---

## 🖥️ 3. Using `console.log()` for Debugging

The easiest way to debug JavaScript is to print variable values and check the program's execution.

```javascript
let price = 100;
let quantity = 3;

console.log("Price:", price);
console.log("Quantity:", quantity);

let total = price * quantity;

console.log("Total:", total);
```

**Output:**

```text
Price: 100
Quantity: 3
Total: 300
```

### 🔍 Why is this useful?

Suppose the total is incorrect. Printing `price` and `quantity` helps you check whether the input values are correct before investigating the calculation.

---

## 🧰 4. Useful Console Methods

JavaScript provides several console methods that help with debugging.

| Method | Purpose | Example |
|---|---|---|
| `console.log()` | Display general information | `console.log(total)` |
| `console.error()` | Display an error message | `console.error("Failed!")` |
| `console.warn()` | Display a warning | `console.warn("Check input")` |
| `console.table()` | Display tabular data | `console.table(students)` |
| `console.assert()` | Report a failed assertion | `console.assert(age >= 18, "Underage")` |
| `console.trace()` | Display a stack trace | `console.trace("Trace here")` |

### Example: `console.table()`

```javascript
const students = [
    { name: "Aman", marks: 85 },
    { name: "Priya", marks: 92 },
    { name: "Rahul", marks: 78 }
];

console.table(students);
```

This displays the student records in a table in developer consoles that support tabular output.

---

## 🔎 5. Debugging Using Browser Developer Tools

Modern browsers such as Chrome and Firefox provide built-in developer tools.

<box gap={3}>
  <row align="start" gap={3}>
    <AsyncImage query="Chrome DevTools Console panel JavaScript errors screenshot" aspectRatio="4:3" width="124px"/>
    <box flex="1" gap={1}>
      **1. Console**

      <text color="secondary" size="sm">Displays logs, warnings, exceptions, and error messages.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="start" gap={3}>
    <AsyncImage query="Chrome DevTools Sources JavaScript debugger breakpoints screenshot" aspectRatio="4:3" width="124px"/>
    <box flex="1" gap={1}>
      **2. Sources / Debugger**

      <text color="secondary" size="sm">Set breakpoints, pause execution, and inspect variable values.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="start" gap={3}>
    <AsyncImage query="Chrome browser developer tools Network panel screenshot" aspectRatio="4:3" width="124px"/>
    <box flex="1" gap={1}>
      **3. Network**

      <text color="secondary" size="sm">Investigate failed API requests, missing files, and HTTP errors.</text>
    </box>
  </row>
</box>

### How to Open Developer Tools

1. Open your webpage in Chrome.
2. Right-click the page and select **Inspect**.
3. Open the **Console** tab to check errors.
4. Open **Sources** to set breakpoints.
5. Reload the page and inspect the execution.

Keyboard shortcuts on Windows/Linux: `F12` or `Ctrl + Shift + J` opens the Console in Chrome.

On macOS: `Option + Command + J` opens the Console in Chrome.

---

## ⏸️ 6. What Is a Breakpoint?

A **breakpoint** pauses program execution at a selected line so that you can inspect the current state of the program.

Consider this code:

```javascript
function calculateTotal(price, quantity) {
    let total = price * quantity;
    return total;
}

let result = calculateTotal(100, 3);
console.log(result);
```

Set a breakpoint on:

```javascript
let total = price * quantity;
```

When execution pauses, inspect:

- `price` → `100`
- `quantity` → `3`
- `total` → not yet assigned on the first pause at this line

You can then step over the line and inspect `total`, which becomes `300`.

### Common Debugger Controls

- ▶️ **Resume:** Continue execution.
- ⏭️ **Step over:** Execute the current line without entering a called function.
- ↘️ **Step into:** Enter a function call.
- ↗️ **Step out:** Finish the current function and return to its caller.

---

## 🧪 7. Practical Debugging Example

Suppose we want to calculate the average marks of three subjects.

❌ Incorrect code:

```javascript
function calculateAverage(a, b, c) {
    let average = a + b + c / 3;
    return average;
}

console.log(calculateAverage(60, 70, 80));
```

**Output:**

```text
156.66666666666666
```

### 🔍 Find the Bug

The division operator has higher precedence than addition. Therefore, JavaScript evaluates:

```javascript
60 + 70 + (80 / 3)
```

Instead of dividing the total marks by three.

✅ Correct code:

```javascript
function calculateAverage(a, b, c) {
    let average = (a + b + c) / 3;
    return average;
}

console.log(calculateAverage(60, 70, 80));
```

**Output:**

```text
70
```

💡 Debugging involves checking both the values and the logic used to process them.

---

## 🪜 8. Step-by-Step Debugging Process

<box border radius="lg" padding={3} gap={3}>
  <row align="center" gap={3}>
    <icon name="search" size="xl" color="secondary"/>
    <box flex="1" gap={1}>
      **Step 1: Reproduce the problem**

      <text color="secondary" size="sm">Run the program and identify the unexpected behavior.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <icon name="message-square-warning" size="xl" color="secondary"/>
    <box flex="1" gap={1}>
      **Step 2: Read the error**

      <text color="secondary" size="sm">Check the error message, file name, and line number.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <icon name="bug" size="xl" color="secondary"/>
    <box flex="1" gap={1}>
      **Step 3: Locate the cause**

      <text color="secondary" size="sm">Inspect variables, conditions, and function calls.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <icon name="wrench" size="xl" color="secondary"/>
    <box flex="1" gap={1}>
      **Step 4: Fix the issue**

      <text color="secondary" size="sm">Correct the root cause rather than hiding the symptom.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <icon name="check-circle" size="xl" color="secondary"/>
    <box flex="1" gap={1}>
      **Step 5: Test again**

      <text color="secondary" size="sm">Confirm the fix and check that existing functionality still works.</text>
    </box>
  </row>
</box>

---

## ⚖️ 9. Debugging vs. Testing

| Debugging | Testing |
|---|---|
| Finds and investigates the cause of a problem | Checks whether software behaves as expected |
| Helps identify and fix defects | Helps reveal defects |
| Often starts after unexpected behavior is observed | Can happen before or after a defect is discovered |
| Uses logs, breakpoints, and code inspection | Uses test cases, assertions, and automated tools |

Both activities are important for reliable software.

---

## 🎤 10. Viva Questions

**Q1. What is debugging?**

Debugging is the process of identifying, analyzing, and fixing defects in a program.

**Q2. What are the three commonly discussed types of programming errors?**

Syntax errors, runtime errors, and logical errors.

**Q3. What is a breakpoint?**

A breakpoint pauses execution at a selected location to help inspect the program.

**Q4. What is the use of `console.log()`?**

It displays values and messages that help developers understand program execution.

**Q5. What is the difference between a syntax error and a logical error?**

A syntax error violates language rules, while a logical error produces an incorrect result despite executing.

**Q6. What are browser Developer Tools?**

They are built-in tools for inspecting webpages, debugging JavaScript, analyzing network requests, and diagnosing performance issues.

**Q7. What is step-by-step debugging?**

It means executing a program one line at a time while inspecting its state.

**Q8. What is the difference between Step Into and Step Over?**

Step Into enters a function call; Step Over executes the call without entering its body.

**Q9. Can a program contain bugs without displaying an error?**

Yes. Logical errors can cause incorrect results without generating an exception.

**Q10. What should you do after fixing a bug?**

Run the relevant tests again and verify that the fix works without breaking existing functionality.

---

## 🧠 Quick Revision

- 🐞 Debugging means finding and fixing defects.
- ⚠️ Syntax errors concern language rules.
- 💥 Runtime errors occur during execution.
- 🧮 Logical errors produce incorrect results.
- 🖥️ `console.log()` helps inspect values.
- ⏸️ Breakpoints allow step-by-step investigation.
- ✅ Always test your code after making a fix.

✨ **Exam definition:** Debugging is the systematic process of locating, analyzing, and correcting errors in a program to make it behave as intended.
