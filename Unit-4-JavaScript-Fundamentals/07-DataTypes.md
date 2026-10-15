# 🗃️ JavaScript Data Types

> 🎯 **Learning Objectives**
> - Understand what a data type is and why it matters.
> - Identify the primitive and non-primitive data types.
> - Use the `typeof` operator and know its quirks.
> - Convert values from one type to another.
> - Understand truthy and falsy values.
> - Differentiate between primitive and reference types.

---

## 🌟 1. What is a Data Type?

A **data type** tells JavaScript what kind of value a variable holds, so it knows what you can do with it.

Think of **containers in a kitchen**. 🍳

| Container | What it holds | What you can do |
|---|---|---|
| 🫙 Sugar jar | Sugar | Measure it, add it |
| 🥛 Water bottle | Water | Pour it, drink it |
| 📒 Recipe book | Instructions | Read it, follow it |

Likewise, you can **add** two numbers, **join** two strings, and **check** a boolean as true or false.

### 🧠 Remember This!

- JavaScript is **dynamically typed**: you don't declare the type, and a variable can hold a different type later.
- Every value in JavaScript has a type.

---

## 🗂️ 2. Types at a Glance

| Category | Types |
|---|---|
| 🟢 **Primitive** (single, simple values) | `string`, `number`, `boolean`, `undefined`, `null`, `bigint`, `symbol` |
| 🔵 **Non-primitive** (collections and complex values) | `object` (including arrays and functions) |

---

## 🟢 3. Primitive Data Types

### 📝 String

Text, written inside single quotes, double quotes, or backticks.

```javascript
let name = "Aman";
let city = 'Delhi';
let greeting = `Hello, ${name}!`;

console.log(name);
console.log(greeting);
console.log(name.length);
```

### 📤 Output

```text
Aman
Hello, Aman!
4
```

### 🔢 Number

Used for both whole numbers and decimals.

```javascript
let age = 20;
let price = 99.5;

console.log(age + 5);
console.log(price * 2);
console.log(1 / 0);
console.log("abc" * 2);
```

### 📤 Output

```text
25
199
Infinity
NaN
```

### 🔍 Explanation

- JavaScript has **one** `number` type for integers and decimals.
- `Infinity` is the result of dividing by zero.
- `NaN` means **"Not a Number"**, and it is produced by invalid maths. Interestingly, `typeof NaN` is `"number"`.

### ✅ Boolean

Only two values: `true` or `false`. Used for decisions.

```javascript
let isStudent = true;
let isPassed = false;

console.log(isStudent);
console.log(5 > 3);
```

### 📤 Output

```text
true
true
```

### ❔ Undefined

A variable that has been declared but **not given a value**.

```javascript
let result;
console.log(result);
console.log(typeof result);
```

### 📤 Output

```text
undefined
undefined
```

### 🚫 Null

Represents an **intentional empty value**. You set it yourself to say "there is nothing here".

```javascript
let selectedCourse = null;
console.log(selectedCourse);
```

### 📤 Output

```text
null
```

### 🆚 `undefined` vs `null`

| `undefined` | `null` |
|---|---|
| JavaScript says "no value assigned yet" | The programmer says "intentionally empty" |
| Default value of unassigned variables | Must be assigned manually |

### 🔟 BigInt

For integers too large for the normal `number` type. Written with an `n` at the end.

```javascript
let big = 123456789012345678901234567890n;
console.log(big);
console.log(typeof big);
```

### 📤 Output

```text
123456789012345678901234567890n
bigint
```

### 🔣 Symbol

Creates a **unique** identifier. It is an advanced type that you will rarely need as a beginner.

```javascript
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 === id2);
```

### 📤 Output

```text
false
```

---

## 🔵 4. Non-Primitive Data Types

### 📚 Array

An ordered list of values.

```javascript
let colors = ["red", "green", "blue"];

console.log(colors[0]);
console.log(colors.length);
```

### 📤 Output

```text
red
3
```

> 💡 Array positions (indexes) start from **0**.

### 🧾 Object

A collection of **key-value pairs**.

```javascript
let student = {
    name: "Aman",
    age: 20,
    branch: "CSE"
};

console.log(student.name);
console.log(student["age"]);
```

### 📤 Output

```text
Aman
20
```

### ⚙️ Function

