# 📜 ECMAScript (ES): The Standard Behind JavaScript

> 🎯 **Learning Objectives**
> - Explain the difference between ECMAScript, JavaScript, engines, and runtimes.
> - Understand who maintains the language and how a new feature becomes part of it.
> - Trace the history of ECMAScript editions (ES5 to ES2026) and the key features of each.
> - Use important modern features from ES2015 to ES2026 in real code.
> - Check browser and Node.js support, and use feature detection, transpilers, and polyfills.
> - Avoid common misunderstandings (for example, "`setTimeout` is part of ECMAScript").

---

## 🌟 1. What is ECMAScript?

**ECMAScript (ES)** is the **official specification** (the rulebook) that defines how the JavaScript language must work: its syntax, types, operators, objects, and built-in methods.

**JavaScript** is the language people actually write, and it follows that specification.

Think of **a recipe book and the chefs who cook from it**. 👨‍🍳

| Cooking | Programming |
|---|---|
| 📖 The recipe book (rules everyone agrees on) | **ECMAScript** (the specification, called ECMA-262) |
| 👨‍🍳 Chefs who cook from the book | **JavaScript engines** (V8, SpiderMonkey, JavaScriptCore) |
| 🍽️ The dish | A running JavaScript program |
| 🏪 The restaurant (tables, menu, doorbell) | **The runtime** (browser or Node.js) with extra features like the DOM and `fetch` |

### 🧠 Remember This!

- **ECMAScript** = the standard (the rules).
- **JavaScript** = the most popular language that implements the standard.
- **Engine** = the program that runs the code.
- **Runtime** = engine + extra tools (browser APIs or Node.js APIs).

### 🧩 Why Does It Have Such an Odd Name?

JavaScript was created at Netscape in 1995. "JavaScript" was a trademark (originally of Sun Microsystems, and now owned by Oracle), so the standard had to use another name. The standards body was **Ecma International**, so the language became **"ECMAScript"**, and the specification is **ECMA-262**.

---

## 🏗️ 2. ECMAScript vs JavaScript vs Engines vs Web APIs

| Term | What it is | Examples |
|---|---|---|
| 📜 **ECMAScript** | The language specification | Variables, functions, classes, `Array`, `Map`, `Promise`, `JSON`, `Math` |
| 🟨 **JavaScript** | The language built on ECMAScript (plus host features) | What you write every day |
| ⚙️ **Engine** | Reads and runs the code | V8 (Chrome, Node.js, Edge), SpiderMonkey (Firefox), JavaScriptCore (Safari) |
| 🌐 **Browser Web APIs** | Features the browser adds | `document`, `window`, `fetch`, `localStorage`, `alert` |
| 🖥️ **Node.js APIs** | Features Node.js adds | `fs`, `process`, `require`, `http` |

### 🪤 Which of These are Actually in the ECMAScript Specification?

| Feature | Part of ECMAScript? |
|---|---|
| `let`, `const`, `class`, `async/await` | ✅ Yes |
| `Array`, `Map`, `Set`, `Promise`, `JSON`, `Math` | ✅ Yes |
| `console.log` | ❌ No (provided by the host, with its own standard) |
| `setTimeout`, `setInterval` | ❌ No (host-provided) |
| `document.querySelector`, `addEventListener` | ❌ No (DOM, not ECMAScript) |
| `fetch`, `localStorage` | ❌ No (Web APIs) |
| `require`, `fs`, `process` | ❌ No (Node.js) |

> 💡 **Quick test:** if it works the same in a browser **and** in Node.js and is about the *language itself*, it is probably ECMAScript. If it talks to the page, the screen, the network, or the file system, it comes from the host environment.

### 🔗 Related Languages and Tools

| Name | Relationship to ECMAScript |
|---|---|
| **TypeScript** | A **superset** of JavaScript that adds static types. It compiles down to plain JavaScript |
| **JScript** | Microsoft's old implementation (Internet Explorer era) |
| **ActionScript** | Adobe Flash's language, based on an earlier ECMAScript edition |
| **Babel** | A tool that converts new ECMAScript syntax into older syntax |

