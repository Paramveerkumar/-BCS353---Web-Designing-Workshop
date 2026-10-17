# ⚙️ JavaScript Operators (Intermediate)

> 🎯 **Learning Objectives**
> - Classify operators by number of operands (unary, binary, ternary).
> - Handle arithmetic edge cases: negative remainders, integer division, floating-point error, and `BigInt`.
> - Compare values correctly using `===`, `==`, `Object.is()`, and `localeCompare()`.
> - Understand how objects behave in arithmetic through `valueOf()` and `toString()`.
> - Use De Morgan's laws to simplify conditions.
> - Use bitwise operators for flags, parity, and powers of two.
> - Use `typeof`, `instanceof`, `in`, and `delete` accurately, including their quirks.
> - Avoid precedence traps in real code.

---

## 🌟 1. Classifying Operators

### 🔢 By Number of Operands

| Type | Operands | Examples |
|---|---|---|
| **Unary** | 1 | `!x`, `-x`, `+x`, `~x`, `typeof x`, `x++`, `delete obj.k`, `void 0`, `await p` |
| **Binary** | 2 | `a + b`, `a === b`, `a && b`, `a in obj`, `a instanceof B`, `a ?? b` |
| **Ternary** | 3 | `condition ? a : b` (the only ternary operator) |

### 🗂️ By Purpose

| Category | Operators |
|---|---|
| ➕ Arithmetic | `+  -  *  /  %  **  ++  --` and unary `+  -` |
| ✏️ Assignment | `=  +=  -=  *=  /=  %=  **=  &=  \|=  ^=  <<=  >>=  >>>=  &&=  \|\|=  ??=` |
| ⚖️ Comparison | `==  !=  ===  !==  <  >  <=  >=` |
| 🔀 Logical | `&&  \|\|  !  ??` |
| 🧮 Bitwise | `&  \|  ^  ~  <<  >>  >>>` |
| 🔍 Type and relational | `typeof  instanceof  in  delete  void` |
| 🧵 String | `+` and `+=` |
| 🛟 Safe access | `?.` (optional chaining) |
| 🎩 Other | `? :`, `,`, `...` (spread/rest), `new`, `await`, `yield` |

> 💡 JavaScript has **no operator overloading**. You cannot redefine `+` for your own classes, but you *can* influence how objects convert to primitives (section 5).

---

## ➕ 2. Arithmetic Operators: Edge Cases

### 🔁 The `%` Operator Gives a **Remainder**, Not a Mathematical Modulo

The result takes the **sign of the left operand (dividend)**.

```javascript
console.log(7 % 3);
console.log(-7 % 3);
console.log(7 % -3);
console.log(5.5 % 2);
console.log(5 % 0);
```

### 📤 Output

```text
1
-1
1
1.5
NaN
```

### 🛠️ True Modulo (Always Non-Negative for a Positive Divisor)

```javascript
const mod = (n, m) => ((n % m) + m) % m;

console.log(mod(-7, 3));
console.log(mod(-1, 5));
console.log(mod(7, 3));
```

### 📤 Output

```text
2
4
1
```

> 💡 This matters for **wrap-around logic** such as carousels, clocks, and circular buffers.

### ➗ There is No Integer Division Operator

`/` always gives a floating-point result. Choose the rounding that you need.

```javascript
console.log(7 / 2);
console.log(Math.trunc(7 / 2));
console.log(Math.floor(-7 / 2));
console.log(Math.trunc(-7 / 2));
```

### 📤 Output

```text
3.5
3
-4
-3
```

| Function | Rounds | `-3.5` becomes |
|---|---|---|
| `Math.trunc` | Towards zero | `-3` |
| `Math.floor` | Down | `-4` |
| `Math.ceil` | Up | `-3` |
| `Math.round` | To nearest | `-3` |

### ♾️ Division by Zero Does Not Throw

```javascript
console.log(5 / 0);
console.log(-5 / 0);
console.log(0 / 0);
console.log(Number.isFinite(5 / 0));
```

### 📤 Output

```text
Infinity
-Infinity
NaN
false
```

### ⚡ Exponent `**`

```javascript
console.log(2 ** 10);
console.log(2 ** -1);
console.log(2 ** 0.5);
console.log((-8) ** (1 / 3));
```

### 📤 Output

```text
1024
0.5
1.4142135623730951
NaN
```

A negative base with a fractional exponent gives `NaN`. Use `Math.cbrt(-8)` (which gives `-2`) for cube roots.

### 🧮 Floating-Point Precision

