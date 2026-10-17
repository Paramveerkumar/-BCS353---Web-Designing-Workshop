# 📦 JavaScript Declarations (Intermediate)

> 📌 **Note:** The beginner *Variables* lesson covers the basics of `let`, `const`, and `var`. The *Statements (Intermediate)* lesson introduces hoisting and the temporal dead zone. This lesson goes deeper into **how declarations really work**: the three phases of a variable, scope and the global object, redeclaration rules, `const` semantics, destructuring declarations, function and class declarations, naming, and best practices.

> 🎯 **Learning Objectives**
> - Distinguish **declaration**, **initialisation**, and **assignment**.
> - Compare `var`, `let`, `const`, function, and class declarations precisely.
> - Understand scope types, the scope chain, and shadowing.
> - Know which declarations create properties on the global object.
> - Predict redeclaration errors and temporal-dead-zone errors, including inside default parameters.
> - Explain what `const` really protects, and use `Object.freeze()` correctly.
> - Use destructuring in declarations (defaults, renaming, nesting, rest).
> - Choose clear names and follow professional declaration habits.

---

## 🌟 1. What is a Declaration?

A **declaration** introduces a **name** into a scope so that JavaScript knows it exists.

JavaScript has these declaration forms:

| Declaration | Example | Creates |
|---|---|---|
| `var` | `var a = 1;` | A function-scoped variable |
| `let` | `let b = 2;` | A block-scoped variable that can be reassigned |
| `const` | `const c = 3;` | A block-scoped binding that **cannot be reassigned** |
| `function` | `function f() {}` | A function (hoisted) |
| `class` | `class A {}` | A class (block-scoped, TDZ) |
| `import` | `import x from "./x.js"` | A read-only **module binding** |

### 🔤 Declaration vs Initialisation vs Assignment

Think of **reserving, filling, and changing a locker**. 🗄️

| Step | Meaning | Code |
|---|---|---|
| 1️⃣ **Declaration** | Reserve the locker (the name exists) | `let score;` |
| 2️⃣ **Initialisation** | Put the **first** value inside | `score = 10;` (or `let score = 10;`) |
| 3️⃣ **Assignment** | Replace the value **later** | `score = 20;` |

```javascript
let score;
console.log(score);

score = 10;
console.log(score);

score = 20;
console.log(score);
```

### 📤 Output

```text
undefined
10
20
```

### 🧠 Remember This!

- A declared-but-not-initialised `let` or `var` holds `undefined`.
- A `const` must be initialised **at the moment it is declared**.
- Declaring is **not** the same as assigning. The three steps can happen together (`let x = 5;`) or separately.

---

## 🧭 2. `var`, `let`, `const` Compared in Depth

| Feature | `var` | `let` | `const` |
|---|---|---|---|
| Scope | **Function** (or global) | **Block** | **Block** |
| Hoisted? | ✅ Yes, initialised as `undefined` | ✅ Yes, but in the **TDZ** | ✅ Yes, but in the **TDZ** |
| Can be redeclared in the same scope? | ✅ Yes | ❌ `SyntaxError` | ❌ `SyntaxError` |
| Can be reassigned? | ✅ Yes | ✅ Yes | ❌ `TypeError` |
| Needs an initial value? | ❌ No | ❌ No | ✅ **Yes** |
| Creates a property on the global object (top level of a classic script)? | ✅ **Yes** | ❌ No | ❌ No |
| Per-iteration binding in `for` loops? | ❌ No (one shared variable) | ✅ Yes | ✅ Yes (but `i++` fails) |
| Recommended today? | ⚠️ Avoid | ✅ When the value changes | ✅ **Default choice** |

### 🌍 The Global Object

At the top level of a **classic browser script**, `var` and function declarations become **properties of the global object** (`window` / `globalThis`). `let`, `const`, and `class` do **not**.