---

## 🏛️ 3. Who Maintains ECMAScript?

| Organisation | Role |
|---|---|
| 🌍 **Ecma International** | The standards body that publishes ECMA-262 |
| 👥 **TC39** (Technical Committee 39) | The committee (browser makers, companies, and experts) that designs and approves language changes |
| 📅 **Yearly editions** | Since ES2015, a new edition is approved by the Ecma General Assembly each **June**, and named by its year |

### 📅 The Naming Confusion: ES6 vs ES2015

- **ES6** and **ES2015** are the **same edition** (the 6th edition).
- Starting with that edition, versions are named by **year**, such as ES2016, ES2017, and so on.
- Saying "ES6" today usually means "the modern JavaScript introduced from 2015 onwards".

---

## 🛤️ 4. How a New Feature Becomes Part of JavaScript: The TC39 Process

Every new feature starts as a **proposal** and moves through **stages**.

| Stage | Name | Meaning |
|---|---|---|
| **0** | Strawperson | An idea is put forward for discussion |
| **1** | Proposal | The problem is studied and a **champion** (a committee member) is assigned |
| **2** | Draft | A first version of the specification text exists, and the feature is expected to be developed |
| **2.7** | Approved | The design is approved, and the proposal waits for tests and validation |
| **3** | Candidate | The design is complete, and engines implement it and give feedback |
| **4** | Finished | Tests exist, at least two engines ship it, and it is ready to join the **next annual edition** |

```text
Idea → Stage 0 → 1 → 2 → 2.7 → 3 → 4 → Included in next ES edition (June)
```

### 💡 Key Points

- A **Stage 4** feature is added to the next yearly edition.
- Browsers and Node.js often ship features **earlier** (at Stage 3), or **later** than the official edition date.
- You can follow all proposals on the **TC39 GitHub page** (`github.com/tc39/proposals`).

---

## 🕰️ 5. History and Evolution of ECMAScript

| Edition | Year | Highlights |
|---|---|---|
| **ES1** | 1997 | First standard version |
| **ES2** | 1998 | Editorial changes to align with the ISO standard |
| **ES3** | 1999 | Regular expressions, `try...catch`, better string handling |
| **ES4** | — | ❌ **Abandoned** after disagreements over its large scope |
| **ES5** | 2009 | Strict mode, `JSON`, `forEach`/`map`/`filter`/`reduce`, `Object.keys`, getters and setters, `bind` |
| **ES5.1** | 2011 | Alignment with the ISO edition and clarifications |
| **ES2015 (ES6)** | 2015 | 🌟 **The biggest update ever**: `let`/`const`, arrow functions, classes, template literals, destructuring, default/rest/spread, modules, `Promise`, `Map`/`Set`, `Symbol`, generators, `for...of` |
| **ES2016** | 2016 | `**` operator, `Array.prototype.includes()` |
| **ES2017** | 2017 | `async`/`await`, `Object.values()`/`Object.entries()`, `padStart()`/`padEnd()` |
| **ES2018** | 2018 | Object rest/spread, `Promise.prototype.finally()`, async iteration (`for await...of`), regex named groups, lookbehind |
| **ES2019** | 2019 | `flat()`/`flatMap()`, `Object.fromEntries()`, `trimStart()`/`trimEnd()`, optional `catch` binding, stable `sort()` |
| **ES2020** | 2020 | Optional chaining `?.`, nullish coalescing `??`, `BigInt`, `Promise.allSettled()`, `globalThis`, dynamic `import()` |
| **ES2021** | 2021 | `replaceAll()`, `Promise.any()`, logical assignment (`&&=`, `\|\|=`, `??=`), numeric separators (`1_000_000`) |
| **ES2022** | 2022 | Class fields, private `#fields`, static blocks, top-level `await`, `at()`, `Object.hasOwn()`, `Error` `cause` |
| **ES2023** | 2023 | `findLast()`/`findLastIndex()`, non-mutating `toSorted()`/`toReversed()`/`toSpliced()`/`with()` |
| **ES2024** | 2024 | `Object.groupBy()`/`Map.groupBy()`, `Promise.withResolvers()`, regex `v` flag |
| **ES2025** | 2025 | Iterator helpers, new `Set` methods (`union`, `intersection`...), `Promise.try()`, JSON modules via import attributes, `Float16Array` |
| **ES2026** | 2026 | Approved on **30 June 2026** (the 17th edition): `Array.fromAsync()`, `Math.sumPrecise()`, `Iterator.concat()`, `Error.isError()`, `Map`/`WeakMap` `getOrInsert()`, `Uint8Array` base64/hex methods, and JSON source-text access |