```javascript
console.log(0.1 + 0.2);
console.log(0.1 * 3);
console.log(0.1 + 0.2 === 0.3);
console.log(Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON);
console.log((0.1 + 0.2).toFixed(2));
console.log(+(0.1 + 0.2).toFixed(2));
```

### 📤 Output

```text
0.30000000000000004
0.30000000000000004
false
true
0.30
0.3
```

### 🔍 Explanation

- Numbers are stored in binary (IEEE 754), so many decimals cannot be stored exactly.
- Compare floating-point numbers with a **tolerance** (`Number.EPSILON`), not with `===`.
- `toFixed(2)` returns a **string**. Use unary `+` to turn it back into a number.
- For **money**, store the amount as an integer number of the smallest unit (paise or cents) and divide only when displaying.

### 🔢 Safe Integer Limits and `BigInt`

```javascript
console.log(Number.MAX_SAFE_INTEGER);
console.log(Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2);
console.log(BigInt(Number.MAX_SAFE_INTEGER) + 2n);
console.log(2n ** 64n);
// console.log(1n + 1);   // ❌ TypeError
```

### 📤 Output

```text
9007199254740991
true
9007199254740993n
18446744073709551616n
```

```text
TypeError: Cannot mix BigInt and other types, use explicit conversions
```

Operators such as `+` and `*` do **not** mix `BigInt` and `Number`. Convert one explicitly, for example `Number(1n) + 1` or `1n + BigInt(1)`.

### ➕ Unary `+` and `-`

Unary `+` is the shortest way to convert a value to a number.

```javascript
console.log(+"42");
console.log(+"");
console.log(+"abc");
console.log(+true);
console.log(+null);
console.log(+undefined);
console.log(-"5");

let s = "5";
s++;
console.log(s, typeof s);
```

### 📤 Output

```text
42
0
NaN
1
0
NaN
-5
6 number
```

`++` and `--` always convert their operand to a number, even if it started as a string.

---

## ✏️ 3. Assignment Operators: The Full Family

```javascript
let x = 10;

x -= 3;   console.log(x);
x *= 2;   console.log(x);
x **= 2;  console.log(x);
x %= 50;  console.log(x);
x /= 4;   console.log(x);
```

### 📤 Output

```text
7
14
196
46
11.5
```

### 🔤 Compound Assignment Works on Strings Too

```javascript
let text = "Hello";
text += ", ";
text += "World";
console.log(text);
```

### 📤 Output

```text
Hello, World
```

### 🔀 Logical Assignment (Recap)

| Operator | Assigns only if the left side is... | Typical use |
|---|---|---|
| `a \|\|= b` | falsy | Fill an empty value |
| `a &&= b` | truthy | Transform an existing value |
| `a ??= b` | `null` or `undefined` | Set a default |

```javascript
const config = { retries: 0, name: "" };

config.retries ||= 3;
config.name ??= "default";
config.timeout ??= 5000;

console.log(config);
```

### 📤 Output

```text
{ retries: 3, name: '', timeout: 5000 }
```

`retries` was `0` (falsy), so `||=` replaced it, which may be a bug if `0` is valid. `name` is `""`, which is **not** `null` or `undefined`, so `??=` kept it.

### 🪤 Chained `let` Creates an Accidental Global

```javascript
// let a = b = 5;    // ❌ Declares 'a' but assigns to an UNDECLARED 'b'
let a, b;
a = b = 5;           // ✅ declare both first
console.log(a, b);
```

### 📤 Output

```text
5 5
```

In `let a = b = 5;`, only `a` is declared. In sloppy mode `b` silently becomes a **global variable**, and in strict mode it throws a `ReferenceError`.

---

## ⚖️ 4. Comparison Operators in Depth

### 🆚 Three Kinds of "Equal"

| Check | `NaN` vs `NaN` | `0` vs `-0` | Converts types? |
|---|---|---|---|
| `==` | `false` | `true` | ✅ Yes |
| `===` | `false` | `true` | ❌ No |
| `Object.is()` | **`true`** | **`false`** | ❌ No |

```javascript
console.log(NaN === NaN);
console.log(Object.is(NaN, NaN));
console.log(0 === -0);
console.log(Object.is(0, -0));
console.log([NaN].includes(NaN));
console.log([NaN].indexOf(NaN));
```

### 📤 Output

```text
false
true
true
false
true
-1
```

`includes()` uses the "same-value-zero" rule, which finds `NaN`, but `indexOf()` uses `===` and cannot.

### 🔍 Checking for `NaN`