```javascript
var a = 1;
let b = 2;
const c = 3;
function f() {}
class K {}

console.log(globalThis.a);
console.log(globalThis.b);
console.log(globalThis.c);
console.log(typeof globalThis.f);
console.log(typeof globalThis.K);
```

### 📤 Output (browser, classic script)

```text
1
undefined
undefined
function
undefined
```

> ⚠️ In **Node.js (CommonJS)** and in **ES modules**, top-level declarations are scoped to the file or module, so even `var a` does **not** appear on `globalThis`. This is one more reason to use modules.

### 🪤 Accidental Globals

```javascript
function setup() {
    leaked = "oops";       // no declaration keyword
}

setup();
console.log(leaked);
```

### 📤 Output (sloppy mode)

```text
oops
```

In **strict mode** the assignment throws `ReferenceError: leaked is not defined`. Always declare variables, and use strict mode or modules.

---

## 🔁 3. Redeclaration Rules

```javascript
var a = 1;
var a = 2;               // ✅ allowed
console.log(a);

let b = 1;
// let b = 2;            // ❌ SyntaxError: Identifier 'b' has already been declared

// var b = 3;            // ❌ also an error: 'b' already exists as a let
```

### 📤 Output

```text
2
```

### 🔍 Where Redeclaration Errors Appear

| Situation | Result |
|---|---|
| `var x; var x;` | ✅ Allowed (silently reuses the variable) |
| `let x; let x;` | ❌ `SyntaxError` |
| `let x; var x;` (or the other way around, same scope) | ❌ `SyntaxError` |
| `function f(p) { let p; }` (parameter vs `let`) | ❌ `SyntaxError` |
| `function f(p) { var p; }` | ✅ Allowed |
| `let x = 1; { let x = 2; }` (different scopes) | ✅ Allowed (**shadowing**) |
| `let x = 1; { var x = 2; }` | ❌ `SyntaxError` (`var` hoists into the same scope as `let x`) |

> 💡 The `SyntaxError` for `let` is detected **before the code runs**, which is a good thing: it catches typos early. `var` silently hides such mistakes.

### 🆚 `function` and `var` with the Same Name

```javascript
console.log(typeof f);

var f = 1;

function f() {}

console.log(typeof f);
```

### 📤 Output

```text
function
number
```

Function declarations are hoisted **with their value**, so `f` is a function at first. Then the assignment `f = 1` runs and replaces it with a number.

### 🔁 Duplicate Function Declarations

```javascript
function greet() {
    return "first";
}

function greet() {
    return "second";
}

console.log(greet());
```

### 📤 Output

```text
second
```

The **last** declaration wins. Never rely on this. It usually signals a mistake.

---

## 🧊 4. `const` in Depth

### 🔒 What `const` Protects: The **Binding**, Not the Value

```javascript
const user = { name: "Aman" };

user.name = "Priya";
console.log(user);

// user = {};             // ❌ TypeError: Assignment to constant variable.
```

### 📤 Output

```text
{ name: 'Priya' }
```

`const` means "this **name** will always point to the same value". If that value is an object or array, its **contents** can still change.

### 📏 `const` Must Be Initialised

```javascript
const a;
```

### 📤 Output

```text
SyntaxError: Missing initializer in const declaration
```

### 🪤 `const` in a Classic `for` Loop

```javascript
for (const i = 0; i < 3; i++) {
    console.log(i);
}
```

### 📤 Output

```text
0
TypeError: Assignment to constant variable.
```

The first iteration runs, but `i++` tries to reassign a constant. (`for (const x of list)` and `for (const k in obj)` are fine, because each iteration creates a **new** binding.)

### 🧊 Making the Value Itself Immutable: `Object.freeze()`

```javascript
const settings = Object.freeze({ theme: "dark", nested: { size: 12 } });

settings.theme = "light";        // ignored silently (TypeError in strict mode)
settings.nested.size = 99;       // ✅ works: freeze is SHALLOW

console.log(settings);
console.log(Object.isFrozen(settings));
console.log(Object.isFrozen(settings.nested));
```

