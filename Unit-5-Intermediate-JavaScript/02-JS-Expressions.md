# 🧮 JavaScript Expressions

> 🎯 **Learning Objectives**
> - Differentiate precisely between an **expression** and a **statement**.
> - Identify the main kinds of expressions in JavaScript.
> - Understand operator **precedence**, **associativity**, and **order of evaluation**.
> - Use short-circuit evaluation (`&&`, `||`, `??`) and understand what these operators really return.
> - Predict the result of expressions that involve **type coercion**.
> - Understand assignment, increment, comma, `void`, and function expressions.
> - Avoid classic traps such as the object-literal ambiguity and mixing `??` with `||`.

---

## 🌟 1. What is an Expression?

An **expression** is any piece of code that **evaluates to a value**.

Think of a **calculator** and a **sentence**. 🧮

| Idea | Meaning | Example |
|---|---|---|
| 🧮 **Expression** | Something that *produces a value*, like a calculation | `2 + 3`, `"Hi".length`, `age >= 18` |
| 📝 **Statement** | A complete *instruction* that *performs an action* | `let x = 5;`, `if (...) { ... }`, `for (...) { ... }` |

### 🧠 The Golden Test

> **If you can put it inside `console.log( ... )` and it produces a value, it is an expression.**

```javascript
console.log(2 + 3);
console.log("Hi".length);
console.log(10 > 5);
console.log(typeof "text");
```

### 📤 Output

```text
5
2
true
string
```

### ❌ Statements are NOT Expressions

```javascript
console.log(let x = 5);
console.log(if (true) { 1 });
```

### 📤 Output

```text
SyntaxError: Unexpected token 'let'
```

(Both lines are errors because `let` and `if` are **statements**. They don't produce a value, so they can't be used where a value is expected.)

---

## 🧱 2. Expressions vs Statements: Where Does Each Belong?

JavaScript has places that **require an expression** and places that **require a statement**.

### ✅ Places That Expect an Expression

| Place | Example |
|---|---|
| Right side of `=` | `const total = price * qty;` |
| Function arguments | `console.log(a + b)` |
| `return` value | `return n * 2;` |
| Inside a template literal | `` `Total: ${price * qty}` `` |
| Array elements and object values | `[1 + 1, "a".toUpperCase()]` |
| Concise arrow body | `(n) => n * 2` |
| Conditions | `if (x > 5)`, `while (i < 10)`, `case` labels |

### 🔁 Expression Statements

Many expressions can also be used **as a statement** by themselves. These are called **expression statements**. They are usually written for their **side effect**, not their value.

```javascript
let count = 0;

count++;                    // expression statement (side effect: count changes)
console.log("Hello");       // expression statement (side effect: prints)
count += 5;                 // expression statement
```

### 🔄 Conditional Logic: `if` vs Ternary

```javascript
const age = 20;

// if is a STATEMENT, so it can't produce a value
let label1;
if (age >= 18) {
    label1 = "adult";
} else {
    label1 = "minor";
}

// ternary is an EXPRESSION, so it can be used directly where a value is needed
const label2 = age >= 18 ? "adult" : "minor";
console.log(`You are an ${age >= 18 ? "adult" : "minor"}`);
console.log(label1, label2);
```

### 📤 Output

```text
You are an adult
adult adult
```

---

## 🗂️ 3. Kinds of Expressions

| Kind | What it does | Examples |
|---|---|---|
| 🔹 **Primary** | The basic building blocks | `42`, `"text"`, `true`, `null`, `x`, `this`, `(a + b)` |
| 🔹 **Literal** | Creates a value directly | `[1, 2]`, `{ a: 1 }`, `/ab+c/`, `` `template` `` |
| 🔹 **Property access** | Reads a property | `obj.name`, `arr[0]`, `obj?.name` |
| 🔹 **Call / New** | Runs a function or constructor | `Math.max(1, 2)`, `new Date()` |
| 🔹 **Unary** | One operand | `!flag`, `-x`, `typeof x`, `x++`, `void 0`, `delete obj.k` |
| 🔹 **Arithmetic** | Maths | `a + b`, `a ** 2`, `a % 2` |
| 🔹 **Comparison** | Gives a boolean | `a > b`, `a === b` |
| 🔹 **Logical** | Combines values or conditions | `a && b`, `a \|\| b`, `a ?? b` |
| 🔹 **String** | Joins or builds text | `"a" + "b"`, `` `${a}-${b}` `` |
| 🔹 **Conditional (ternary)** | Chooses a value | `cond ? a : b` |
| 🔹 **Assignment** | Stores a value *and* produces one | `x = 5`, `x += 2`, `x ??= 0` |
| 🔹 **Function / Class** | Creates a function or class value | `function () {}`, `() => {}`, `class {}` |
| 🔹 **Comma** | Evaluates several, returns the last | `(a, b, c)` |
| 🔹 **Spread / Await** | Special expressions | `...arr`, `await promise` |

