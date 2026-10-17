# 📝 JavaScript Statements (Intermediate)

> 📌 **Note:** This is the **intermediate** lesson. The beginner lesson (`Statement.md`) covers what a statement is, semicolons, and blocks. The *JS Expressions* lesson covers the expression-vs-statement distinction in detail. Here we go deeper into scope, hoisting, automatic semicolon insertion, control flow, jump statements, and exception handling.

> 🎯 **Learning Objectives**
> - Classify all the statement types in JavaScript.
> - Understand block scope, shadowing, hoisting, and the temporal dead zone.
> - Understand Automatic Semicolon Insertion (ASI) and the bugs it can cause.
> - Use `while`, `do...while`, `for...of`, labeled `break`/`continue`, and know their pitfalls.
> - Understand `return`, `throw`, and the behaviour of `try...catch...finally`.
> - Use strict mode and know where a directive must appear.
> - Write clean, flat control flow using guard clauses.

---

## 🌟 1. A Map of JavaScript Statements

A JavaScript program is a list of **statements**. Each statement is an instruction that is executed for its effect.

| Category | Statements | Purpose |
|---|---|---|
| 📦 **Declarations** | `var`, `let`, `const`, `function`, `async function`, `function*`, `class`, `import`, `export` | Create names, values, and module connections |
| 🧮 **Expression statements** | `count++;`, `console.log(x);`, `x = 5;` | Run an expression for its side effect |
| 🔀 **Conditional** | `if...else`, `switch` | Choose which code runs |
| 🔁 **Loops** | `for`, `while`, `do...while`, `for...in`, `for...of`, `for await...of` | Repeat code |
| 🛑 **Jump** | `break`, `continue`, `return`, `throw` | Change the normal flow |
| 🛡️ **Error handling** | `try...catch...finally` | Handle runtime errors |
| 🧱 **Block** | `{ ... }` | Group statements and create a scope |
| ⬜ **Empty** | `;` | Does nothing |
| 🏷️ **Labeled** | `name: statement` | Give a statement a name for `break` or `continue` |
| 🐞 **Debugger** | `debugger;` | Triggers a breakpoint when DevTools is open |
| 🚫 **`with`** | `with (obj) { ... }` | Deprecated and **forbidden in strict mode**. Never use it |

### 🧠 Remember This!

- Statements are executed **in order**, from top to bottom, unless a control-flow or jump statement changes the order.
- A statement that **declares** something (`let`, `class`, `function`) behaves differently from one that **does** something (`if`, `for`).

### 💡 Did You Know?

Statements technically have a hidden *completion value*. In the browser console, typing `if (true) 42` shows `42`. You cannot use this value in your code, which is the practical difference between statements and expressions.

---

## 🧱 2. Blocks, Scope, and Shadowing

A **block** `{ ... }` groups statements. `let`, `const`, and `class` are **block-scoped**. `var` is **function-scoped** and ignores blocks.

```javascript
{
    let a = 1;
    const b = 2;
    var c = 3;
}

console.log(typeof a);
console.log(typeof b);
console.log(c);
```

### 📤 Output

```text
undefined
undefined
3
```

(`typeof` is used for `a` and `b` because reading an undeclared name directly would throw a `ReferenceError`.)

### 🌓 Shadowing

An inner block can declare a variable with the **same name** as an outer one. The inner one **shadows** it.

```javascript
let n = 1;

{
    let n = 2;
    console.log(n);
}

console.log(n);
```

### 📤 Output

```text
2
1
```

### 🪤 `var` Cannot Shadow a `let` in the Same Scope

```javascript
let value = 1;

{
    var value = 2;   // ❌ SyntaxError
}
```

### 📤 Output

```text
SyntaxError: Identifier 'value' has already been declared
```

`var` is hoisted to the **enclosing function or global scope**, where `let value` already lives, so the two collide.

### 🪤 A Declaration Cannot Be the Body of an `if` or Loop

```javascript
if (true) let x = 1;   // ❌ SyntaxError
```

### 📤 Output

```text
SyntaxError: Lexical declaration cannot appear in a single-statement context
```

Wrap the declaration in a block: `if (true) { let x = 1; }`.

---

## 🪝 3. Hoisting and the Temporal Dead Zone

Declarations are processed **before** any code runs. What you can do with a name **before** its line depends on how it was declared.