```javascript
console.log(isNaN("abc"));
console.log(Number.isNaN("abc"));
console.log(Number.isNaN(NaN));
```

### 📤 Output

```text
true
false
true
```

Global `isNaN()` **converts** its argument first, so a string like `"abc"` gives `true`. `Number.isNaN()` is strict and only gives `true` for the actual value `NaN`. Prefer `Number.isNaN()`.

### 📋 Loose Equality (`==`) Cheat Sheet

```javascript
console.log("1" == 1);
console.log(0 == "");
console.log(0 == "0");
console.log("" == "0");
console.log(false == "0");
console.log(false == "false");
console.log(null == undefined);
console.log(null == false);
console.log([] == "");
console.log([1, 2] == "1,2");
console.log([] == ![]);
```

### 📤 Output

```text
true
true
true
false
true
false
true
false
true
true
true
```

| Rule | Example |
|---|---|
| String vs number → string becomes a number | `"1" == 1` |
| Boolean → converted to a number first | `false == "0"` (both become `0`) |
| `null` equals only `undefined` (and itself) | `null == false` is `false` |
| Both strings → plain string comparison (no conversion) | `"" == "0"` is `false` |
| Object vs primitive → object converted to a primitive | `[1, 2] == "1,2"` |

✅ **Rule of thumb:** use `===`. The one accepted use of `==` is `value == null`, which checks for `null` or `undefined` together.

### 🧱 Objects Are Compared by Reference

```javascript
const a = [1, 2];
const b = [1, 2];
const c = a;

console.log(a === b);
console.log(a === c);
console.log(JSON.stringify(a) === JSON.stringify(b));
```

### 📤 Output

```text
false
true
true
```

`JSON.stringify` comparison is a quick trick for simple data, but it fails for functions, `undefined`, and different key orders.

### 🔤 Comparing Strings

Relational operators compare strings **character code by character code** (alphabetically for similar case, but with uppercase before lowercase).

```javascript
console.log("apple" < "banana");
console.log("Zebra" < "apple");
console.log("10" < "9");
console.log(10 < "9");

console.log("apple".localeCompare("banana"));
console.log("banana".localeCompare("apple"));
console.log("a".localeCompare("a"));

console.log(["b", "a", "C"].sort());
console.log(["b", "a", "C"].sort((x, y) => x.localeCompare(y)));
```

### 📤 Output

```text
true
true
true
false
-1
1
0
[ 'C', 'a', 'b' ]
[ 'a', 'b', 'C' ]
```

Use `localeCompare()` for human-friendly (and language-aware) sorting.

### 📅 Comparing Dates

```javascript
const d1 = new Date("2026-01-01");
const d2 = new Date("2026-01-01");
const d3 = new Date("2026-01-02");

console.log(d1 < d3);
console.log(d1 === d2);
console.log(+d1 === +d2);
console.log(d3 - d1);
```

### 📤 Output

```text
true
false
true
86400000
```

Dates are objects, so `===` compares **references**. Relational operators and subtraction convert dates to **milliseconds**, so `d3 - d1` gives the difference in milliseconds (86,400,000 ms = 1 day).

### 🪤 `NaN` and `undefined` in Comparisons

```javascript
console.log(NaN < 1, NaN > 1, NaN == NaN);
console.log(undefined > 0, undefined < 0, undefined == 0);
```

### 📤 Output

```text
false false false
false false false
```

Any comparison involving `NaN` is `false`. `undefined` converts to `NaN` in relational comparisons.

---

## 🎭 5. Objects in Operators: `valueOf()` and `toString()`

When an object is used with an operator, JavaScript converts it to a primitive by calling `valueOf()` and/or `toString()`.

| Context | Tries first | Then |
|---|---|---|
| Arithmetic (`*`, `-`) and relational (`>`) | `valueOf()` | `toString()` |
| Template literals and `String(obj)` | `toString()` | `valueOf()` |
| `+` with default hint | `valueOf()` | `toString()` |

```javascript
const price = {
    amount: 100,
    valueOf() {
        return this.amount;
    },
    toString() {
        return "₹" + this.amount;
    }
};

console.log(price + 50);
console.log(price * 2);
console.log(price > 50);
console.log(`${price}`);
console.log(String(price));
```

### 📤 Output

```text
150
200
true
₹100
₹100
```

### 🛠️ Why This Matters

```javascript
console.log([] + []);
console.log([] + {});
console.log([1, 2] + [3]);
console.log({} + 1);
```

### 📤 Output