---

## ⚖️ 4. Operator Precedence and Associativity

**Precedence** decides which operator runs **first**. **Associativity** decides the direction when operators have **equal** precedence.

### 📊 Precedence (highest to lowest, simplified)

| Level | Operators | Notes |
|---|---|---|
| 1️⃣ | `( )` grouping | Always evaluated first |
| 2️⃣ | `.` `[ ]` `?.` function call `new` | Member access and calls |
| 3️⃣ | `x++` `x--` | Postfix |
| 4️⃣ | `!` `-` `+` `typeof` `void` `delete` `++x` `--x` `await` | Unary and prefix |
| 5️⃣ | `**` | **Right-associative** |
| 6️⃣ | `*` `/` `%` | |
| 7️⃣ | `+` `-` | |
| 8️⃣ | `<` `<=` `>` `>=` `in` `instanceof` | |
| 9️⃣ | `==` `!=` `===` `!==` | |
| 🔟 | `&&` | |
| 1️⃣1️⃣ | `\|\|` `??` | |
| 1️⃣2️⃣ | `? :` `=` `+=` `??=` arrow functions | **Right-associative** |
| 1️⃣3️⃣ | `,` comma | Lowest |

### 🔍 Precedence Examples

```javascript
console.log(2 + 3 * 4);
console.log((2 + 3) * 4);
console.log(2 + 3 * 4 ** 2);
console.log(true || false && false);
console.log((true || false) && false);
console.log(!true == false);
```

### 📤 Output

```text
14
20
50
true
false
true
```

### 🔍 Explanation

- `2 + 3 * 4 ** 2`: `**` first (16), then `*` (48), then `+` (50).
- `true || false && false`: `&&` runs before `||`, so it is `true || (false && false)`, which is `true`.
- `!true == false`: `!` runs first, so it is `false == false`, which is `true`.

### ↔️ Associativity

```javascript
console.log(10 - 5 - 2);
console.log(2 ** 3 ** 2);

let a, b, c;
a = b = c = 7;
console.log(a, b, c);
```

### 📤 Output

```text
3
512
7 7 7
```

| Case | How it is grouped | Result |
|---|---|---|
| `10 - 5 - 2` | Left to right: `(10 - 5) - 2` | `3` |
| `2 ** 3 ** 2` | Right to left: `2 ** (3 ** 2)` | `512` |
| `a = b = c = 7` | Right to left: `a = (b = (c = 7))` | all become `7` |

### 🪤 A Chain of Comparisons Doesn't Work Like Maths

```javascript
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```

### 📤 Output

```text
true
false
```

`3 > 2 > 1` is evaluated as `(3 > 2) > 1`, which is `true > 1`, then `1 > 1`, which is `false`. To check a range, write `x > 1 && x < 10`.

### 🪤 Unary Minus and `**`

```javascript
console.log((-2) ** 2);
console.log(-(2 ** 2));
// console.log(-2 ** 2);   // ❌ SyntaxError: the meaning is ambiguous
```

### 📤 Output

```text
4
-4
```

JavaScript refuses to guess what `-2 ** 2` should mean. You must add parentheses.

---

## 🔢 5. Order of Evaluation

Precedence decides **how operators group**. But **operands are always evaluated left to right**.

```javascript
function f(n) {
    console.log("f" + n);
    return n;
}

const result = f(1) + f(2) * f(3);
console.log(result);
```

### 📤 Output

```text
f1
f2
f3
7
```

### 🔍 Explanation

- All three calls run **in order**: `f1`, `f2`, `f3`.
- The multiplication is performed **after** its operands are ready, giving `1 + (2 * 3)`, which is `7`.
- Higher precedence does not make `f(2) * f(3)` run before `f(1)`.

---

## ➕ 6. Assignment Expressions

An assignment is an **expression**. It stores a value **and** produces that value.