| Declaration | Hoisted? | Usable before its line? |
|---|---|---|
| `function f() {}` | ✅ Fully | ✅ Yes, you can call it |
| `var x` | ✅ Declaration only (value is `undefined`) | ⚠️ Gives `undefined` |
| `let`, `const` | ✅ Declared but **uninitialised** | ❌ `ReferenceError` (the **temporal dead zone**) |
| `class` | ✅ Declared but **uninitialised** | ❌ `ReferenceError` |
| Function **expression** (`const f = function(){}`) | Follows `var`/`let`/`const` rules | Depends on the keyword |

```javascript
console.log(a);
var a = 1;

hoisted();
function hoisted() {
    console.log("function declarations work early");
}
```

### 📤 Output

```text
undefined
function declarations work early
```

```javascript
console.log(typeof b);
let b = 2;
```

### 📤 Output

```text
ReferenceError: Cannot access 'b' before initialization
```

```javascript
const pet = new Dog();
class Dog {}
```

### 📤 Output

```text
ReferenceError: Cannot access 'Dog' before initialization
```

### 🔍 Explanation

- The **temporal dead zone (TDZ)** is the time between the start of the scope and the line where a `let`, `const`, or `class` is initialised.
- Even `typeof` throws inside the TDZ, unlike `typeof` on a completely undeclared name.
- ✅ **Best practice:** declare variables at the top of their scope, and use `const` by default.

---

## ✂️ 4. Automatic Semicolon Insertion (ASI)

JavaScript inserts a semicolon for you in certain situations. This usually works, but it fails in **three well-known cases**.

### ✅ When ASI Inserts a Semicolon

1. When a token **cannot legally continue** the statement and there is a **line break** before it.
2. Before a closing `}`.
3. At the end of the file.

```javascript
let a = 1
let b = 2
console.log(a + b)
```

### 📤 Output

```text
3
```

### 🪤 Trap 1: A Line Break After `return` (Restricted Productions)

```javascript
function getUser() {
    return
    { name: "Aman" };
}

console.log(getUser());
```

### 📤 Output

```text
undefined
```

JavaScript inserts a semicolon right after `return`, so the object is never returned. The same restriction applies to `break`, `continue`, `throw`, and postfix `++`/`--`. **Keep the value on the same line as `return`.**

### 🪤 Trap 2: A Line Starting with `(`

```javascript
const count = 5
(function () {
    console.log("IIFE");
})()
```

### 📤 Output

```text
TypeError: 5 is not a function
```

No semicolon is inserted, because `5(function () { ... })` is *valid* syntax. It tries to call `5` as a function.

### 🪤 Trap 3: A Line Starting with `[`

```javascript
let total = 10
[1, 2].forEach((n) => console.log(n))
```

### 📤 Output

```text
TypeError: Cannot read properties of undefined (reading 'forEach')
```

This is parsed as `10[1, 2].forEach(...)`. The expression `10[1, 2]` reads property `2` of the number `10`, which is `undefined`.

### 🛡️ How to Stay Safe

| Strategy | Detail |
|---|---|
| ✅ **Always write semicolons** | The simplest and most common rule |
| ✅ Keep `return`, `throw`, `break`, `continue` values on the same line | Avoids restricted productions |
| ✅ If you skip semicolons, start risky lines with `;` | For example `;[1, 2].forEach(...)` and `;(function () {})()` |
| ✅ Use a formatter and linter | Prettier and ESLint catch these cases |

---

## 🔀 5. Conditional Statements: Intermediate Details

### 🧩 `if` with Truthy and Falsy Values

```javascript
const items = [];
const name = "";

if (items.length) {
    console.log("has items");
} else {
    console.log("empty cart");
}

if (name) {
    console.log("has name");
} else {
    console.log("no name");
}
```

### 📤 Output

```text
empty cart
no name
```

### 🛡️ Guard Clauses: Flat Code Instead of Deep Nesting

**Deeply nested (hard to read):**

```javascript
function discount(user) {
    if (user) {
        if (user.isActive) {
            if (user.orders > 10) {
                return 0.2;
            }
            return 0.1;
        }
    }
    return 0;
}
```

**Guard clauses (clear and flat):**

```javascript
function discount(user) {
    if (!user) return 0;
    if (!user.isActive) return 0;
    if (user.orders > 10) return 0.2;
    return 0.1;
}

console.log(discount(null));
console.log(discount({ isActive: true, orders: 3 }));
console.log(discount({ isActive: true, orders: 25 }));
```