> ⚠️ **Temporal and `using`:** The `Temporal` date/time API and `using` declarations (explicit resource management) were widely expected for 2026, but they were not on the list of approved ES2026 additions in the sources checked in July 2026. Always check the TC39 "finished proposals" list for the latest status.

### 📊 What Changed Most?

```text
ES5 (2009)   ──►  ES2015 (2015)  ──►  ES2017 (async)  ──►  ES2020 (?. and ??)  ──►  ES2022 (classes, await)
Old JS             Modern JS           Easy async           Safer code               Mature language
```

---

## 🧪 6. Key Features in Action (Intermediate Level)

### ➡️ ES2015: Modules (`import` / `export`)

**📄 `math.js`**

```javascript
export const PI = 3.14159;

export function square(n) {
    return n * n;
}

export default function greet(name) {
    return "Hello, " + name;
}
```

**📄 `main.js`**

```javascript
import greet, { PI, square } from "./math.js";

console.log(greet("Aman"));
console.log(PI);
console.log(square(4));
```

### 📤 Output

```text
Hello, Aman
3.14159
16
```

**📄 `index.html`**

```html
<script type="module" src="main.js"></script>
```

> 💡 Use `type="module"` to enable `import`/`export` in the browser. Modules are always in **strict mode**.

### 🧩 ES2018: Object Rest and Spread

```javascript
const user = { name: "Aman", age: 20, city: "Delhi" };

const { name, ...rest } = user;
console.log(name);
console.log(rest);

const updated = { ...user, age: 21 };
console.log(updated);
```

### 📤 Output

```text
Aman
{ age: 20, city: 'Delhi' }
{ name: 'Aman', age: 21, city: 'Delhi' }
```

### 🛟 ES2020: Optional Chaining `?.` and Nullish Coalescing `??`

```javascript
const settings = { theme: { color: "blue" } };

console.log(settings.theme?.color);
console.log(settings.font?.size);
console.log(settings.font?.size ?? 16);

const volume = 0;
console.log(volume || 50);
console.log(volume ?? 50);
```

### 📤 Output

```text
blue
undefined
16
50
0
```

### 🔍 Explanation

- `?.` stops safely and returns `undefined` if something along the path is `null` or `undefined`.
- `??` uses the right side **only** for `null` or `undefined`.
- `||` replaces **any falsy value** (such as `0`), which is usually a bug for numbers. `??` keeps `0`.

### ✍️ ES2021: Logical Assignment Operators

```javascript
let a = null;
a ??= "default";
console.log(a);

let count = 0;
count ||= 10;
console.log(count);

const person = { name: "aman" };
person.name &&= person.name.toUpperCase();
console.log(person.name);
```

### 📤 Output

```text
default
10
AMAN
```

| Operator | Assigns only when the left side is... |
|---|---|
| `??=` | `null` or `undefined` |
| `\|\|=` | falsy |
| `&&=` | truthy |

### 🎯 ES2022: `at()`, `Object.hasOwn()`, Private Fields

```javascript
const letters = ["a", "b", "c"];
console.log(letters.at(-1));

const obj = { x: 1 };
console.log(Object.hasOwn(obj, "x"));
console.log(Object.hasOwn(obj, "toString"));

class BankAccount {
    #balance = 0;

    deposit(amount) {
        this.#balance += amount;
        return this.#balance;
    }
}

const account = new BankAccount();
console.log(account.deposit(500));
console.log(account.balance);
```