```javascript
let x;

console.log(x = 10);
console.log(x += 5);
console.log(x *= 2);
console.log(x);

let y = null;
console.log(y ??= 42);
```

### 📤 Output

```text
10
15
30
30
42
```

### 🔁 Destructuring Assignment is an Expression Too

```javascript
let a = 1;
let b = 2;

[a, b] = [b, a];
console.log(a, b);
```

### 📤 Output

```text
2 1
```

### 🔄 A Useful (But Easy-to-Misuse) Pattern: Assignment in a Condition

```javascript
const queue = [1, 2, 3];
let item;

while ((item = queue.shift()) !== undefined) {
    console.log("Processing", item);
}
```

### 📤 Output

```text
Processing 1
Processing 2
Processing 3
```

The extra parentheses show that the assignment is **intentional**.

### 🪤 The Accidental Assignment Bug

```javascript
let n = 3;

if (n = 5) {
    console.log("always runs");
}
console.log(n);
```

### 📤 Output

```text
always runs
5
```

`n = 5` **assigns** and produces `5` (truthy). Use `n === 5` to compare.

---

## 🔼 7. Increment and Decrement Expressions

| Form | Name | Returns | Then... |
|---|---|---|---|
| `x++` | Postfix | The **old** value | increases `x` |
| `++x` | Prefix | The **new** value | (already increased) |

```javascript
let i = 5;

console.log(i++);
console.log(i);
console.log(++i);

let j = 5;
console.log(j++ + ++j);
console.log(j);
```

### 📤 Output

```text
5
6
7
12
7
```

### 🔍 Explanation of `j++ + ++j`

1. `j++` returns `5`, then `j` becomes `6`.
2. `++j` makes `j` become `7`, and returns `7`.
3. `5 + 7 = 12`, and `j` is now `7`.

> ⚠️ Mixing several increments in one expression is **legal but confusing**. Write them on separate lines in real code.

---

## 🔀 8. Short-Circuit Evaluation and What `&&`, `||`, `??` Really Return

Logical operators do **not** always return `true` or `false`. They return **one of the operands**, and they **stop evaluating** as soon as the answer is known.

| Operator | Returns | Evaluates the right side only if the left is... |
|---|---|---|
| `a && b` | `a` if `a` is falsy, otherwise `b` | **truthy** |
| `a \|\| b` | `a` if `a` is truthy, otherwise `b` | **falsy** |
| `a ?? b` | `a` if `a` is not `null`/`undefined`, otherwise `b` | `null` or `undefined` |

```javascript
console.log("Aman" || "Guest");
console.log("" || "Guest");
console.log(0 && "yes");
console.log(1 && "yes");
console.log(0 ?? "default");
console.log(null ?? "default");
console.log(false || null);
```

### 📤 Output

```text
Aman
Guest
0
yes
0
default
null
```

### 👀 Seeing Short-Circuiting in Action

```javascript
const check = (v) => {
    console.log("check", v);
    return v;
};

console.log(check(0) && check(1));
console.log(check(1) || check(2));
console.log(check(0) || check(2));
```

### 📤 Output

```text
check 0
0
check 1
1
check 0
check 2
2
```

### 🛠️ Practical Patterns

```javascript
const user = { name: "Riya" };

// Guard: only read the property if user exists
console.log(user && user.name);

// Default value for missing data
const nickname = user.nickname ?? "No nickname";
console.log(nickname);

// Run something only when a condition is true
const isAdmin = true;
isAdmin && console.log("Admin tools loaded");

// Optional chaining and optional call
console.log(user.address?.city);
console.log(user.sayHi?.());
```

### 📤 Output

```text
Riya
No nickname
Admin tools loaded
undefined
undefined
```

### 🪤 You Cannot Mix `??` with `||` or `&&` Without Parentheses

```javascript
const a = null, b = 0, c = "x";

// console.log(a ?? b || c);        // ❌ SyntaxError
console.log((a ?? b) || c);
console.log(a ?? (b || c));
```

### 📤 Output

```text
x
x
```

JavaScript forces you to add parentheses so the meaning is never ambiguous.

---

## 🔄 9. Type Coercion Inside Expressions

Operators convert values automatically when the types don't match. This is where most "JavaScript is weird" jokes come from.

### ➕ The `+` Operator

| Rule | Example | Result |
|---|---|---|
| If **either** side is a string → joins text | `"5" + 2` | `"52"` |
| Otherwise → converts to numbers and adds | `true + 1` | `2` |