### 📤 Output

```text
{ theme: 'dark', nested: { size: 99 } }
true
false
```

### 🧊🧊 Deep Freeze

```javascript
function deepFreeze(obj) {
    Object.values(obj).forEach((value) => {
        if (typeof value === "object" && value !== null) {
            deepFreeze(value);
        }
    });
    return Object.freeze(obj);
}

const config = deepFreeze({ api: { url: "https://example.com", retries: 3 } });

config.api.retries = 10;         // ignored (TypeError in strict mode)
console.log(config.api.retries);
```

### 📤 Output

```text
3
```

### 📊 Three Levels of Protection

| Tool | Protects |
|---|---|
| `const` | The **variable** cannot be reassigned |
| `Object.freeze(obj)` | The object's **own properties** cannot be added, removed, or changed (shallow) |
| Deep freeze | Nested objects too |

---

## 🌳 5. Scopes and the Scope Chain

### 🗂️ Kinds of Scope

| Scope | Created by | Holds |
|---|---|---|
| 🌍 **Global** | The top level of a classic script | `var`, `function` (as properties), and `let`/`const`/`class` (in a separate global lexical scope) |
| 📄 **Module** | A file loaded as an ES module | Everything declared at the top level of that file |
| 🔧 **Function** | A function body | `var`, `let`, `const`, parameters, inner functions |
| 🧱 **Block** | `{ ... }` of `if`, `for`, `while`, `try`, `catch`, plain blocks | `let`, `const`, `class` (not `var`) |

### 🔗 The Scope Chain

When JavaScript looks up a name, it starts in the **current** scope and moves **outwards** until it finds it. If it reaches the global scope without a match, it throws a `ReferenceError`.

```javascript
const level = "global";

function outer() {
    const level = "outer";

    function inner() {
        console.log(level);
    }

    inner();
}

outer();
```

### 📤 Output

```text
outer
```

`inner` has no `level` of its own, so it finds the one in `outer` first (this is **shadowing**).

### 🔭 Scope is Decided by Where Code is **Written** (Lexical Scope)

```javascript
const name = "global";

function show() {
    console.log(name);
}

function run() {
    const name = "local";
    show();
}

run();
```

### 📤 Output

```text
global
```

`show` looks up `name` from the place where it was **defined** (global), not from where it was **called**.

### 🔁 Per-Iteration Bindings in Loops

```javascript
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log("var:", i), 0);
}

for (let j = 0; j < 3; j++) {
    setTimeout(() => console.log("let:", j), 0);
}
```

### 📤 Output

```text
var: 3
var: 3
var: 3
let: 0
let: 1
let: 2
```

`var` creates **one** variable shared by all iterations. `let` creates a **fresh** variable for each iteration, so each closure keeps its own value.

---

## 🧮 6. Declaring Multiple Variables and Initialisation Order

```javascript
let a = 1, b = a + 1, c;
console.log(a, b, c);
```

### 📤 Output

```text
1 2 undefined
```

Declarations in one statement run **left to right**, so `b` can use `a`.

### ⏳ TDZ Between Declarations

```javascript
try {
    const x = y + 1;
    const y = 1;
} catch (e) {
    console.log(e.name + ": " + e.message);
}
```

### 📤 Output

```text
ReferenceError: Cannot access 'y' before initialization
```

### ⏳ TDZ in Default Parameters

Parameters are initialised **left to right**, so a default can use an **earlier** parameter but not a later one.

```javascript
function ok(a, b = a * 2) {
    return a + b;
}

function broken(a = b, b = 2) {
    return a + b;
}

console.log(ok(5));

try {
    broken();
} catch (e) {
    console.log(e.name);
}
```

### 📤 Output

```text
15
ReferenceError
```

### 🪤 Shadowing and the TDZ

```javascript
let x = "outer";

{
    try {
        console.log(x);
    } catch (e) {
        console.log(e.name);
    }
    let x = "inner";
}
```

### 📤 Output