```text

[object Object]
1,23
[object Object]1
```

- Arrays convert to strings by joining their items with commas: `[1, 2]` becomes `"1,2"`.
- Plain objects convert to `"[object Object]"`.
- That is why `+` between objects produces odd text.

> 💡 For full control, objects can define a `[Symbol.toPrimitive](hint)` method. This is how `Date` objects behave differently with `+` (text) and `-` (number).

---

## 🔀 6. Logical Operators: De Morgan's Laws

De Morgan's laws help you **simplify or rewrite** conditions:

```text
!(A && B)  ≡  !A || !B
!(A || B)  ≡  !A && !B
```

```javascript
for (const a of [true, false]) {
    for (const b of [true, false]) {
        console.log(a, b, !(a && b) === (!a || !b), !(a || b) === (!a && !b));
    }
}
```

### 📤 Output

```text
true true true true
true false true true
false true true true
false false true true
```

### 🛠️ A Practical Rewrite

```javascript
const age = 25;
const hasTicket = true;

// "Not (adult AND has ticket)" ...
if (!(age >= 18 && hasTicket)) {
    console.log("Denied");
}

// ... is the same as "Not adult OR no ticket", usually easier to read
if (age < 18 || !hasTicket) {
    console.log("Denied");
}
```

(Neither line prints here, because both conditions are `false` for these values.)

### 🔄 Booleans: XOR and Conversion

```javascript
const a = true;
const b = false;

console.log(a !== b);
console.log(!!"text", !!0, !!{});
console.log(Boolean("0"));
```

### 📤 Output

```text
true
true false true
true
```

`a !== b` is a neat **exclusive OR** (true when exactly one side is true).

### 🪤 `!` Binds Tighter Than `in` and `==`

```javascript
const obj = { a: 1 };

console.log(!("b" in obj));
console.log(!"b" in obj);
```

### 📤 Output

```text
true
false
```

`!"b" in obj` is read as `(!"b") in obj`, which is `false in obj`, a check for a property named `"false"`. Always use parentheses: `!(key in obj)`.

---

## 🧮 7. Bitwise Operators

Bitwise operators convert numbers to **32-bit signed integers**, work on their binary digits, and convert back.

| Operator | Name | Rule |
|---|---|---|
| `&` | AND | Bit is `1` only if **both** bits are `1` |
| `\|` | OR | Bit is `1` if **either** bit is `1` |
| `^` | XOR | Bit is `1` if the bits are **different** |
| `~` | NOT | Flips every bit (`~n` equals `-(n + 1)`) |
| `<<` | Left shift | Moves bits left (multiplies by 2 each step) |
| `>>` | Sign-propagating right shift | Moves bits right, keeping the sign |
| `>>>` | Zero-fill right shift | Moves bits right, fills with zeros |

### 🔍 Binary Representations

```javascript
console.log((5).toString(2));
console.log((5).toString(2).padStart(8, "0"));
console.log(parseInt("101", 2));
console.log((255).toString(16));
```

### 📤 Output

```text
101
00000101
5
ff
```

### 🧪 Operations

```text
 5 = 0101
 3 = 0011
-----------
5 & 3 = 0001 = 1
5 | 3 = 0111 = 7
5 ^ 3 = 0110 = 6
```

```javascript
console.log(5 & 3);
console.log(5 | 3);
console.log(5 ^ 3);
console.log(~5);
console.log(5 << 1);
console.log(5 >> 1);
console.log(-16 >> 2);
console.log(-16 >>> 0);
console.log(1 << 31);
console.log(1 << 32);
```

### 📤 Output

```text
1
7
6
-6
10
2
-4
4294967280
-2147483648
1
```

### 🔍 Explanation

- `~5` is `-(5 + 1)` = `-6`.
- `-16 >> 2` keeps the sign and gives `-4`, while `-16 >>> 0` reinterprets the bits as an unsigned number.
- `1 << 31` becomes the sign bit, so the result is negative.
- Shift counts wrap around modulo 32, so `1 << 32` is `1`.

### 🛠️ Practical Uses

**1. Odd or even**

```javascript
console.log(7 & 1);
console.log(8 & 1);
```

### 📤 Output

```text
1
0
```

**2. Power of two**

```javascript
const isPowerOfTwo = (n) => n > 0 && (n & (n - 1)) === 0;

console.log(isPowerOfTwo(8));
console.log(isPowerOfTwo(6));
```

### 📤 Output

```text
true
false
```

**3. Truncating decimals (only safe within 32-bit range)**