### 📤 Output

```text
c
true
false
500
undefined
```

Trying to read `account.#balance` from outside the class is a **syntax error**. The `#` makes the field truly private.

### 🧬 ES2023: Non-Mutating Array Methods

```javascript
const nums = [3, 1, 2];

const sorted = nums.toSorted((a, b) => a - b);
const reversed = nums.toReversed();

console.log(sorted);
console.log(reversed);
console.log(nums);
```

### 📤 Output

```text
[ 1, 2, 3 ]
[ 2, 1, 3 ]
[ 3, 1, 2 ]
```

The original array is **unchanged**, unlike `sort()` and `reverse()`.

### 🗂️ ES2024: `Object.groupBy()`

```javascript
const numbers = [1, 2, 3, 4, 5];

const grouped = Object.groupBy(numbers, (n) => (n % 2 === 0 ? "even" : "odd"));

console.log(grouped.even);
console.log(grouped.odd);
```

### 📤 Output

```text
[ 2, 4 ]
[ 1, 3, 5 ]
```

### 🔵 ES2025: New `Set` Methods

```javascript
const a = new Set([1, 2, 3]);
const b = new Set([3, 4]);

console.log([...a.union(b)]);
console.log([...a.intersection(b)]);
console.log([...a.difference(b)]);
console.log(a.isSubsetOf(new Set([1, 2, 3, 4])));
```

### 📤 Output

```text
[ 1, 2, 3, 4 ]
[ 3 ]
[ 1, 2 ]
true
```

---

## 🆕 7. What's New in ES2026

ES2026 is a **practical** update. It adds useful helpers rather than big new syntax.

> ⚠️ These are very new. Check your browser and Node.js version before relying on them (see section 8).

### 🔄 1. `Array.fromAsync()`

Builds an array from an **async** source, such as an async generator.

```javascript
async function* countdown() {
    yield 3;
    yield 2;
    yield 1;
}

async function main() {
    const arr = await Array.fromAsync(countdown());
    console.log(arr);
}

main();
```

### 📤 Output

```text
[ 3, 2, 1 ]
```

### ➕ 2. `Math.sumPrecise()`

Adds numbers while minimising floating-point rounding error.

```javascript
console.log(0.1 + 0.2 + 0.3);
console.log(Math.sumPrecise([0.1, 0.2, 0.3]));
```

### 📤 Output

```text
0.6000000000000001
0.6
```

### 🔗 3. `Iterator.concat()`

Joins several iterables into one iterator, without building a big array first.

```javascript
const combined = Iterator.concat([1, 2], [3, 4]);
console.log(combined.toArray());
```

### 📤 Output

```text
[ 1, 2, 3, 4 ]
```

> 💡 `toArray()` is one of the iterator helper methods added in ES2025.

### 🚨 4. `Error.isError()`

A reliable way to check whether a value is a real error object. Unlike `instanceof Error`, it also works for errors created in **another realm** (for example, inside an iframe).

```javascript
console.log(Error.isError(new Error("Oops")));
console.log(Error.isError({ message: "Oops" }));
console.log(Error.isError("Oops"));
```

### 📤 Output

```text
true
false
false
```

### 🗺️ 5. `Map.prototype.getOrInsert()` (and `WeakMap`)

Gets a value, or inserts a default if the key is missing. This replaces the old "check, then set" pattern.

```javascript
const cache = new Map();

console.log(cache.getOrInsert("views", 0));
cache.set("views", 5);
console.log(cache.getOrInsert("views", 0));
console.log(cache.size);
```

### 📤 Output

```text
0
5
1
```

A companion method, `getOrInsertComputed()`, takes a function so an expensive default is only calculated when it is actually needed.

### 🔐 6. `Uint8Array` Base64 and Hex Methods

```javascript
const bytes = new Uint8Array([72, 105]);

console.log(bytes.toBase64());
console.log(bytes.toHex());
console.log(Array.from(Uint8Array.fromBase64("SGk=")));
```

### 📤 Output

```text
SGk=
4869
[ 72, 105 ]
```