### 📤 Output

```text
0
0.1
0.2
```

Handle the **failure cases first** and return early, so the main logic stays at the lowest indentation level.

### 🔁 `switch`: Fall-Through and Scope

```javascript
switch (2) {
    case 1:
        console.log("a");
    case 2:
        console.log("b");
    case 3:
        console.log("c");
        break;
    default:
        console.log("d");
}
```

### 📤 Output

```text
b
c
```

After matching `case 2`, execution **falls through** into `case 3` until `break`. Remember that all cases share **one scope**, so wrap a case in `{ }` when it declares a `let` or `const`.

---

## 🔁 6. Loop Statements: Intermediate Details

### 🔂 `while` and `do...while`

| Loop | Condition is checked | Runs at least once? |
|---|---|---|
| `while` | **Before** each iteration | ❌ No |
| `do...while` | **After** each iteration | ✅ **Yes** |

```javascript
let n = 10;

while (n < 5) {
    console.log("while runs");
}

do {
    console.log("do...while runs once");
    n++;
} while (n < 5);

console.log(n);
```

### 📤 Output

```text
do...while runs once
11
```

### 🪤 `continue` in a `while` Loop Can Cause an Infinite Loop

```javascript
let i = 0;

while (i < 5) {
    if (i === 2) {
        continue;      // ❌ skips i++ below, and i stays 2 forever
    }
    console.log(i);
    i++;
}
```

In a `for` loop, `continue` still runs the **update** part (`i++`). In a `while` loop, the update is part of the body, so `continue` can skip it. Update the counter **before** `continue`, or use a `for` loop.

### 🔁 `for...of`: Works with Any Iterable

```javascript
for (const ch of "Hi") console.log(ch);

for (const [i, v] of ["a", "b"].entries()) console.log(i, v);

for (const [key, value] of new Map([["x", 1], ["y", 2]])) console.log(key, value);

for (const v of new Set([1, 1, 2])) console.log(v);
```

### 📤 Output

```text
H
i
0 a
1 b
x 1
y 2
1
2
```

### 🔍 `for...of` and Unicode

```javascript
const emoji = "😀";

console.log(emoji.length);
console.log([...emoji].length);

for (const ch of emoji) {
    console.log(ch);
}
```

### 📤 Output

```text
2
1
😀
```

`for...of` iterates over **code points**, so it handles emoji correctly, whereas indexing with `emoji[0]` splits the character into two broken halves.

### 🆚 `for...in` vs `for...of`

| `for...in` | `for...of` |
|---|---|
| Keys (property names, as strings) | Values |
| Includes inherited enumerable properties | Uses the object's iterator |
| For plain objects | For arrays, strings, `Map`, `Set`, and generators |

### ⏳ `for await...of`

Iterates over an **async** iterable (such as a stream or async generator) and waits for each value. It can only be used inside an `async` function or at the top level of a module.

```javascript
async function* countdown() {
    yield 3;
    yield 2;
    yield 1;
}

async function main() {
    for await (const n of countdown()) {
        console.log(n);
    }
}

main();
```

### 📤 Output

```text
3
2
1
```

---

## 🛑 7. Jump Statements

### 🏷️ Labeled `break` and `continue`

A **label** lets you break out of, or continue, an **outer** loop from inside a nested loop.

```javascript
const grid = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

let found = null;

search: for (let r = 0; r < grid.length; r++) {
    for (let c = 0; c < grid[r].length; c++) {
        if (grid[r][c] === 5) {
            found = [r, c];
            break search;
        }
    }
}

console.log(found);
```

### 📤 Output

```text
[ 1, 1 ]
```

```javascript
outer: for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 3; j++) {
        if (j === 2) {
            continue outer;
        }
        console.log(i, j);
    }
}
```

### 📤 Output

```text
1 1
2 1
3 1
```

| Statement | Effect |
|---|---|
| `break` | Exits the **innermost** loop (or `switch`) |
| `break label` | Exits the loop (or block) with that label |
| `continue` | Skips to the next iteration of the **innermost** loop |
| `continue label` | Skips to the next iteration of the **labeled** loop |

> 💡 Labels are rarely needed. If you use many of them, consider moving the loop into a function and using `return`.

### 🔙 `return`