```text
ReferenceError
```

The inner `let x` is hoisted to the top of its **block** and creates a dead zone, so the code can't see the outer `x` at all inside that block.

---

## 🧩 7. Destructuring Declarations

Destructuring **declares and initialises** several variables from an array or object in one step.

### 📚 Array Destructuring

```javascript
const [first, second = 10, ...rest] = [1, undefined, 3, 4];

console.log(first);
console.log(second);
console.log(rest);

const [, , third] = ["a", "b", "c"];
console.log(third);
```

### 📤 Output

```text
1
10
[ 3, 4 ]
c
```

- The default value (`= 10`) is used when the value is **`undefined`**.
- A rest element `...rest` collects the remaining items into a real array.
- Commas can **skip** items.

### 🧾 Object Destructuring

```javascript
const person = { name: "Aman", age: 20, role: "admin" };

const { name, age: years, city = "Delhi", ...others } = person;

console.log(name);
console.log(years);
console.log(city);
console.log(others);
```

### 📤 Output

```text
Aman
20
Delhi
{ role: 'admin' }
```

| Syntax | Meaning |
|---|---|
| `{ name }` | Declare `name` from the property `name` |
| `{ age: years }` | Take the property `age`, and declare the variable `years` |
| `{ city = "Delhi" }` | Use a default if the property is `undefined` |
| `{ ...others }` | Collect the remaining properties into an object |

### 🪆 Nested Destructuring

```javascript
const order = {
    id: 101,
    customer: { name: "Riya", address: { pin: 110001 } },
    items: ["pen", "book"]
};

const {
    id,
    customer: { name: customerName, address: { pin } },
    items: [firstItem]
} = order;

console.log(id, customerName, pin, firstItem);
```

### 📤 Output

```text
101 Riya 110001 pen
```

Only the names at the **end** of each pattern (`id`, `customerName`, `pin`, `firstItem`) become variables. `customer` and `address` are **not** declared.

### 🔧 In Function Parameters

```javascript
function show({ name, age = 18 }, [x, y] = [0, 0]) {
    console.log(name, age, x, y);
}

show({ name: "Aman" });
show({ name: "Priya", age: 22 }, [3, 4]);
```

### 📤 Output

```text
Aman 18 0 0
Priya 22 3 4
```

### 🪤 Gotchas

**1. Defaults apply only to `undefined`, not `null`**

```javascript
const { v = 5 } = { v: null };
const { w = 5 } = { w: undefined };

console.log(v);
console.log(w);
```

### 📤 Output

```text
null
5
```

**2. Destructuring `null` or `undefined` throws**

```javascript
const { x } = null;
```

### 📤 Output

```text
TypeError: Cannot destructure property 'x' of 'null' as it is null.
```

**3. Assigning with object destructuring needs parentheses**

```javascript
let a;

// { a } = { a: 7 };      // ❌ SyntaxError: { is read as a BLOCK
({ a } = { a: 7 });       // ✅
console.log(a);
```

### 📤 Output

```text
7
```

---

## ⚙️ 8. Function Declarations vs Expressions

| Feature | Declaration | Expression (`const f = function(){}` / arrow) |
|---|---|---|
| Hoisted with its value | ✅ Yes (callable before its line) | ❌ No (follows the rules of `var`/`let`/`const`) |
| Needs a name | ✅ Yes | ❌ Optional |
| Can be redeclared | Yes (last wins) | ❌ No (with `let` or `const`) |
| Is a statement | ✅ | ❌ It is an expression |

```javascript
console.log(add(2, 3));

function add(a, b) {
    return a + b;
}

try {
    multiply(2, 3);
} catch (e) {
    console.log(e.name + ": " + e.message);
}

const multiply = (a, b) => a * b;
```

### 📤 Output

```text
5
ReferenceError: Cannot access 'multiply' before initialization
```

### 🧱 Function Declarations Inside Blocks

```javascript
"use strict";

{
    function inner() {
        return "hi";
    }
    console.log(inner());
}

console.log(typeof inner);
```