```javascript
console.log(~~7.9);
console.log(7.9 | 0);
console.log(-7.9 | 0);
console.log(4294967301 | 0);
console.log(Math.trunc(4294967301));
```

### 📤 Output

```text
7
7
-7
5
4294967301
```

The last two lines show the danger: numbers beyond 32 bits **wrap around**. Prefer `Math.trunc()` unless you are certain about the range.

### 🚩 Permission Flags with Bitwise Operators

```javascript
const READ = 1;     // 001
const WRITE = 2;    // 010
const EXEC = 4;     // 100

let perms = READ | WRITE;
console.log(perms);

console.log((perms & WRITE) !== 0);
console.log((perms & EXEC) !== 0);

perms |= EXEC;
console.log(perms);

perms &= ~WRITE;
console.log(perms);

perms ^= READ;
console.log(perms);
```

### 📤 Output

```text
3
true
false
7
5
4
```

| Goal | Expression |
|---|---|
| Combine flags | `READ \| WRITE` |
| Check a flag | `(perms & WRITE) !== 0` |
| Add a flag | `perms \|= EXEC` |
| Remove a flag | `perms &= ~WRITE` |
| Toggle a flag | `perms ^= READ` |

### 🆚 Bitwise `&` and `|` vs Logical `&&` and `||`

| Bitwise `&`, `\|` | Logical `&&`, `\|\|` |
|---|---|
| Work on the **bits** of numbers | Work on **truthiness** |
| **No** short-circuiting (both sides always run) | **Short-circuit** |
| Return a number | Return one of the operands |

> ⚠️ Typing `&` when you meant `&&` (or `|` for `||`) is a common bug that gives wrong results without any error.

---

## 🔍 8. Type and Relational Operators

### 🏷️ `typeof`

```javascript
console.log(typeof 42);
console.log(typeof "hi");
console.log(typeof true);
console.log(typeof undefined);
console.log(typeof 10n);
console.log(typeof Symbol());
console.log(typeof null);
console.log(typeof []);
console.log(typeof function () {});
console.log(typeof class {});
console.log(typeof NaN);
console.log(typeof notDeclaredAnywhere);
```

### 📤 Output

```text
number
string
boolean
undefined
bigint
symbol
object
object
function
function
number
undefined
```

| Surprise | Why |
|---|---|
| `typeof null` is `"object"` | A historic bug kept for compatibility. Check with `x === null` |
| `typeof []` is `"object"` | Use `Array.isArray(x)` |
| `typeof NaN` is `"number"` | `NaN` is a special number value |
| `typeof undeclaredVar` is `"undefined"` | `typeof` is the **only** operator that doesn't throw on an undeclared name |

### 🧬 `instanceof`

Checks whether a constructor's `prototype` appears in the object's prototype chain.

```javascript
class Animal {}
class Dog extends Animal {}

const d = new Dog();

console.log(d instanceof Dog);
console.log(d instanceof Animal);
console.log(d instanceof Object);
console.log([] instanceof Array);
console.log(Object.create(null) instanceof Object);
console.log("hi" instanceof String);
console.log(new String("hi") instanceof String);
```

### 📤 Output

```text
true
true
true
true
false
false
true
```

Primitives such as `"hi"` are **not** instances of anything, and objects created with `Object.create(null)` have no prototype chain.

### 🔑 `in`

Checks whether a property exists on the object **or its prototype chain**.

```javascript
const obj = { a: 1 };

console.log("a" in obj);
console.log("toString" in obj);
console.log(Object.hasOwn(obj, "toString"));
console.log(1 in [10, 20]);
console.log(5 in [10, 20]);
console.log("length" in []);
```

### 📤 Output

```text
true
true
false
true
false
true
```

For arrays, `in` checks **indexes** (not values). To check values, use `includes()`.

### 🗑️ `delete`

```javascript
const user = { name: "Aman", age: 20 };

console.log(delete user.age);
console.log(user);

const arr = [1, 2, 3];
delete arr[1];
console.log(arr);
console.log(arr.length);
```

### 📤 Output

```text
true
{ name: 'Aman' }
[ 1, <1 empty item>, 3 ]
3
```

`delete` removes a property but leaves a **hole** in arrays, and the length doesn't change. Use `splice()` to remove array elements properly.

---

## ❓ 9. Ternary and Spread

### ❓ Readable Ternaries

```javascript
const score = 72;

// Chained ternary: acceptable when formatted clearly
const grade =
    score >= 90 ? "A" :
    score >= 75 ? "B" :
    score >= 60 ? "C" :
    "D";

console.log(grade);
```