`return` ends the **function** (not just the loop) and sends back a value. A bare `return;` gives back `undefined`.

### 🪤 `return` and `break` Inside `forEach`

```javascript
[1, 2, 3].forEach((n) => {
    if (n === 2) return;
    console.log(n);
});

// [1, 2, 3].forEach((n) => { if (n === 2) break; });   // ❌ SyntaxError: Illegal break statement
```

### 📤 Output

```text
1
3
```

The `return` only ends the **callback** for that element, so it behaves like `continue`. You cannot `break` out of `forEach`. To stop early, use a `for...of` loop, or the `some()`/`every()` methods.

---

## 🛡️ 8. `try...catch...finally` in Depth

### 🔄 How the Flow Works

```text
try block runs
  ├── no error ──────────────► skip catch ──► finally runs ──► continue
  └── error thrown ──► catch runs ──► finally runs ──► continue
```

### 🧹 `finally` Always Runs

```javascript
function f() {
    try {
        return "try";
    } finally {
        console.log("cleanup");
    }
}

console.log(f());
```

### 📤 Output

```text
cleanup
try
```

The `finally` block runs **before** the function actually returns.

### 🪤 `return` in `finally` Overrides Everything

```javascript
function g() {
    try {
        return 1;
    } finally {
        return 2;
    }
}

console.log(g());
```

### 📤 Output

```text
2
```

A `return` (or `throw`) inside `finally` **replaces** the earlier result and can even swallow an error. Avoid it.

### 🕳️ Optional Catch Binding

```javascript
try {
    JSON.parse("{");
} catch {
    console.log("Invalid JSON");
}
```

### 📤 Output

```text
Invalid JSON
```

If you don't need the error object, you can omit `(error)` (ES2019).

### 🧱 Custom Errors and Re-throwing

```javascript
class ValidationError extends Error {
    constructor(message) {
        super(message);
        this.name = "ValidationError";
    }
}

function validate(age) {
    if (age === undefined) {
        throw new ValidationError("Age is required");
    }
    return age;
}

try {
    validate();
} catch (e) {
    console.log(e.name, "-", e.message);
    console.log(e instanceof ValidationError, e instanceof Error);
}
```

### 📤 Output

```text
ValidationError - Age is required
true true
```

### 🔁 Handle Only the Errors You Understand

```javascript
try {
    validate();
} catch (e) {
    if (!(e instanceof ValidationError)) {
        throw e;                 // not ours, so pass it on
    }
    console.log("Please fix the input");
}
```

### 📤 Output

```text
Please fix the input
```

### 🔗 Adding Context with `cause` (ES2022)

```javascript
try {
    try {
        JSON.parse("{");
    } catch (err) {
        throw new Error("Could not load settings", { cause: err });
    }
} catch (e) {
    console.log(e.message);
    console.log(e.cause.name);
}
```

### 📤 Output

```text
Could not load settings
SyntaxError
```

### ⚠️ What `try...catch` Cannot Do

- It cannot catch **syntax errors** in the same script (the code never starts running).
- It does not catch errors thrown **later** inside asynchronous callbacks (like `setTimeout`) unless the `try...catch` is inside that callback. With `async/await`, `await` inside a `try` **does** let you catch rejections.
- `throw` can throw **any value**, but always throw `Error` objects, because they carry a stack trace.

---

## 🔒 9. Strict Mode: A Statement-Level Directive

`"use strict";` is a **directive**. It must be the **first statement** of a script or function to take effect.

```javascript
"use strict";

function show() {
    return this;
}

console.log(show());

undeclaredVariable = 5;
```

### 📤 Output

```text
undefined
ReferenceError: undeclaredVariable is not defined
```

### 🔍 What Strict Mode Changes

| Behaviour | Sloppy mode | Strict mode |
|---|---|---|
| Assigning to an undeclared variable | Creates a **global** | `ReferenceError` |
| `this` in a plain function call | The global object | `undefined` |
| Assigning to a read-only property | Silently ignored | `TypeError` |
| Duplicate parameter names | Allowed | `SyntaxError` |
| The `with` statement | Allowed | `SyntaxError` |

```javascript
console.log("first");
"use strict";   // ❌ not first, so it is just a useless string
```

> 💡 **ES modules** (`<script type="module">`) and the bodies of **classes** are **always strict**, so you rarely need to write the directive in modern code.

---