### 📤 Output

```text
hi
undefined
```

In **strict mode** (and modules), a function declared inside a block is **block-scoped**. In older **sloppy mode**, browsers apply legacy rules that make it also visible outside the block, which behaves inconsistently. To avoid confusion, don't declare functions inside blocks. Use `const fn = () => { ... }` instead.

---

## 🏛️ 9. Class Declarations

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        return `${this.name} makes a sound`;
    }
}

const a = new Animal("Dog");
console.log(a.speak());
console.log(typeof Animal);
console.log(typeof globalThis.Animal);
```

### 📤 Output

```text
Dog makes a sound
function
undefined
```

### 🔍 How Class Declarations Differ from Function Declarations

| Feature | `function` declaration | `class` declaration |
|---|---|---|
| Usable before its line | ✅ Yes | ❌ No (TDZ) |
| Scope | Function (or block in strict mode) | **Block** |
| Creates a global property | ✅ In a classic script | ❌ No |
| Can be redeclared | Yes | ❌ No |
| Code inside is always strict | ❌ No | ✅ **Yes** |
| Callable without `new` | ✅ Yes | ❌ `TypeError` |

---

## 🏷️ 10. Naming Declarations

### ✅ Rules

- A name may contain **letters, digits, `_`, and `$`** (including many Unicode letters).
- It **cannot start with a digit** and cannot contain spaces or hyphens.
- It cannot be a **reserved word** (`class`, `const`, `if`, `new`, and so on).
- Names are **case-sensitive**.

```javascript
const π = 3.14159;
const $el = "element";
const _private = "convention";

console.log(π, $el, _private);
```

### 📤 Output

```text
3.14159 element convention
```

> ⚠️ Unicode names are legal but make code harder to type and share. Stick to ASCII in team projects.

### 📋 Conventions

| Kind | Style | Example |
|---|---|---|
| Variables and functions | `camelCase` | `totalPrice`, `getUser` |
| Classes and constructors | `PascalCase` | `UserAccount` |
| True constants (fixed configuration) | `UPPER_SNAKE_CASE` | `MAX_RETRIES` |
| Booleans | Prefix `is`, `has`, `can`, `should` | `isActive`, `hasAccess` |
| "Private" by convention | Leading `_` (real privacy uses `#`) | `_cache`, `#secret` |
| Unused value | `_` | `const [, second] = list` or `(_, i) => i` |

> 💡 Not every `const` needs `UPPER_SNAKE_CASE`. Use it for **fixed, module-level constants** (like `MAX_RETRIES`), and `camelCase` for values that are simply computed once (like `const total = a + b`).

---

## 🏭 11. Mini Example: Putting Declarations to Work

```javascript
const CONFIG = Object.freeze({ currency: "₹", taxRate: 0.18 });

function createIdGenerator(prefix) {
    let next = 1;
    return () => `${prefix}-${next++}`;
}

const userId = createIdGenerator("USR");
const orderId = createIdGenerator("ORD");

const { currency, taxRate } = CONFIG;
const [price, qty] = [250, 2];
const total = price * qty * (1 + taxRate);

console.log(userId());
console.log(userId());
console.log(orderId());
console.log(`${currency}${total.toFixed(2)}`);
```

### 📤 Output

```text
USR-1
USR-2
ORD-1
₹590.00
```

### 🔍 Declarations Used

| Declaration | Purpose |
|---|---|
| `const CONFIG = Object.freeze(...)` | A fixed, protected configuration |
| `function createIdGenerator` | A hoisted declaration that creates a closure |
| `let next` | A private counter that changes inside the closure |
| Object and array destructuring | Declare `currency`, `taxRate`, `price`, and `qty` in one line each |
| `const total` | A computed value that never changes |

---

## ✅ 12. Best Practices