```javascript
console.log("5" + 2);
console.log("5" - 2);
console.log("5" * "2");
console.log(+"5");
console.log(true + 1);
console.log(null + 1);
console.log(undefined + 1);
console.log([] + []);
console.log([] + {});
console.log("b" + "a" + +"a" + "a");
```

### 📤 Output

```text
52
3
10
5
2
1
NaN

[object Object]
baNaNa
```

(The `[] + []` line prints an empty string, which looks like a blank line.)

### ⚖️ Comparison: Strings vs Numbers

```javascript
console.log(10 > "9");
console.log("10" > "9");
console.log("abc" < "abd");
console.log(0.1 + 0.2 === 0.3);
console.log(NaN === NaN);
console.log(Object.is(NaN, NaN));
```

### 📤 Output

```text
true
false
true
false
false
true
```

| Expression | Why |
|---|---|
| `10 > "9"` | One side is a number, so `"9"` becomes `9`. |
| `"10" > "9"` | Both are strings, so they are compared **alphabetically**: `"1"` comes before `"9"`. |
| `"abc" < "abd"` | Alphabetical comparison. |
| `0.1 + 0.2 === 0.3` | Floating-point rounding: `0.30000000000000004` is not `0.3`. |
| `NaN === NaN` | `NaN` is never equal to anything, even itself. |
| `Object.is(NaN, NaN)` | `Object.is` treats `NaN` as the same as `NaN`. |

### 🎭 Equality vs Comparison: The `null` Puzzle

```javascript
console.log(null == 0);
console.log(null > 0);
console.log(null >= 0);
console.log(null == undefined);
console.log(null === undefined);
```

### 📤 Output

```text
false
false
true
true
false
```

`==` has a special rule: `null` equals only `undefined` (and itself). But `>=` converts `null` to `0`, so `null >= 0` is `true`.

### 🧪 Truthiness in Expressions

```javascript
console.log(!!"0");
console.log(!!"");
console.log(!![]);
console.log(!!{});
console.log(!!NaN);
console.log([] == false);
```

### 📤 Output

```text
true
false
true
true
false
true
```

> 💡 `[] == false` is `true` because `[]` converts to `""`, then to `0`, and `false` converts to `0`. This is why `===` is recommended.

---

## 🧩 10. Function Expressions

A function can be written as an **expression**, which makes it a value.

```javascript
const add = function (a, b) {        // anonymous function expression
    return a + b;
};

const factorial = function inner(n) {   // NAMED function expression
    return n <= 1 ? 1 : n * inner(n - 1);
};

console.log(add(2, 3));
console.log(factorial(5));
console.log(typeof inner);
```

### 📤 Output

```text
5
120
undefined
```

The name `inner` is visible **only inside the function**, which is useful for recursion and for clearer stack traces.

### ⚡ IIFE: Why the Parentheses Matter

```javascript
const result = (function () {
    return 42;
})();

console.log(result);

// function () { return 42; }();   // ❌ SyntaxError: at the start of a statement
```

### 📤 Output

```text
42
```

At the **start of a statement**, `function` is read as a **declaration**, which needs a name and cannot be called immediately. The surrounding parentheses force JavaScript to read it as an **expression**.

### 🪤 Arrow Functions That Return Objects

```javascript
const makePoint = (x, y) => ({ x, y });
const broken = (x, y) => { x, y };

console.log(makePoint(1, 2));
console.log(broken(1, 2));
```

### 📤 Output

```text
{ x: 1, y: 2 }
undefined
```

### 🔍 Explanation

- After `=>`, a `{` starts a **function body** (a block), not an object.
- In `broken`, `{ x, y }` is a block containing the comma expression `x, y`, with no `return`, so the result is `undefined`.
- Wrapping the object in **parentheses** turns it into an expression: `({ x, y })`.

---

## 🧾 11. Other Useful Expressions

### 🧵 Template Literal Expressions

```javascript
const price = 250;
const qty = 3;

console.log(`Total: ${price * qty}`);
console.log(`Status: ${qty > 2 ? "bulk" : "single"}`);
console.log(`2 + 3 = ${2 + 3}`);
```

### 📤 Output

```text
Total: 750
Status: bulk
2 + 3 = 5
```

Anything inside `${ }` can be **any expression**.

### 🔗 Array and Object Literals Contain Expressions