Functions are also objects in JavaScript, and `typeof` reports them as `"function"`.

```javascript
function greet() {
    return "Hello!";
}

console.log(typeof greet);
```

### 📤 Output

```text
function
```

---

## 🔍 5. The `typeof` Operator

```javascript
console.log(typeof "Hello");
console.log(typeof 42);
console.log(typeof true);
console.log(typeof undefined);
console.log(typeof 10n);
console.log(typeof Symbol("x"));
console.log(typeof { a: 1 });
console.log(typeof [1, 2, 3]);
console.log(typeof null);
```

### 📤 Output

```text
string
number
boolean
undefined
bigint
symbol
object
object
object
```

### ⚠️ Famous Quirks

| Expression | Result | Why |
|---|---|---|
| `typeof null` | `"object"` | A historic bug in JavaScript that was never fixed to avoid breaking old code |
| `typeof [1, 2, 3]` | `"object"` | Arrays are objects. Use `Array.isArray()` to check for arrays |

```javascript
console.log(Array.isArray([1, 2, 3]));
console.log(Array.isArray("hello"));
```

### 📤 Output

```text
true
false
```

---

## 🔄 6. Type Conversion

### 🔧 Explicit Conversion (you do it)

```javascript
console.log(Number("42"));
console.log(Number(""));
console.log(Number("abc"));
console.log(Number(true));

console.log(String(123));
console.log(String(true));

console.log(Boolean(0));
console.log(Boolean("hello"));
```

### 📤 Output

```text
42
0
NaN
1
123
true
false
true
```

### ✂️ `parseInt()` and `parseFloat()`

They read a number from the **start** of a string.

```javascript
console.log(parseInt("42px"));
console.log(parseFloat("3.14abc"));
console.log(parseInt("abc"));
```

### 📤 Output

```text
42
3.14
NaN
```

### 🤖 Implicit Conversion (JavaScript does it)

```javascript
console.log("5" + 3);
console.log("5" - 3);
console.log("5" * "2");
console.log(true + 1);
```

### 📤 Output

```text
53
2
10
2
```

> ⚠️ `+` with a string joins text. `-`, `*`, and `/` convert to numbers. When in doubt, convert explicitly.

---

## ⚖️ 7. Truthy and Falsy Values

In a condition, every value is treated as either **truthy** (acts like `true`) or **falsy** (acts like `false`).

### ❌ The Falsy Values (memorise these 8)

| Value | Type |
|---|---|
| `false` | boolean |
| `0` and `-0` | number |
| `0n` | bigint |
| `""` (empty string) | string |
| `null` | null |
| `undefined` | undefined |
| `NaN` | number |

✅ **Everything else is truthy**, including `"0"`, `"false"`, `[]` (empty array), and `{}` (empty object).

```javascript
if ("Hello") {
    console.log("Non-empty string is truthy ✅");
}

if (!0) {
    console.log("Zero is falsy ❌");
}

console.log(Boolean([]));
console.log(Boolean("0"));
```

### 📤 Output

```text
Non-empty string is truthy ✅
Zero is falsy ❌
true
true
```

---

## 🧬 8. Primitive vs Reference Types

### 🟢 Primitives are copied by **value**

```javascript
let x = 5;
let y = x;
y = 10;

console.log(x);
console.log(y);
```

### 📤 Output

```text
5
10
```

### 🔵 Objects and arrays are copied by **reference**

```javascript
let a = { score: 1 };
let b = a;
b.score = 99;

console.log(a.score);
console.log(b.score);
```

### 📤 Output

```text
99
99
```

### 🔍 Explanation

- A primitive variable holds the **value itself**, so `y` gets its own copy.
- An object variable holds a **reference** (like an address) to the object. `a` and `b` both point to the **same** object, so changing one changes the other.

💡 To make an independent copy of a simple object, use the spread syntax: `let b = { ...a };`

---

## ⚠️ 9. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Expecting `"5" + 3` to be `8` | Convert first: `Number("5") + 3` |
| Using `typeof` to check for an array or `null` | Use `Array.isArray(x)` or `x === null` |
| Confusing `null` and `undefined` | `undefined` = not assigned, `null` = intentionally empty |
| Treating `[]` or `"0"` as falsy | Both are truthy |
| Comparing with `NaN` using `===` | Use `Number.isNaN(value)` |
| Changing a copied object and being surprised the original changed | Objects are copied by reference |