| Practice | Why |
|---|---|
| 🥇 Use **`const` by default**, `let` only if the value changes, and **never `var`** | Fewer bugs and clearer intent |
| 📍 Declare variables **as close as possible** to where they are used | Smaller scope, easier to read |
| 1️⃣ One declaration per line (`const a = 1;`) | Easier to read and review |
| 🏁 Initialise at the point of declaration | Avoids `undefined` surprises |
| 🔒 Avoid global variables. Use modules or functions | Prevents name clashes |
| 🔒 Use **strict mode** or ES modules | Turns accidental globals into errors |
| 🏷️ Choose **descriptive** names | Self-documenting code |
| 🌓 Avoid shadowing names from outer scopes | Prevents confusion |
| 🧰 Enable linter rules: `no-var`, `prefer-const`, `no-shadow`, `no-undef` | Catches problems automatically |

### 🧭 Quick Decision Guide

```text
Will the variable be reassigned?
 ├── No  ──► const
 └── Yes ──► let
(var is only for reading old code)
```

---

## 🎯 13. Predict the Output

```javascript
// 1
console.log(typeof f);
var f = 1;
function f() {}
console.log(typeof f);

// 2
let x = 1;
{
    try { console.log(x); } catch (e) { console.log(e.name); }
    let x = 2;
}

// 3
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 0);
}

// 4
const o = { a: 1 };
o.a = 2;
console.log(o.a);

// 5
const { v = 5 } = { v: null };
console.log(v);

// 6
function g(a = b, b = 2) { return a + b; }
try { g(); } catch (e) { console.log(e.name); }

// 7
var a = 1;
var a = 2;
console.log(a);
```

### ✅ Solution

| # | Output | Reason |
|---|---|---|
| 1 | `function` then `number` | The function is hoisted with its value, then `f = 1` reassigns it |
| 2 | `ReferenceError` | The inner `let x` creates a TDZ for the whole block |
| 3 | `3`, `3`, `3` | `var` shares one `i`, and the timeouts run after the loop ends |
| 4 | `2` | `const` protects the binding, not the object's contents |
| 5 | `null` | Defaults apply only for `undefined`, not `null` |
| 6 | `ReferenceError` | `b` is in the TDZ when `a`'s default is evaluated |
| 7 | `2` | `var` allows redeclaration, and the second assignment wins |

---

## ⚠️ 14. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Declaring a `const` without a value | `const x = 5;` (initialise immediately) |
| Believing `const` makes an object immutable | Use `Object.freeze()` (and deep freeze if needed) |
| Using `var` inside blocks and expecting block scope | Use `let` or `const` |
| Forgetting a keyword (`total = 5;`), which creates an accidental global | Always declare: `const total = 5;` |
| Using a variable before its `let`, `const`, or `class` line | Declare first (TDZ) |
| Declaring `let x` in a function that already has a parameter `x` | Use a different name |
| Using `const i` in a classic `for` loop | Use `let i` |
| `{ a } = obj;` at the start of a statement | `({ a } = obj);` |
| Expecting `const { v = 5 } = { v: null }` to give `5` | Defaults apply only to `undefined` |
| Destructuring a value that may be `null` or `undefined` | Provide a fallback: `const { x } = obj ?? {};` |
| Declaring functions inside blocks | Use a `const` function expression |
| Relying on `var` creating properties on `window` | Use explicit exports or objects |
| Shadowing outer variables carelessly | Use distinct names |

---

## 🧪 15. Practice Tasks