### 📤 Output

```text
C
```

> ⚠️ Avoid nesting ternaries inside each other on one line. If a chain gets long or has side effects, use `if...else` or `switch`.

### 🔗 Spread Syntax (`...`)

`...` is **syntax**, not a true operator, but it is used inside expressions.

```javascript
const a = [1, 2];
const b = [3, 4];

console.log([...a, ...b]);
console.log(Math.max(...a, ...b));
console.log({ ...{ x: 1, y: 2 }, y: 99, z: 3 });
console.log({ y: 99, ...{ x: 1, y: 2 } });
```

### 📤 Output

```text
[ 1, 2, 3, 4 ]
4
{ x: 1, y: 99, z: 3 }
{ y: 2, x: 1 }
```

**Order matters** in object spread: later properties **overwrite** earlier ones.

### 🛟 Optional Chaining Forms

```javascript
const data = { list: [10, 20], fn() { return "called"; } };

console.log(data.list?.[1]);
console.log(data.other?.[1]);
console.log(data.fn?.());
console.log(data.missing?.());
```

### 📤 Output

```text
20
undefined
called
undefined
```

---

## ⚠️ 10. Precedence Traps You Will Actually Meet

| Expression | What really happens | Result |
|---|---|---|
| `typeof 1 + 2` | `(typeof 1) + 2` | `"number2"` |
| `1 + +"2"` | `1 + (+"2")` | `3` |
| `1 + "2" - 1` | `("1" + "2" = "12") - 1` | `11` |
| `"3" + 4 + 5` | `("3" + 4) + 5` | `"345"` |
| `3 + 4 + "5"` | `(3 + 4) + "5"` | `"75"` |
| `!"b" in obj` | `(!"b") in obj` | Usually `false` |
| `a ?? b \|\| c` | ❌ SyntaxError | Add parentheses |
| `-2 ** 2` | ❌ SyntaxError | Write `(-2) ** 2` |
| `x = y ? a : b` | `x = (y ? a : b)` | Assignment is lowest |
| `a && b \|\| c` | `(a && b) \|\| c` | `&&` before `\|\|` |

---

## 🧰 11. Mini Examples

### 🎠 Wrap-Around Navigation and Clamping

```javascript
const clamp = (n, min, max) => Math.min(Math.max(n, min), max);

const slides = 5;
const next = (i) => (i + 1) % slides;
const prev = (i) => (i - 1 + slides) % slides;

console.log(clamp(15, 0, 10));
console.log(clamp(-4, 0, 10));
console.log(next(4));
console.log(prev(0));
```

### 📤 Output

```text
10
0
0
4
```

### 🔢 Sum of Digits with `%` and `Math.trunc`

```javascript
function sumDigits(n) {
    let sum = 0;
    while (n > 0) {
        sum += n % 10;
        n = Math.trunc(n / 10);
    }
    return sum;
}

console.log(sumDigits(1234));
console.log(sumDigits(9075));
```

### 📤 Output

```text
10
21
```

---

## 📋 12. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Expecting `-7 % 3` to be `2` | `%` is a remainder (`-1`). Use `((n % m) + m) % m` for true modulo |
| Comparing floats with `===` | Use a tolerance with `Number.EPSILON`, or integers for money |
| Using `isNaN("abc")` as a strict check | Use `Number.isNaN(x)` |
| Comparing arrays/objects with `===` for content | Compare item by item, or use a deep-equality helper |
| Sorting strings (or numbers) with the default `sort()` | `sort((a, b) => a.localeCompare(b))` or `sort((a, b) => a - b)` |
| Writing `\|\| ` for a default when `0` or `""` is valid | Use `??` |
| Writing `&` or `\|` when you meant `&&` or `\|\|` | Use logical operators for conditions |
| Using `~~x` or `x \| 0` on big numbers | They wrap at 32 bits. Use `Math.trunc` |
| `!key in obj` | `!(key in obj)` |
| `delete arr[i]` to remove an element | `arr.splice(i, 1)` |
| Mixing `BigInt` and `Number` | Convert explicitly |
| `let a = b = 5;` | Declare both variables separately |
| Relying on `typeof` to detect arrays or `null` | `Array.isArray(x)` and `x === null` |

---

## 🧪 13. Practice Tasks