---

## 🧪 10. Practice Tasks

- [ ] 🟢 **Beginner:** Create one variable of each primitive type (string, number, boolean, undefined, null) and print its `typeof`.
- [ ] 🟡 **Intermediate:** Predict the output: `console.log("10" + 5)`, `console.log("10" - 5)`, `console.log(true + true)`.
- [ ] 🟡 **Intermediate:** Convert the string `"150"` to a number and add `50` to it.
- [ ] 🔵 **Practice:** Create an object `student` with name, age, and branch, then print each property.
- [ ] 🔵 **Practice:** Tell which of these are falsy: `0`, `"0"`, `""`, `[]`, `null`, `NaN`.
- [ ] 🔴 **Challenge:** Create an object, copy it into another variable, change the copy, and explain why the original changed. Then fix it using the spread syntax.

---

## 🎤 11. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a data type?**

**Answer:** A data type defines the kind of value a variable holds and what operations can be performed on it.

**Q2. What are the primitive data types in JavaScript?**

**Answer:** `string`, `number`, `boolean`, `undefined`, `null`, `bigint`, and `symbol`.

**Q3. What is a non-primitive data type?**

**Answer:** A complex type such as an object (including arrays and functions) that can hold collections of values.

**Q4. What does it mean that JavaScript is dynamically typed?**

**Answer:** Variables are not bound to a specific type, so the same variable can hold different types of values at different times.

**Q5. Which operator is used to find the data type of a value?**

**Answer:** The `typeof` operator.

### 🟡 Intermediate Questions

**Q6. What is the difference between `null` and `undefined`?**

**Answer:** `undefined` means a variable has been declared but not assigned a value. `null` is an intentional "empty" value assigned by the programmer.

**Q7. What is `NaN`?**

**Answer:** `NaN` stands for "Not a Number". It is the result of an invalid numeric operation, such as `"abc" * 2`. Its type is `number`.

**Q8. What does `typeof null` return, and why?**

**Answer:** It returns `"object"`. This is a historic bug in JavaScript that has been kept for backward compatibility.

**Q9. How can you check whether a value is an array?**

**Answer:** Using `Array.isArray(value)`, because `typeof` returns `"object"` for arrays.

**Q10. What is the difference between `Number()` and `parseInt()`?**

**Answer:** `Number("42px")` gives `NaN` because the whole string must be numeric, while `parseInt("42px")` reads the number from the start and gives `42`.

**Q11. What are falsy values?**

**Answer:** Values that behave as `false` in a condition: `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, and `NaN`.

**Q12. What is the difference between implicit and explicit type conversion?**

**Answer:** Implicit conversion is done automatically by JavaScript (like `"5" - 3`), while explicit conversion is done by the programmer using functions like `Number()` or `String()`.

### 🔵 Practical Questions

**Q13. What is the output of `"5" + 3` and `"5" - 3`?**

**Answer:** `"53"` and `2`.

**Q14. What is the output of the following code?**

```javascript
let a = { n: 1 };
let b = a;
b.n = 2;
console.log(a.n);
```

**Answer:** `2`, because objects are copied by reference, so `a` and `b` point to the same object.

**Q15. Is an empty array `[]` truthy or falsy?**

**Answer:** Truthy. Only the eight falsy values behave as `false`.

**Q16. What is the difference between primitive and reference types?**

**Answer:** Primitives store the actual value and are copied by value. Objects and arrays store a reference to the data, so copies share the same underlying object.

---

## 🏆 12. Key Takeaways

- 🗃️ A data type defines the kind of value a variable holds.
- 🟢 Primitive types: string, number, boolean, undefined, null, bigint, symbol.
- 🔵 Objects (including arrays and functions) are non-primitive.
- 🔍 `typeof` is useful, but `typeof null` and `typeof []` both give `"object"`.
- 🔄 Convert types explicitly with `Number()`, `String()`, and `Boolean()` to avoid surprises.
- ⚖️ There are only eight falsy values; everything else is truthy.
- 🧬 Primitives are copied by value; objects are copied by reference.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Knowing your data types helps you predict what your code will do and avoid bugs before they happen.

**Happy Coding! 💻✨**