- [ ] 🟢 **Beginner:** Declare `let score;`, print it, then initialise it and change it. Explain the three steps.
- [ ] 🟢 **Beginner:** Write code that produces each of these errors on purpose: *Missing initializer in const declaration*, *Assignment to constant variable*, and *Identifier has already been declared*.
- [ ] 🟡 **Intermediate:** Create `const user = { name: "Aman", tags: ["a"] }`. Change `name`, push to `tags`, then try to reassign `user`. Explain each result.
- [ ] 🟡 **Intermediate:** Use `Object.freeze()` on an object with a nested object. Show which changes are blocked and which are not, then write `deepFreeze`.
- [ ] 🟡 **Intermediate:** Demonstrate the temporal dead zone with a `let`, a `class`, and a default parameter.
- [ ] 🔵 **Practice:** Given `const data = { id: 7, info: { name: "Riya", langs: ["JS", "Python"] } }`, use **one** destructuring declaration to create `id`, `name`, and `firstLang`.
- [ ] 🔵 **Practice:** Write a function that takes `({ width = 1, height = 1 } = {})` and returns the area. Call it with no argument, with one property, and with both.
- [ ] 🔵 **Practice:** In a browser, show that `var` and `function` declarations appear on `globalThis` while `let`, `const`, and `class` do not.
- [ ] 🔴 **Challenge:** Fix this loop so that it prints `0, 1, 2` without changing `var` to `let`: `for (var i = 0; i < 3; i++) setTimeout(() => console.log(i), 0);`
- [ ] 🔴 **Challenge:** Write `createCounter(start = 0)` that returns an object with `increment()`, `decrement()`, and `value()`. The count must be private, using declarations and a closure.
- [ ] 🔴 **Challenge:** Explain why `let x = 1; { console.log(x); let x = 2; }` throws instead of printing `1`.

---

## 🎤 16. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a declaration?**

**Answer:** A declaration introduces a name into a scope (using `var`, `let`, `const`, `function`, `class`, or `import`) so that JavaScript knows the name exists.

**Q2. What is the difference between declaration, initialisation, and assignment?**

**Answer:** Declaration creates the name (`let x;`), initialisation gives it its first value, and assignment changes its value later (`x = 5;`). They can happen together, as in `let x = 5;`.

**Q3. What value does a declared but uninitialised `let` or `var` hold?**

**Answer:** `undefined`.

**Q4. Must a `const` be initialised when it is declared?**

**Answer:** Yes. `const x;` throws `SyntaxError: Missing initializer in const declaration`.

**Q5. Which declaration should you use by default?**

**Answer:** `const`. Use `let` only when the value must be reassigned, and avoid `var`.

### 🟡 Intermediate Questions

**Q6. What does `const` actually protect?**

**Answer:** It prevents **reassigning the variable** to a different value. If the value is an object or array, its contents can still be changed.

**Q7. How can you make an object truly immutable?**

**Answer:** Use `Object.freeze(obj)`, which blocks adding, removing, or changing the object's own properties. It is shallow, so nested objects need `Object.freeze` applied recursively (a deep freeze).

**Q8. What is the difference between `var` and `let` scope?**

**Answer:** `var` is function-scoped (it ignores blocks), while `let` is block-scoped, so it exists only inside the nearest `{ }`.

**Q9. Which declarations create properties on the global object?**

**Answer:** In a classic browser script, `var` and function declarations at the top level become properties of `globalThis`. `let`, `const`, and `class` do not. In ES modules and Node.js (CommonJS), none of them do.

**Q10. What is the scope chain?**

**Answer:** The sequence of scopes JavaScript searches when resolving a name: it starts at the current scope and moves outward to the global scope, throwing a `ReferenceError` if the name is not found.

**Q11. What is shadowing?**

**Answer:** Declaring a variable in an inner scope with the same name as one in an outer scope. The inner one hides the outer one inside that scope.

**Q12. Why does `let x = 1; { var x = 2; }` throw an error?**

**Answer:** `var x` is hoisted to the enclosing function or global scope, which already contains `let x`, so the name is declared twice, causing a `SyntaxError`.

**Q13. What is the temporal dead zone?**

**Answer:** The period from the start of a scope until a `let`, `const`, or `class` declaration is executed. Accessing the name during this period throws a `ReferenceError`.

### 🔵 Practical and Advanced Questions

**Q14. What happens with `typeof f; var f = 1; function f() {}; typeof f`?**

**Answer:** The first `typeof f` is `"function"`, because function declarations are hoisted with their value. After `var f = 1;` runs, the second `typeof f` is `"number"`.