- [ ] 🟢 **Beginner:** Print `7 % 3`, `-7 % 3`, and `7 % -3`. Explain the signs.
- [ ] 🟢 **Beginner:** Write a function `isEven(n)` using `%`, and another using `&`. Check that they agree for `-3`, `0`, and `8`.
- [ ] 🟡 **Intermediate:** Write `mod(n, m)` that always returns a non-negative result, and use it to build a clock that wraps from `11` back to `0`.
- [ ] 🟡 **Intermediate:** Write `almostEqual(a, b)` that safely compares two floating-point numbers using `Number.EPSILON`. Test it with `0.1 + 0.2` and `0.3`.
- [ ] 🟡 **Intermediate:** Predict, then verify: `console.log("10" < "9", 10 < "9", "b" > "a")`.
- [ ] 🔵 **Practice:** Create an object with `valueOf()` and `toString()` that represents a temperature, and use it in arithmetic and in a template literal.
- [ ] 🔵 **Practice:** Sort `["banana", "Apple", "cherry"]` alphabetically, ignoring case, using `localeCompare()`.
- [ ] 🔵 **Practice:** Simplify `!(a < 5 && b > 10)` using De Morgan's law and test every combination.
- [ ] 🔴 **Challenge:** Build a permission system with the flags `READ`, `WRITE`, `DELETE`, and `ADMIN`. Write functions `grant`, `revoke`, `toggle`, and `has` using bitwise operators.
- [ ] 🔴 **Challenge:** Write `isPowerOfTwo(n)` and use it to find all powers of two up to `1000`.
- [ ] 🔴 **Challenge:** Explain why `[] == ![]` is `true`, step by step, using the conversion rules for `==`.

---

## 🎤 14. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What are unary, binary, and ternary operators?**

**Answer:** Unary operators take one operand (`!x`, `typeof x`), binary operators take two (`a + b`), and the ternary operator takes three (`condition ? a : b`), which is the only one in JavaScript.

**Q2. Does JavaScript support operator overloading?**

**Answer:** No. You cannot redefine operators for your own types, but you can control how objects convert to primitives using `valueOf()`, `toString()`, or `Symbol.toPrimitive`.

**Q3. What does the `%` operator return?**

**Answer:** The remainder of a division. Its result has the same sign as the dividend, so `-7 % 3` is `-1`.

**Q4. Is there an integer division operator in JavaScript?**

**Answer:** No. `/` always gives a floating-point result. Use `Math.trunc(a / b)` or `Math.floor(a / b)` depending on how negative numbers should round.

**Q5. What does `5 / 0` return?**

**Answer:** `Infinity`. JavaScript does not throw an error for division by zero, and `0 / 0` gives `NaN`.

### 🟡 Intermediate Questions

**Q6. How do you get a true (non-negative) modulo in JavaScript?**

**Answer:** Use `((n % m) + m) % m`. For example, `((-7 % 3) + 3) % 3` is `2`.

**Q7. Why is `0.1 + 0.2 !== 0.3`, and how do you compare such numbers safely?**

**Answer:** Numbers are stored in binary floating-point, so some decimals cannot be represented exactly. Compare with a small tolerance, for example `Math.abs(a - b) < Number.EPSILON`, or work in integers (such as paise or cents) for money.

**Q8. What happens if you mix `BigInt` and `Number` in an arithmetic operation?**

**Answer:** A `TypeError` is thrown. You must convert one explicitly, for example `BigInt(5) + 2n` or `Number(2n) + 5`.

**Q9. What is the difference between `==`, `===`, and `Object.is()`?**

**Answer:** `==` converts types before comparing, `===` compares value and type strictly, and `Object.is()` is like `===` except that `Object.is(NaN, NaN)` is `true` and `Object.is(0, -0)` is `false`.

**Q10. Why is `NaN === NaN` false, and how should you test for `NaN`?**

**Answer:** `NaN` represents an invalid number and is defined as not equal to anything, including itself. Use `Number.isNaN(x)` (or `Object.is(x, NaN)`).

**Q11. What is the difference between `isNaN()` and `Number.isNaN()`?**

**Answer:** `isNaN()` converts its argument to a number first, so `isNaN("abc")` is `true`. `Number.isNaN()` does not convert, so `Number.isNaN("abc")` is `false`.

**Q12. How are two arrays or objects compared by `===`?**

**Answer:** By **reference**. Two different objects with identical content are not equal; they are equal only if they refer to the same object in memory.

**Q13. Why does `"10" < "9"` give `true` but `10 < "9"` gives `false`?**

**Answer:** When both operands are strings, they are compared character by character (`"1"` comes before `"9"`). When one operand is a number, the other is converted to a number, so `10 < 9` is `false`.