```javascript
const key = "k";

console.log([1 + 1, "a".toUpperCase(), 3 > 2]);
console.log({ [key + 1]: 1 + 1, upper: "x".toUpperCase() });
```

### 📤 Output

```text
[ 2, 'A', true ]
{ k1: 2, upper: 'X' }
```

### 🧬 Property Access, Calls, and `new`

```javascript
console.log("hello".toUpperCase().slice(0, 3));
console.log(new Date(2026, 0, 1).getFullYear());
console.log(Math.max(...[4, 9, 2]));
```

### 📤 Output

```text
HEL
2026
9
```

### 🕵️ Unary and Relational Operators as Expressions

```javascript
const obj = { name: "Aman", age: 20 };

console.log(typeof null);
console.log("name" in obj);
console.log([] instanceof Array);
console.log(delete obj.age);
console.log(obj);
```

### 📤 Output

```text
object
true
true
true
{ name: 'Aman' }
```

### 🎩 The Comma Operator

Evaluates each expression left to right and returns the **last** one.

```javascript
const x = (1, 2, 3);
console.log(x);

let a = 0;
const y = (a++, a++, a);
console.log(y);
```

### 📤 Output

```text
3
2
```

> ⚠️ Rarely useful. Don't confuse it with the **commas in function arguments** or array literals, which are just separators.

### 🕳️ The `void` Operator

Evaluates an expression and always returns `undefined`.

```javascript
console.log(void 0);
console.log(void "anything");
console.log(typeof void 0);
```

### 📤 Output

```text
undefined
undefined
undefined
```

---

## 🛒 12. Mini Example: Order Summary Using Only Expressions

```javascript
const order = {
    items: [
        { price: 250, qty: 2 },
        { price: 100, qty: 1 }
    ],
    coupon: null
};

const subtotal = order.items.reduce((sum, i) => sum + i.price * i.qty, 0);
const discountRate = subtotal >= 500 ? 0.1 : 0;
const discount = Math.round(subtotal * discountRate);
const coupon = order.coupon ?? "NONE";
const total = subtotal - discount;

console.log(`Subtotal: ${subtotal}`);
console.log(`Coupon: ${coupon}`);
console.log(`Discount: ${discount}`);
console.log(`Total: ${total}`);
```

### 📤 Output

```text
Subtotal: 600
Coupon: NONE
Discount: 60
Total: 540
```

### 🔍 Expressions Used

| Expression | Kind |
|---|---|
| `sum + i.price * i.qty` | Arithmetic (with precedence) |
| `subtotal >= 500 ? 0.1 : 0` | Conditional (ternary) |
| `order.coupon ?? "NONE"` | Nullish coalescing |
| `` `Subtotal: ${subtotal}` `` | Template literal containing expressions |
| `Math.round(...)` | Call expression |

---

## 🎯 13. Predict the Output

Try to answer **before** looking at the solution.

```javascript
// 1
console.log(1 + 2 + "3");

// 2
console.log("1" + 2 + 3);

// 3
console.log(2 + 3 * 2 ** 2);

// 4
console.log(null ?? undefined ?? "end");

// 5
let n = 1;
console.log(n++ + n++);

// 6
console.log(typeof (1 + "2"));

// 7
console.log([10, 9, 1].sort());

// 8
console.log(0 || null || "x" || "y");
```

### ✅ Solution

| # | Output | Reason |
|---|---|---|
| 1 | `33` | `1 + 2` = `3`, then `3 + "3"` joins to `"33"` |
| 2 | `123` | `"1" + 2` = `"12"`, then `"12" + 3` = `"123"` |
| 3 | `14` | `2 ** 2` = 4, `3 * 4` = 12, `2 + 12` = 14 |
| 4 | `end` | `??` skips `null` and `undefined` |
| 5 | `3` | First `n++` returns 1 (n becomes 2), second returns 2, and `1 + 2` = 3 |
| 6 | `string` | `1 + "2"` is `"12"` |
| 7 | `[ 1, 10, 9 ]` | `sort()` compares as strings by default |
| 8 | `x` | `||` returns the first truthy operand |

---