## 🚧 10. Statements That Cannot Start an Expression Statement

Some words at the **start** of a statement are always read as a **statement**, never as an expression. That is why these tricks need parentheses:

| You write | JavaScript reads it as | Fix |
|---|---|---|
| `function () {}()` | A function **declaration** (needs a name) | `(function () {})()` |
| `{ a: 1 }.a` | A **block** with a label | `({ a: 1 }).a` |
| `class {}` | A class declaration (needs a name) | `(class {})` |

```javascript
{ a: 1, b: 2 }
```

### 📤 Output

```text
SyntaxError: Unexpected token ':'
```

JavaScript reads `{ ... }` at the start of a statement as a block, and `a: 1, b: 2` as a label followed by an invalid expression.

---

## 🧰 11. Mini Examples

### 📦 Safe Batch Processing: `continue`, `throw`, and `finally` Together

```javascript
const inputs = ["10", "abc", "20", "", "30"];

let total = 0;
let errors = 0;
let processed = 0;

for (const raw of inputs) {
    try {
        if (raw === "") {
            continue;
        }

        const n = Number(raw);

        if (Number.isNaN(n)) {
            throw new Error(`Invalid number: ${raw}`);
        }

        total += n;
    } catch (err) {
        errors++;
        console.log(err.message);
    } finally {
        processed++;
    }
}

console.log({ total, errors, processed });
```

### 📤 Output

```text
Invalid number: abc
{ total: 60, errors: 1, processed: 5 }
```

### 🔍 What Happens?

- `""` triggers `continue`, but the `finally` block **still runs**, so `processed` counts all 5 items.
- `"abc"` triggers `throw`, which is caught by `catch`.
- A single bad item does not stop the whole loop.

---

## 🎯 12. Predict the Output

```javascript
// 1
for (var i = 0; i < 3; i++) {}
console.log(i);

// 2
function f() {
    try { return "A"; } finally { console.log("B"); }
}
console.log(f());

// 3
[1, 2, 3].forEach((n) => {
    if (n === 2) return;
    console.log(n);
});

// 4
let k = 0;
do { k++; } while (k < 0);
console.log(k);

// 5
outer: for (let i = 0; i < 3; i++) {
    for (let j = 0; j < 3; j++) {
        if (j === 1) continue outer;
        if (i === 2) break outer;
        console.log(i, j);
    }
}

// 6
switch (2) {
    case 1: console.log("a");
    case 2: console.log("b");
    case 3: console.log("c"); break;
    default: console.log("d");
}
```

### ✅ Solution

| # | Output | Reason |
|---|---|---|
| 1 | `3` | `var` is function-scoped, so `i` survives the loop and ends at `3` |
| 2 | `B` then `A` | `finally` runs before the function returns |
| 3 | `1` then `3` | `return` inside `forEach` skips only that callback |
| 4 | `1` | `do...while` runs the body once before checking |
| 5 | `0 0` then `1 0` | `j === 1` moves to the next `i`. At `i === 2`, `break outer` ends everything |
| 6 | `b` then `c` | Fall-through from `case 2` into `case 3` until `break` |

---

## ⚠️ 13. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Putting the `return` value on the next line | Keep it on the same line as `return` |
| Starting a line with `(` or `[` without a semicolon before it | End the previous line with `;` |
| Using a variable before its `let`, `const`, or `class` line | Declare first (temporal dead zone) |
| Declaring a `let` or `const` as the direct body of an `if` | Use a block: `if (x) { let y = 1; }` |
| Using `continue` in a `while` loop without updating the counter | Update the counter first, or use a `for` loop |
| Expecting `return` inside `forEach` to stop the loop | Use `for...of`, `some()`, or `every()` |
| Putting `return` or `throw` inside `finally` | Keep `finally` for cleanup only |
| Throwing strings or plain objects | `throw new Error("message")` |
| Catching every error and ignoring it | Catch only what you can handle, and re-throw the rest |
| Declaring the same `let` in two `case` clauses | Wrap each case in `{ }` |
| Writing `"use strict"` after other statements | It must be the **first** statement |
| Using labels everywhere | Prefer a function with an early `return` |

---

## 🧪 14. Practice Tasks