### 📄 7. JSON Source-Text Access

The `JSON.parse` reviver now receives a third argument with the **original text** of primitive values. This helps with numbers too big for JavaScript to represent exactly. `JSON.rawJSON()` lets `JSON.stringify` write such a number back exactly.

```javascript
const text = "12345678901234567890";

console.log(JSON.parse(text));

const source = JSON.parse(text, (key, value, context) => context.source);
console.log(source);

console.log(JSON.stringify({ id: JSON.rawJSON(text) }));
```

### 📤 Output

```text
12345678901234567000
12345678901234567890
{"id":12345678901234567890}
```

---

## 🌐 8. Using New Features Safely: Compatibility

A feature being in the specification does **not** mean every browser can run it today.

### 🔍 Step 1: Check Support

| Tool | Use |
|---|---|
| **MDN Web Docs** | Each feature page has a *Browser compatibility* table |
| **caniuse.com** | Browser support percentages |
| **node.green** | Node.js version support |
| **TC39 proposals page** | Which stage a feature is at |

### 🧪 Step 2: Feature Detection

Test whether a feature exists **before** using it, instead of guessing from the browser name.

```javascript
if (typeof Array.prototype.toSorted === "function") {
    console.log("toSorted is supported ✅");
} else {
    console.log("toSorted is NOT supported ❌");
}
```

### 📤 Output (modern browser or Node.js)

```text
toSorted is supported ✅
```

### 🔧 Step 3: Choose a Strategy

| Tool | What it does | Example |
|---|---|---|
| **Transpiler** (Babel, TypeScript) | Converts new **syntax** into older syntax | Arrow function → regular function |
| **Polyfill** (core-js) | Adds missing **methods** at runtime | Adds `Array.prototype.at` to old browsers |
| **Bundler + browserslist** | Chooses what to transform for your target browsers | Vite, webpack, esbuild |

### 🔁 What a Transpiler Does

**You write (ES2015):**

```javascript
const add = (a, b) => a + b;
```

**Babel can produce (ES5):**

```javascript
var add = function add(a, b) {
    return a + b;
};
```

### 🩹 What a Polyfill Looks Like (Simplified)

```javascript
if (!Array.prototype.at) {
    Array.prototype.at = function (index) {
        const i = index < 0 ? this.length + index : index;
        return this[i];
    };
}
```

> ⚠️ **Syntax vs API:** A transpiler can rewrite **syntax** (like `?.`, `class`, `=>`). A polyfill is needed for new **built-in methods** (like `toSorted`, `Object.groupBy`). Real polyfills handle many more edge cases than the simplified example above.

---

## ⚠️ 9. Common Misunderstandings

| ❌ Myth | ✅ Reality |
|---|---|
| "JavaScript and ECMAScript are different languages" | ECMAScript is the **specification**; JavaScript is the language that implements it |
| "ES6 is the newest version" | ES6 = ES2015. New editions arrive **every year** |
| "JavaScript is Java's little brother" | They are unrelated languages with different designs |
| "`setTimeout`, `fetch`, and `document` are JavaScript language features" | They come from the **host** (browser or Node.js), not ECMAScript |
| "If it's in the spec, it works everywhere" | Engines and browsers ship features at different times |
| "A transpiler adds missing methods" | Transpilers change **syntax**; **polyfills** add missing methods |
| "TypeScript is a different language from ECMAScript" | TypeScript is a **superset** of JavaScript and compiles to ECMAScript |
| "Newer is always better to use immediately" | Check your **target browsers** and Node.js versions first |

---

## 🧪 10. Practice Tasks