**Q15. Why does `for (const i = 0; i < 3; i++)` fail?**

**Answer:** The loop body runs once, then `i++` tries to reassign the constant `i`, throwing a `TypeError`. `for (const x of list)` works because each iteration creates a fresh binding.

**Q16. Why does `var` in a loop with `setTimeout` print the same number each time, while `let` does not?**

**Answer:** `var` creates a single variable shared by all iterations, which holds its final value when the timeouts fire. `let` creates a new binding per iteration, so each closure captures its own value.

**Q17. When is a default value used in destructuring?**

**Answer:** Only when the value is `undefined`. A value of `null` does not trigger the default.

**Q18. What happens when you destructure `null` or `undefined`?**

**Answer:** A `TypeError` is thrown. A common guard is `const { x } = obj ?? {};`.

**Q19. Why is `({ a } = obj)` written with parentheses?**

**Answer:** At the start of a statement, `{` is parsed as a block. Parentheses make it an expression so it is read as a destructuring assignment.

**Q20. What is wrong with `function f(a = b, b = 2) {}`?**

**Answer:** Parameters are initialised left to right, so `b` is still in the temporal dead zone when `a`'s default is evaluated, causing a `ReferenceError` when `f()` is called with no arguments.

**Q21. How do class declarations differ from function declarations?**

**Answer:** Classes are not usable before their declaration (temporal dead zone), are block-scoped, do not create global properties, always run in strict mode, and cannot be called without `new`.

**Q22. What happens when you assign to a name that was never declared?**

**Answer:** In sloppy mode, it creates a global variable, which is a common source of bugs. In strict mode (and modules), it throws a `ReferenceError`.

**Q23. Why should functions not be declared inside blocks?**

**Answer:** Behaviour differs between strict mode (block-scoped) and legacy sloppy mode (also visible outside the block), which is inconsistent. A `const` function expression is clearer.

**Q24. What is the difference between `UPPER_SNAKE_CASE` and `camelCase` for `const`?**

**Answer:** `UPPER_SNAKE_CASE` signals a fixed, module-level configuration constant (like `MAX_RETRIES`). `camelCase` is used for ordinary values that happen to be declared with `const`.

**Q25. Which linter rules help with declarations?**

**Answer:** `no-var`, `prefer-const`, `no-shadow`, `no-undef`, and `no-use-before-define`.

---

## 🏆 17. Key Takeaways

- 📦 A declaration introduces a name. **Declaration**, **initialisation**, and **assignment** are three separate steps.
- 🥇 Use **`const` by default**, `let` when you must reassign, and avoid `var`.
- 🧱 `let`, `const`, and `class` are **block-scoped** with a **temporal dead zone**. `var` is function-scoped.
- 🌍 Only `var` and function declarations (in classic scripts) become **global object properties**. Modules avoid this entirely.
- 🔁 `let` redeclaration is a **SyntaxError**, while `var` silently allows it. A `let` and a `var` of the same name in one scope collide.
- 🧊 `const` locks the **binding**, not the value. Use `Object.freeze()` (and deep freeze) to protect objects.
- 🔗 Names are resolved along the **scope chain**, using lexical (where-it-was-written) scope.
- 🔁 `let` gives each loop iteration its **own** binding, and `var` shares one.
- 🧩 **Destructuring** declares several variables at once (with defaults, renaming, nesting, and rest). Defaults apply only for `undefined`.
- 🏛️ Class declarations are hoisted into the TDZ, are block-scoped, and are always strict.
- 🏷️ Choose clear names (`camelCase`, `PascalCase`, `UPPER_SNAKE_CASE`) and declare variables close to where they are used.
- 🔒 Strict mode and ES modules turn accidental globals into errors.

---

### 🚀 Keep Practising!

> 💡 **Remember:** A good declaration answers three questions: *Where does this name live? Can it change? What is its first value?*

**Happy Coding! 💻✨**