- [ ] 🟢 **Beginner:** Write a block that declares `let`, `const`, and `var`, then show which ones are visible outside the block.
- [ ] 🟢 **Beginner:** Write a `do...while` loop that asks (simulated with a counter) until a value is `3`, and show that it runs at least once.
- [ ] 🟡 **Intermediate:** Rewrite a three-level nested `if` function using guard clauses.
- [ ] 🟡 **Intermediate:** Cause the temporal dead zone error with `let`, and the equivalent error with `class`. Explain both messages.
- [ ] 🟡 **Intermediate:** Write a function with a `return` followed by a line break, and explain why it returns `undefined`.
- [ ] 🔵 **Practice:** Search a 2D array for a value using a labeled `break`, then rewrite it using a function with `return`.
- [ ] 🔵 **Practice:** Loop over a `Map`, a `Set`, and a string using `for...of`.
- [ ] 🔵 **Practice:** Write a function whose `try` returns a value and whose `finally` logs a message. Predict the order, then verify.
- [ ] 🔴 **Challenge:** Create a custom `ValidationError` class, and write `parseAge(text)` that throws it for invalid input. Handle it so that only `ValidationError` is caught, and anything else is re-thrown.
- [ ] 🔴 **Challenge:** Process an array of strings so that blank entries are skipped with `continue`, bad entries are logged with `throw`/`catch`, and a `finally` block counts how many entries were handled.
- [ ] 🔴 **Challenge:** Explain, line by line, why `const a = 1` followed by a line starting with `(` throws `TypeError: 1 is not a function`.

---

## 🎤 15. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What are the main categories of statements in JavaScript?**

**Answer:** Declarations (`var`, `let`, `const`, `function`, `class`), expression statements, conditionals (`if`, `switch`), loops (`for`, `while`, `do...while`, `for...in`, `for...of`), jump statements (`break`, `continue`, `return`, `throw`), `try...catch...finally`, blocks, and empty statements.

**Q2. What is a block statement and why is it important?**

**Answer:** A block `{ ... }` groups several statements into one. It also creates a scope for `let`, `const`, and `class` declarations.

**Q3. What is the difference between `while` and `do...while`?**

**Answer:** `while` checks the condition before each iteration and may never run. `do...while` checks it after each iteration, so the body always runs at least once.

**Q4. What does `break` do compared to `continue`?**

**Answer:** `break` exits the innermost loop or `switch`. `continue` skips the rest of the current iteration and moves on to the next one.

**Q5. What is the `finally` block used for?**

**Answer:** Code that must run whether or not an error occurred, such as cleanup. It runs after `try` and `catch`, even when `return`, `break`, or `continue` is used.

### 🟡 Intermediate Questions

**Q6. What is the temporal dead zone?**

**Answer:** The period between the start of a scope and the line where a `let`, `const`, or `class` is initialised. Accessing the name in that period throws a `ReferenceError`.

**Q7. How does hoisting differ between `var`, `let`, and function declarations?**

**Answer:** `var` is hoisted and initialised to `undefined`. `let`, `const`, and `class` are hoisted but remain uninitialised (the temporal dead zone). Function declarations are hoisted completely and can be called before their definition.

**Q8. What is Automatic Semicolon Insertion?**

**Answer:** A feature where the parser inserts semicolons when a token cannot continue a statement after a line break, before `}`, and at the end of the file. It also applies to restricted productions such as `return`, `break`, `continue`, `throw`, and postfix `++`/`--`.

**Q9. Why does `return` followed by a line break return `undefined`?**

**Answer:** `return` is a restricted production, so a semicolon is inserted immediately after it when a line break follows. The value on the next line is never returned.

**Q10. Why can a line starting with `(` or `[` cause bugs when the previous line has no semicolon?**

**Answer:** ASI does not insert a semicolon if the next token can legally continue the previous expression. For example, `5` followed by `(function(){})()` is parsed as the call `5(function(){})()`, causing a `TypeError`.

**Q11. What is a labeled statement, and when would you use it?**

**Answer:** A statement prefixed by a name (`outer: for (...)`). It lets `break label` or `continue label` act on an outer loop from within nested loops. It is rarely needed, and a function with `return` is often cleaner.

**Q12. Why can't you `break` out of `forEach`?**

**Answer:** `forEach` runs a callback function for each element, and `break` is only valid directly inside a loop or `switch`. A `return` in the callback only ends that call (like `continue`). Use `for...of`, `some()`, or `every()` to stop early.

**Q13. Why should you avoid `return` inside a `finally` block?**