- [ ] 🟢 **Beginner:** Explain in your own words the difference between ECMAScript, JavaScript, and a JavaScript engine.
- [ ] 🟢 **Beginner:** Sort `console`, `setTimeout`, `Array`, `document`, `Promise`, and `fetch` into two groups: **part of ECMAScript** and **not part of ECMAScript**.
- [ ] 🟡 **Intermediate:** Rewrite `user && user.address && user.address.city` using optional chaining, and add a default value with `??`.
- [ ] 🟡 **Intermediate:** Use `toSorted()` to sort an array of numbers without changing the original, and prove the original is unchanged.
- [ ] 🔵 **Practice:** Use `Object.groupBy()` to group an array of student objects by their grade.
- [ ] 🔵 **Practice:** Use the new `Set` methods to find the common subjects between two students' subject sets.
- [ ] 🔵 **Practice:** Write a feature-detection check for `Object.groupBy` and print a message either way.
- [ ] 🔴 **Challenge:** Create two files, `utils.js` and `app.js`, and use ES modules (`export` and `import`) with `<script type="module">`.
- [ ] 🔴 **Challenge:** Write a small polyfill for `Array.prototype.last` (a method that returns the last element), and use `if (!Array.prototype.last)` so it is only added when missing.
- [ ] 🔴 **Challenge:** Look up one Stage 3 proposal on the TC39 proposals page, and write three sentences about the problem it tries to solve.

---

## 🎤 11. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is ECMAScript?**

**Answer:** ECMAScript is the standard specification (ECMA-262) that defines the syntax, types, and built-in objects of the JavaScript language.

**Q2. What is the relationship between ECMAScript and JavaScript?**

**Answer:** ECMAScript is the specification (the rules), and JavaScript is the language that implements it, along with extra features from its host environment such as the browser or Node.js.

**Q3. Who maintains ECMAScript?**

**Answer:** TC39, a technical committee of Ecma International made up of browser vendors, companies, and experts, designs the language, and Ecma International publishes it as ECMA-262.

**Q4. What is the difference between ES6 and ES2015?**

**Answer:** They are the same edition. ES6 is the 6th edition, and ES2015 is its year-based name. Later editions are named only by year.

**Q5. How often is a new ECMAScript edition released?**

**Answer:** Once a year, typically approved in June by the Ecma General Assembly.

### 🟡 Intermediate Questions

**Q6. Why is the language called ECMAScript and not JavaScript?**

**Answer:** "JavaScript" was a trademark, so the standard was published by Ecma International under the name ECMAScript.

**Q7. What is a JavaScript engine? Give examples.**

**Answer:** An engine is the program that parses and executes JavaScript code. Examples are V8 (Chrome and Node.js), SpiderMonkey (Firefox), and JavaScriptCore (Safari).

**Q8. Is `setTimeout` part of ECMAScript?**

**Answer:** No. `setTimeout`, `fetch`, `document`, and `console` are provided by the host environment (browser or Node.js), not the ECMAScript specification.

**Q9. Describe the stages of the TC39 process.**

**Answer:** Stage 0 (strawperson idea), Stage 1 (proposal with a champion), Stage 2 (draft specification), Stage 2.7 (approved design awaiting tests), Stage 3 (candidate being implemented), and Stage 4 (finished and ready for the next yearly edition).

**Q10. What happened to ES4?**

**Answer:** It was abandoned because its scope was too large and the committee could not agree on it. Development continued with ES5 and later ES2015.

**Q11. Name five major features introduced in ES2015.**

**Answer:** `let` and `const`, arrow functions, classes, template literals, destructuring, default/rest/spread, modules, promises, and `Map` and `Set` (any five).

**Q12. What is the difference between optional chaining `?.` and nullish coalescing `??`?**

**Answer:** `?.` safely accesses a property and returns `undefined` if something along the path is `null` or `undefined`. `??` returns its right-hand side only when the left side is `null` or `undefined`.

**Q13. Why can `??` be better than `||` for default values?**

**Answer:** `||` replaces every falsy value, including `0`, `""`, and `false`, which can be valid values. `??` replaces only `null` and `undefined`.

### 🔵 Practical and Advanced Questions

**Q14. What is the difference between a transpiler and a polyfill?**

**Answer:** A transpiler (like Babel) converts new syntax into older syntax at build time. A polyfill adds missing built-in methods or objects at runtime so that old environments can use new APIs.

**Q15. How do you safely use a very new feature that some browsers lack?**