## ⚠️ 14. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Calling `if` or `let` an expression | They are **statements**. Use the ternary operator for a value |
| `1 < x < 10` for a range | `x > 1 && x < 10` |
| `if (x = 5)` | `if (x === 5)` |
| `"5" + 2` expecting `7` | Convert first: `Number("5") + 2` |
| Using `\|\|` for defaults when `0` or `""` is valid | Use `??` |
| `a ?? b \|\| c` with no parentheses | Add parentheses: `(a ?? b) \|\| c` |
| `-2 ** 2` | `(-2) ** 2` or `-(2 ** 2)` |
| `=> { x, y }` to return an object | `=> ({ x, y })` |
| Writing `function(){}()` at the start of a line | Wrap in parentheses: `(function(){})()` |
| Packing several `++` in one expression | Use separate lines |
| Comparing `NaN === NaN` | Use `Number.isNaN(x)` or `Object.is` |
| Assuming precedence also controls the order functions run | Operands are always evaluated left to right |

---

## 🧪 15. Practice Tasks

- [ ] 🟢 **Beginner:** Write five different expressions (one arithmetic, one comparison, one logical, one string, one ternary) and print their results.
- [ ] 🟢 **Beginner:** Classify each as expression or statement: `5 + 5`, `let a = 5;`, `a > 3`, `if (a) {}`, `a = 7`, `typeof a`.
- [ ] 🟡 **Intermediate:** Predict, then check: `console.log(2 ** 3 ** 2, (2 ** 3) ** 2, 10 - 4 - 3)`.
- [ ] 🟡 **Intermediate:** Rewrite `if (user !== null && user !== undefined) name = user.name; else name = "Guest";` as **one expression** using `?.` and `??`.
- [ ] 🔵 **Practice:** Write `let a = 1, b = 2; ` and swap their values without a temporary variable, using a destructuring assignment expression.
- [ ] 🔵 **Practice:** Create a function `isBetween(x, min, max)` that returns a boolean using a single logical expression.
- [ ] 🔵 **Practice:** Use the helper `check(v)` from section 8 to prove which operand `a && b || c` evaluates for different values of `a`, `b`, and `c`.
- [ ] 🔴 **Challenge:** Explain, step by step, why `null >= 0` is `true` while `null == 0` is `false`.
- [ ] 🔴 **Challenge:** Write a one-line arrow function `fullName(first, last)` that returns an object `{ first, last, full }`, where `full` is a template literal. Make sure it returns the object correctly.
- [ ] 🔴 **Challenge:** Without running it, predict the output of the following, then verify it and explain each result: `console.log([] + [], [] + {}, +[], +{}, [] == "")`.

---

## 🎤 16. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is an expression in JavaScript?**

**Answer:** An expression is any piece of code that evaluates to a value, such as `2 + 3`, `"Hi".length`, or `age >= 18`.

**Q2. What is the difference between an expression and a statement?**

**Answer:** An expression produces a value, while a statement performs an action and does not produce a value that can be used directly. For example, `a > 3` is an expression and `if (a > 3) { ... }` is a statement.

**Q3. Give examples of expressions and statements.**

**Answer:** Expressions: `5 + 5`, `x * 2`, `typeof x`, `a ? b : c`. Statements: `let x = 5;`, `if`, `for`, `while`, `return`.

**Q4. What is an expression statement?**

**Answer:** An expression used as a statement on its own, usually for its side effect, such as `count++;` or `console.log("Hi");`.

**Q5. Is `x = 5` an expression? What does it evaluate to?**

**Answer:** Yes. An assignment is an expression that stores the value and also evaluates to that assigned value (`5`).

### 🟡 Intermediate Questions

**Q6. What is operator precedence? What is associativity?**

**Answer:** Precedence determines which operator is applied first when an expression has several operators. Associativity decides the direction (left to right or right to left) for operators of equal precedence.

**Q7. Which operators are right-associative?**

**Answer:** The exponent operator `**`, the assignment operators (`=`, `+=`, `??=`, and so on), and the conditional (ternary) operator.

**Q8. What is the value of `2 ** 3 ** 2`?**

**Answer:** `512`, because `**` is right-associative, so it is evaluated as `2 ** (3 ** 2)`.

**Q9. Does higher precedence mean an operator's operands are evaluated first?**

**Answer:** No. Operands are always evaluated from left to right. Precedence only decides how the operators group. For example, in `f(1) + f(2) * f(3)`, the functions run in the order `f(1)`, `f(2)`, `f(3)`.

**Q10. What is short-circuit evaluation?**

**Answer:** The logical operators `&&`, `||`, and `??` stop evaluating as soon as the result is determined, so the right-hand side may never run.

**Q11. What do `&&` and `||` actually return?**