**Q14. What are De Morgan's laws?**

**Answer:** `!(A && B)` is equivalent to `!A || !B`, and `!(A || B)` is equivalent to `!A && !B`. They help simplify negated conditions.

### 🔵 Practical and Advanced Questions

**Q15. How does JavaScript convert an object when it is used with an operator?**

**Answer:** It calls `valueOf()` and/or `toString()` (or `Symbol.toPrimitive` if defined). For arithmetic and relational operators it tries `valueOf()` first, and for string contexts such as template literals it tries `toString()` first.

**Q16. What is the difference between `&` and `&&`?**

**Answer:** `&` is the bitwise AND that works on the bits of numbers and always evaluates both operands. `&&` is the logical AND that works on truthiness, short-circuits, and returns one of its operands.

**Q17. What is the difference between `>>` and `>>>`?**

**Answer:** `>>` shifts bits right and preserves the sign bit, while `>>>` shifts right and always fills with zeros, so the result is always non-negative.

**Q18. What is the value of `~5`, and what is the general rule?**

**Answer:** `-6`. The general rule is `~n === -(n + 1)`.

**Q19. How would you manage permission flags using bitwise operators?**

**Answer:** Give each permission its own bit (`READ = 1`, `WRITE = 2`, `EXEC = 4`). Combine with `|`, test with `(perms & WRITE) !== 0`, add with `|=`, remove with `&= ~WRITE`, and toggle with `^=`.

**Q20. Why is `x | 0` or `~~x` not a safe replacement for `Math.trunc(x)`?**

**Answer:** Bitwise operators convert to 32-bit integers, so numbers outside that range wrap around (for example `4294967301 | 0` is `5`).

**Q21. Why is `typeof null` equal to `"object"`?**

**Answer:** It is a historical bug in the original JavaScript implementation that has been kept for backward compatibility. Check for `null` with `x === null`.

**Q22. What is special about `typeof` with an undeclared variable?**

**Answer:** `typeof notDeclared` returns `"undefined"` without throwing a `ReferenceError`, unlike any other use of an undeclared variable.

**Q23. What is the difference between `in` and `Object.hasOwn()`?**

**Answer:** `in` checks the object and its entire prototype chain (so `"toString" in {}` is `true`), while `Object.hasOwn(obj, key)` checks only the object's own properties.

**Q24. What happens when you use `delete` on an array element?**

**Answer:** The element is removed but leaves an empty slot (a hole) and the array's `length` stays the same. Use `splice()` to remove elements properly.

**Q25. Why is `!key in obj` usually a bug?**

**Answer:** `!` has higher precedence than `in`, so it is evaluated as `(!key) in obj`, which checks for a property named `"false"` (or `"true"`). The correct form is `!(key in obj)`.

**Q26. Predict the output: `console.log(1 + "2" - 1, "3" + 4 + 5, 3 + 4 + "5")`.**

**Answer:** `11 345 75`. In the first, `1 + "2"` is `"12"`, and `"12" - 1` is `11`. In the second, `"3" + 4` is `"34"`, then `"345"`. In the third, `3 + 4` is `7`, then `"75"`.

---

## 🏆 15. Key Takeaways

- 🔢 Operators are **unary**, **binary**, or **ternary**, and JavaScript has no operator overloading.
- ➗ `%` is a **remainder** (sign of the left operand). Use `((n % m) + m) % m` for a true modulo. There is no integer division, so use `Math.trunc()`.
- 🧮 Floating-point errors are normal. Compare with `Number.EPSILON`, and use integers for money.
- 🔢 `BigInt` and `Number` cannot be mixed in arithmetic.
- ⚖️ Prefer `===`. Use `Object.is()` for `NaN` and `-0`, `Number.isNaN()` for `NaN` checks, and `localeCompare()` for sorting text.
- 🧱 Objects and arrays are compared by **reference**.
- 🎭 Objects take part in operators through `valueOf()`, `toString()`, and `Symbol.toPrimitive`.
- 🔀 De Morgan's laws help you simplify negated conditions.
- 🧮 Bitwise operators work on **32-bit integers**, and they are ideal for flags, parity, and powers of two.
- 🔍 `typeof`, `instanceof`, `in`, and `delete` each have quirks, so know them before relying on them.
- ⚠️ Use parentheses to avoid precedence traps such as `!key in obj`.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Most operator bugs come from **hidden conversions**. When the result surprises you, ask: *"What type did each operand become?"*

**Happy Coding! 💻✨**