**Answer:** Check compatibility tables (MDN, caniuse), use feature detection (such as `typeof Array.prototype.toSorted === "function"`), and add a transpiler or polyfill if the target browsers need it.

**Q16. Why can an arrow function be transpiled but `Array.prototype.at` cannot?**

**Answer:** An arrow function is new **syntax**, which a transpiler can rewrite into equivalent old syntax. `at` is a new **method**, so it must be provided at runtime by a polyfill.

**Q17. What is the output of the following code?**

```javascript
const volume = 0;
console.log(volume || 50);
console.log(volume ?? 50);
```

**Answer:** `50` and `0`. `||` treats `0` as falsy and replaces it, while `??` keeps it because it is neither `null` nor `undefined`.

**Q18. How is `toSorted()` different from `sort()`?**

**Answer:** `sort()` changes the original array, while `toSorted()` returns a new sorted array and leaves the original unchanged (ES2023).

**Q19. What is the advantage of `Error.isError()` over `instanceof Error`?**

**Answer:** `Error.isError()` reliably recognises error objects even when they come from a different realm (such as another iframe), where `instanceof Error` can fail.

**Q20. What problem does `Math.sumPrecise()` solve?**

**Answer:** Adding floating-point numbers one by one accumulates rounding errors (for example, `0.1 + 0.2 + 0.3` gives `0.6000000000000001`). `Math.sumPrecise()` sums an iterable of numbers with minimal precision loss.

**Q21. What is the difference between `Object.hasOwn()` and the `in` operator?**

**Answer:** `Object.hasOwn(obj, key)` checks only the object's own properties, while `key in obj` also checks inherited properties through the prototype chain.

**Q22. What is the significance of `type="module"` on a script tag?**

**Answer:** It tells the browser to treat the script as an ES module, enabling `import` and `export`, strict mode by default, and module-level scope.

---

## 🏆 12. Key Takeaways

- 📜 **ECMAScript** is the specification (ECMA-262); **JavaScript** is the language that implements it.
- 🏛️ **TC39** (inside **Ecma International**) designs the language, and a new edition is approved every **June**.
- 🛤️ A feature moves from Stage 0 to Stage 4 before joining the next edition.
- 🔢 **ES6 = ES2015**. Newer editions are named by year.
- 🌟 ES2015 was the huge turning point. ES2017 brought `async/await`, ES2020 brought `?.` and `??`, and ES2022 matured classes and top-level `await`.
- 🆕 **ES2026** (approved 30 June 2026) adds practical tools such as `Array.fromAsync()`, `Math.sumPrecise()`, `Iterator.concat()`, `Error.isError()`, `getOrInsert()`, `Uint8Array` base64/hex, and JSON source-text access.
- 🌐 `console`, `setTimeout`, `document`, `fetch`, and Node's `require` are **host features**, not ECMAScript.
- 🔧 Use **feature detection**, **transpilers** (for syntax), and **polyfills** (for methods) to support older environments.
- ✅ Always check **MDN** and **caniuse** before depending on a new feature.

---

### 🚀 Keep Practising!

> 💡 **Remember:** JavaScript keeps evolving every year, so the best habit is to learn the stable core well and check the compatibility tables before using the newest additions.

**Happy Coding! 💻✨**

---

## 📚 Sources

- [ECMAScript 2026 specification approved (InfoWorld)](https://www.infoworld.com/article/4193461/ecmascript-2026-specification-approved.html)
- [Ecma International approves new standards (1 July 2026)](https://ecma-international.org/?p=19624)
- [ECMA-262, 17th edition: ECMAScript 2026 Language Specification](https://262.ecma-international.org/17.0/index.html)
- [What's new in ECMAScript 2026 (Paweł Grzybek)](https://pawelgrzybek.com/whats-new-in-ecmascript-2026/)
- [ECMA 2026 Spec Approved (I Programmer)](https://www.i-programmer.info/news/167-javascript/18988-ecma-2026-spec-approved.html)
- [Les nouveautés d'ECMAScript 2026 (OpenReplay)](https://blog.openreplay.com/fr/nouveautes-ecmascript-2026/)