**Answer:** They return one of their operands, not necessarily a boolean. `a && b` returns `a` if `a` is falsy, otherwise `b`. `a || b` returns `a` if `a` is truthy, otherwise `b`.

**Q12. What is the difference between `||` and `??`?**

**Answer:** `||` falls back for any falsy value (`0`, `""`, `false`, `null`, `undefined`, `NaN`), while `??` falls back only for `null` and `undefined`.

**Q13. Why is `a ?? b || c` a syntax error?**

**Answer:** The language forbids mixing `??` with `||` or `&&` without parentheses to avoid ambiguity. You must write `(a ?? b) || c` or `a ?? (b || c)`.

**Q14. What is the difference between `x++` and `++x` as expressions?**

**Answer:** `x++` evaluates to the old value and then increments `x`. `++x` increments `x` first and evaluates to the new value.

### 🔵 Practical and Advanced Questions

**Q15. What is the output of `1 + 2 + "3"` and `"1" + 2 + 3`?**

**Answer:** `"33"` and `"123"`. In the first, `1 + 2` is added numerically before the string is involved. In the second, the leftmost `+` already has a string, so all remaining `+` operations join text.

**Q16. Why does `3 > 2 > 1` evaluate to `false`?**

**Answer:** It is evaluated as `(3 > 2) > 1`, which becomes `true > 1`, then `1 > 1`, which is `false`. Comparisons do not chain like in maths.

**Q17. Why is `null >= 0` true but `null == 0` false?**

**Answer:** Relational operators (`>=`) convert `null` to the number `0`, so `0 >= 0` is true. The loose equality operator `==` has a special rule where `null` is equal only to `undefined` (and itself), so `null == 0` is false.

**Q18. Why do arrow functions need parentheses to return an object literal directly?**

**Answer:** After `=>`, a `{` begins a function body (a block), not an object. Writing `() => ({ a: 1 })` wraps the object in parentheses so it is parsed as an expression.

**Q19. Why must an IIFE be wrapped in parentheses?**

**Answer:** At the beginning of a statement, `function` is parsed as a declaration, which requires a name and cannot be invoked directly. Wrapping it in parentheses makes it a function expression that can be called immediately.

**Q20. What is the difference between a function declaration and a function expression?**

**Answer:** A declaration is a statement that defines a named function and is hoisted. An expression produces a function value, can be anonymous or named, can be assigned or passed around, and is not hoisted in the same way.

**Q21. What is a named function expression and why use it?**

**Answer:** A function expression with its own name, such as `const f = function inner() {}`. The name is only visible inside the function, which allows recursion and gives clearer stack traces.

**Q22. What does the comma operator do?**

**Answer:** It evaluates each operand from left to right and returns the value of the last one. For example, `(1, 2, 3)` evaluates to `3`.

**Q23. What does the `void` operator return?**

**Answer:** Always `undefined`, after evaluating its operand. For example, `void 0` is `undefined`.

**Q24. Why does `-2 ** 2` throw a `SyntaxError`?**

**Answer:** It is ambiguous whether the minus applies before or after the exponent, so JavaScript requires parentheses: `(-2) ** 2` gives `4`, and `-(2 ** 2)` gives `-4`.

---

## 🏆 17. Key Takeaways

- 🧮 An **expression produces a value**. A **statement performs an action**. Use `console.log( ... )` as a quick test.
- 🔁 Many expressions can be written as **expression statements** (like `count++;`) for their side effects.
- ⚖️ **Precedence** decides grouping, and **associativity** decides direction. `**`, assignment, and `?:` are right-associative.
- 🔢 **Operands are evaluated left to right**, no matter how operators group.
- 🔀 `&&`, `||`, and `??` **short-circuit** and return an **operand**, not always a boolean.
- 🧩 Don't mix `??` with `||` or `&&` without parentheses.
- 🔄 Type coercion rules (especially `+`, `==`, and comparisons) cause most surprising results. Prefer `===` and explicit conversion.
- 🪤 Remember the traps: `if (x = 5)`, chained comparisons, `-2 ** 2`, `=> { x, y }`, and un-parenthesised IIFEs.
- ➡️ Assignments, function expressions, template literals, and ternaries are all expressions, so they can be used anywhere a value is expected.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Whenever you are unsure what a line will do, ask two questions: **"What does each part evaluate to?"** and **"In what order?"**

**Happy Coding! 💻✨**