**Answer:** It overrides any value returned or error thrown in the `try` or `catch` blocks, which can hide errors and produce surprising results.

### 🔵 Practical and Advanced Questions

**Q14. What is the difference between `for...in` and `for...of`?**

**Answer:** `for...in` iterates over the enumerable property names (keys) of an object, including inherited ones. `for...of` iterates over the values of an iterable such as an array, string, `Map`, or `Set`.

**Q15. Why does `for...of` handle emoji better than indexing a string?**

**Answer:** `for...of` iterates over Unicode code points, while indexing and `length` work on 16-bit code units, so characters outside the basic range (like emoji) are split into two units.

**Q16. In which situation can `continue` cause an infinite loop?**

**Answer:** In a `while` loop where the counter update is inside the body after the `continue`. The update is skipped, so the condition never changes. In a `for` loop, the update part still runs.

**Q17. Why does `if (true) let x = 1;` cause a `SyntaxError`?**

**Answer:** A lexical declaration (`let`, `const`, `class`) cannot be the direct body of a single-statement context like `if`. It must be inside a block.

**Q18. Why does `let a = 1; { var a = 2; }` throw an error?**

**Answer:** `var a` is hoisted to the enclosing function or global scope, where `let a` is already declared, so the identifier is declared twice, which is a `SyntaxError`.

**Q19. What does this return?**

```javascript
function f() {
    try { return "A"; } finally { console.log("B"); }
}
console.log(f());
```

**Answer:** It prints `B` first, then `A`. The `finally` block runs before the function returns.

**Q20. What is strict mode, and where must `"use strict"` appear?**

**Answer:** Strict mode is a restricted variant of the language that turns silent mistakes into errors (for example, assigning to an undeclared variable throws a `ReferenceError`, and `this` is `undefined` in plain function calls). The directive must be the first statement in a script or function; ES modules and classes are strict automatically.

**Q21. Why should you throw `Error` objects instead of strings?**

**Answer:** `Error` objects carry a message, a name, and a stack trace, and they work with `instanceof` checks, so errors can be handled by type. A thrown string carries none of that.

**Q22. How do you handle only specific types of errors?**

**Answer:** In the `catch` block, check the error with `instanceof` (or its `name`), handle the expected type, and re-throw anything else with `throw e`.

**Q23. What is the purpose of the `cause` option on `Error`?**

**Answer:** `new Error("message", { cause: originalError })` (ES2022) attaches the original error so that higher-level code keeps the full context when re-throwing.

**Q24. Why does `function () {}()` fail while `(function () {})()` works?**

**Answer:** At the start of a statement, `function` is parsed as a declaration, which needs a name and cannot be invoked. Wrapping it in parentheses makes it an expression that can be called immediately.

**Q25. What are guard clauses and why use them?**

**Answer:** Early `return` statements at the top of a function that handle invalid or special cases first. They reduce nesting and keep the main logic easy to read.

---

## 🏆 16. Key Takeaways

- 🗺️ Statements fall into **declarations**, **expression statements**, **conditionals**, **loops**, **jumps**, **error handling**, blocks, and labeled or empty statements.
- 🧱 `let`, `const`, and `class` are **block-scoped**, and `var` is **function-scoped**.
- 🪝 Function declarations are fully hoisted, `var` gives `undefined`, and `let`, `const`, and `class` have a **temporal dead zone**.
- ✂️ **ASI** is handy but dangerous. Never put a `return` value on a new line, and protect lines that begin with `(` or `[`. The safest habit is to always write semicolons.
- 🔂 `do...while` runs at least once. In a `while` loop, `continue` can skip your counter update.
- 🔁 `for...of` works on any iterable and handles Unicode correctly. `for...in` is for object keys.
- 🏷️ Labels allow `break` and `continue` on outer loops, but a function with `return` is often cleaner.
- 🛡️ `finally` always runs, so use it for cleanup, and never `return` or `throw` inside it.
- 🧱 Throw `Error` objects (or subclasses), catch only what you can handle, and re-throw the rest.
- 🔒 `"use strict"` must be the first statement, and modules and classes are already strict.
- 🌿 Prefer **guard clauses** over deeply nested `if` statements.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Statements control the **flow** of your program. When code behaves unexpectedly, trace the order of execution line by line, and check what the parser really sees.

**Happy Coding! 💻✨**
