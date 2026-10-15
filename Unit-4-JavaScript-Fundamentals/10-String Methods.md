# 🔤 JavaScript String Methods

> 🎯 **Learning Objectives**
> - Understand what a string is and that strings are immutable.
> - Find the length and access characters of a string.
> - Change case, trim spaces, and extract parts of a string.
> - Search inside strings and replace text.
> - Split strings into arrays and join arrays into strings.
> - Chain methods to solve real problems.

---

## 🌟 1. What is a String Method?

A **string** is text, such as `"Hello"` or `"JavaScript"`. A **string method** is a built-in function that works on a string to do something useful with it.

Think of a **text editor** like Word. 📝

| Word feature | JavaScript string method |
|---|---|
| 🔠 Change to UPPERCASE | `toUpperCase()` |
| ✂️ Cut out a portion | `slice()` |
| 🔍 Find a word | `indexOf()`, `includes()` |
| 🔄 Find and Replace | `replace()` |

### 🧩 Syntax

```javascript
string.methodName(arguments);
```

### 🧠 Remember This!

- Strings are **immutable**: methods never change the original string, they **return a new one**.
- Positions in a string start from **0**.
- String methods are **case-sensitive**.

---

## 💻 2. Length and Accessing Characters

```javascript
let text = "JavaScript";

console.log(text.length);
console.log(text[0]);
console.log(text.charAt(4));
console.log(text.at(-1));
console.log(text[20]);
console.log(text.charAt(20));
```

### 📤 Output

```text
10
J
S
t
undefined

```

The last line is an **empty string** (it prints a blank line).

### 🔍 Explanation

| Code | Meaning |
|---|---|
| `length` | Number of characters (a **property**, so no `()`) |
| `text[0]` | Character at position 0 |
| `charAt(4)` | Character at position 4 |
| `at(-1)` | Character from the **end** (`-1` is the last one) |
| `text[20]` | Position doesn't exist, so `undefined` |
| `charAt(20)` | Position doesn't exist, so `""` (empty string) |

### 🗺️ Index Map of `"JavaScript"`

```text
Character:  J  a  v  a  S  c  r  i  p  t
Index:      0  1  2  3  4  5  6  7  8  9
Negative:  -10 -9 -8 -7 -6 -5 -4 -3 -2 -1
```

💡 **Try It Yourself:** Print the first and last character of your own name.

---

## 🔠 3. Changing Case

```javascript
let msg = "Hello World";

console.log(msg.toUpperCase());
console.log(msg.toLowerCase());
```

### 📤 Output

```text
HELLO WORLD
hello world
```

### 🛠️ Use Case: Case-Insensitive Comparison

```javascript
let input = "YES";

if (input.toLowerCase() === "yes") {
    console.log("Confirmed ✅");
}
```

### 📤 Output

```text
Confirmed ✅
```

---

## ✂️ 4. Removing Extra Spaces

```javascript
let spaced = "   Hello   ";

console.log(`[${spaced.trim()}]`);
console.log(`[${spaced.trimStart()}]`);
console.log(`[${spaced.trimEnd()}]`);
```

### 📤 Output

```text
[Hello]
[Hello   ]
[   Hello]
```

| Method | Removes spaces from |
|---|---|
| `trim()` | Both ends |
| `trimStart()` | Start only |
| `trimEnd()` | End only |

💡 Always `trim()` text typed by users in forms.

---

## 🍰 5. Extracting Parts of a String

### 🟢 `slice(start, end)`

Returns the part from `start` up to, but **not including**, `end`.

```javascript
let text = "JavaScript";

console.log(text.slice(0, 4));
console.log(text.slice(4));
console.log(text.slice(-6));
console.log(text.slice(-6, -3));
```

### 📤 Output

```text
Java
Script
Script
Scr
```

### 🔵 `substring(start, end)`

Similar to `slice()`, but with different rules.

```javascript
console.log(text.substring(0, 4));
console.log(text.substring(4, 0));
```

### 📤 Output

```text
Java
Java
```

### 🆚 `slice()` vs `substring()`

| Feature | `slice()` | `substring()` |
|---|---|---|
| Negative numbers | ✅ Counts from the end | ❌ Treated as `0` |
| If `start > end` | Returns `""` | Swaps the two values |
| Recommended? | ✅ Yes | OK, but `slice()` is simpler |

> ⚠️ The old `substr()` method is deprecated. Use `slice()` instead.

---

## 🔍 6. Searching Inside a String

### 📍 Finding Positions

```javascript
let sentence = "Hello World";

console.log(sentence.indexOf("o"));
console.log(sentence.lastIndexOf("o"));
console.log(sentence.indexOf("World"));
console.log(sentence.indexOf("z"));
```

### 📤 Output

```text
4
7
6
-1
```

- `indexOf()` returns the position of the **first** match.
- `lastIndexOf()` returns the position of the **last** match.
- `-1` means **not found**.

### ✅ Checking if Text Exists

```javascript
let course = "JavaScript";

console.log(course.includes("Script"));
console.log(course.includes("script"));
console.log(course.startsWith("Java"));
console.log(course.endsWith("pt"));
```

### 📤 Output

```text
true
false
true
true
```

These methods return a **boolean**, which makes them ideal for `if` conditions. Note that `"script"` does not match `"Script"` because searches are case-sensitive.

---

## 🔄 7. Replacing Text

```javascript
let text = "I like cats. cats are cute.";

console.log(text.replace("cats", "dogs"));
console.log(text.replaceAll("cats", "dogs"));
console.log(text);
```

### 📤 Output

```text
I like dogs. cats are cute.
I like dogs. dogs are cute.
I like cats. cats are cute.
```

### 🔍 Explanation

- `replace()` changes only the **first** match.
- `replaceAll()` changes **every** match.
- The original `text` stays unchanged, because strings are immutable.

---

## 🔗 8. Splitting and Joining

### ✂️ `split()`: String → Array

```javascript
console.log("red,green,blue".split(","));
console.log("Hello".split(""));
console.log("I love coding".split(" "));
```

### 📤 Output

```text
[ 'red', 'green', 'blue' ]
[ 'H', 'e', 'l', 'l', 'o' ]
[ 'I', 'love', 'coding' ]
```

### 🪢 `join()`: Array → String

`join()` belongs to **arrays**, but it is the partner of `split()`.

```javascript
let words = ["a", "b", "c"];
console.log(words.join("-"));
console.log(words.join(""));
```

### 📤 Output

```text
a-b-c
abc
```

### 🔁 Reversing a String

JavaScript has no `reverse()` for strings, so we combine three methods.

```javascript
let word = "Hello";
let reversed = word.split("").reverse().join("");
console.log(reversed);
```

### 📤 Output

```text
olleH
```

---

## 🧱 9. Building and Formatting Strings

### 🔁 `repeat()`

```javascript
console.log("Ha".repeat(3));
console.log("-".repeat(20));
```

### 📤 Output

```text
HaHaHa
--------------------
```

### 📏 `padStart()` and `padEnd()`

Add characters until the string reaches a target length.

```javascript
console.log("5".padStart(3, "0"));
console.log("7".padEnd(3, "*"));
```

### 📤 Output

```text
005
7**
```

### ➕ `concat()` and `+`

```javascript
console.log("Hello".concat(" ", "World"));
console.log("Hello" + " " + "World");
```

### 📤 Output

```text
Hello World
Hello World
```

💡 In modern code, prefer **template literals**: `` `Hello ${name}` ``.

---

## 🧊 10. Strings Are Immutable

```javascript
let s = "Hello";

s.toUpperCase();
console.log(s);

s[0] = "J";
console.log(s);

s = s.toUpperCase();
console.log(s);
```

### 📤 Output

```text
Hello
Hello
HELLO
```

### 🔍 Explanation

- `s.toUpperCase()` returns a new string, but we never stored it, so `s` is unchanged.
- `s[0] = "J"` is ignored (in strict mode it throws a `TypeError`).
- To "change" a string, **reassign** the variable with the new result.

---

## ⛓️ 11. Method Chaining

Because each method returns a string, you can call another method on the result.

```javascript
let raw = "   hello WORLD   ";
let clean = raw.trim().toLowerCase();
console.log(clean);
```

### 📤 Output

```text
hello world
```

### 🔠 Capitalise the First Letter

```javascript
let word = "jAVASCRIPT";
let result = word.charAt(0).toUpperCase() + word.slice(1).toLowerCase();
console.log(result);
```

### 📤 Output

```text
Javascript
```

---

## 🛠️ 12. Mini Examples

### 📧 Extract Username and Domain from an Email

```javascript
let email = "aman.sharma@example.com";

if (email.includes("@")) {
    let at = email.indexOf("@");
    console.log(email.slice(0, at));
    console.log(email.slice(at + 1));
}
```

### 📤 Output

```text
aman.sharma
example.com
```

### 🏷️ Convert a Sentence to Title Case

```javascript
let sentence = "hello world from js";

let title = sentence
    .split(" ")
    .map((w) => w[0].toUpperCase() + w.slice(1))
    .join(" ");

console.log(title);
```

### 📤 Output

```text
Hello World From Js
```

### 🔍 What Happens?

1. `split(" ")` breaks the sentence into words.
2. `map()` capitalises the first letter of each word.
3. `join(" ")` joins the words back into one string.

---

## 📋 13. Quick Reference

| Method | Purpose | Example | Result |
|---|---|---|---|
| `length` | Number of characters | `"Hi".length` | `2` |
| `charAt(i)` / `at(i)` | Character at position | `"Hi".at(-1)` | `"i"` |
| `toUpperCase()` | Uppercase | `"hi".toUpperCase()` | `"HI"` |
| `toLowerCase()` | Lowercase | `"HI".toLowerCase()` | `"hi"` |
| `trim()` | Remove edge spaces | `" hi ".trim()` | `"hi"` |
| `slice(s, e)` | Extract a part | `"Hello".slice(1, 3)` | `"el"` |
| `indexOf(x)` | First position or `-1` | `"Hello".indexOf("l")` | `2` |
| `includes(x)` | Contains? | `"Hello".includes("ell")` | `true` |
| `startsWith(x)` | Starts with? | `"Hello".startsWith("He")` | `true` |
| `endsWith(x)` | Ends with? | `"Hello".endsWith("lo")` | `true` |
| `replace(a, b)` | Replace first match | `"aa".replace("a", "b")` | `"ba"` |
| `replaceAll(a, b)` | Replace all matches | `"aa".replaceAll("a", "b")` | `"bb"` |
| `split(sep)` | String → array | `"a-b".split("-")` | `["a", "b"]` |
| `repeat(n)` | Repeat text | `"ab".repeat(2)` | `"abab"` |
| `padStart(n, c)` | Pad at the start | `"5".padStart(2, "0")` | `"05"` |

---

## ⚠️ 14. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Writing `text.length()` | `length` is a property: `text.length` |
| Expecting `toUpperCase()` to change the original | Store the result: `text = text.toUpperCase()` |
| Forgetting that `slice(0, 4)` excludes index 4 | The `end` position is **not** included |
| Searching with the wrong case: `includes("script")` | Convert both sides to lowercase first |
| Using `replace()` when you want to change all matches | Use `replaceAll()` |
| Checking `indexOf("x")` as true/false (`-1` is truthy) | Use `includes("x")` or compare with `-1` |
| Using the deprecated `substr()` | Use `slice()` |

---

## 🧪 15. Practice Tasks

- [ ] 🟢 **Beginner:** Print the length of your name and its first and last character.
- [ ] 🟢 **Beginner:** Convert a sentence to uppercase and lowercase.
- [ ] 🟡 **Intermediate:** Take `"   Welcome   "` and print it without the extra spaces.
- [ ] 🟡 **Intermediate:** Extract `"Script"` from `"JavaScript"` using `slice()`.
- [ ] 🔵 **Practice:** Check whether a given email contains `@` and ends with `.com`.
- [ ] 🔵 **Practice:** Replace every space in `"I love JS"` with a hyphen.
- [ ] 🔴 **Challenge:** Write a function that checks whether a word is a palindrome (for example, `"madam"`).
- [ ] 🔴 **Challenge:** Write a function that counts how many vowels are in a string.

---

## 🎤 16. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a string in JavaScript?**

**Answer:** A string is a sequence of characters used to represent text, written inside single quotes, double quotes, or backticks.

**Q2. How do you find the length of a string?**

**Answer:** Using the `length` property, for example `"Hello".length` gives `5`. It is a property, not a method.

**Q3. What index does the first character of a string have?**

**Answer:** `0`.

**Q4. How do you convert a string to uppercase and lowercase?**

**Answer:** Using `toUpperCase()` and `toLowerCase()`.

**Q5. What does `trim()` do?**

**Answer:** It removes whitespace from both the start and the end of a string.

### 🟡 Intermediate Questions

**Q6. What does it mean that strings are immutable?**

**Answer:** Once created, a string cannot be changed. String methods return a new string instead of modifying the original.

**Q7. What is the difference between `slice()` and `substring()`?**

**Answer:** `slice()` supports negative indexes (counting from the end) and returns an empty string if `start > end`. `substring()` treats negatives as `0` and swaps the arguments if `start > end`.

**Q8. What does `indexOf()` return if the text is not found?**

**Answer:** `-1`.

**Q9. What is the difference between `indexOf()` and `includes()`?**

**Answer:** `indexOf()` returns the position (or `-1`), while `includes()` returns a boolean `true` or `false`.

**Q10. What is the difference between `replace()` and `replaceAll()`?**

**Answer:** `replace()` replaces only the first match, while `replaceAll()` replaces every match.

**Q11. How do you convert a string into an array?**

**Answer:** Using `split()`, for example `"a,b,c".split(",")` gives `["a", "b", "c"]`.

**Q12. Are string methods case-sensitive?**

**Answer:** Yes. For example, `"JavaScript".includes("script")` returns `false`.

### 🔵 Practical Questions

**Q13. How do you reverse a string?**

**Answer:**

```javascript
let reversed = "Hello".split("").reverse().join("");
```

**Q14. What is the output of the following code?**

```javascript
let s = "hello";
s.toUpperCase();
console.log(s);
```

**Answer:** `hello`. The method returns a new string, which was not stored, so `s` is unchanged.

**Q15. What does `"JavaScript".slice(-6)` return?**

**Answer:** `"Script"`, because `-6` counts six characters from the end.

**Q16. What does `"5".padStart(3, "0")` return?**

**Answer:** `"005"`.

**Q17. What is method chaining?**

**Answer:** Calling one method directly on the result of another, for example `text.trim().toLowerCase()`.

**Q18. How do you capitalise the first letter of a word?**

**Answer:**

```javascript
word.charAt(0).toUpperCase() + word.slice(1).toLowerCase();
```

---

## 🏆 17. Key Takeaways

- 🔤 A string is text, and string methods perform useful operations on it.
- 🧊 Strings are immutable. Methods return a new string, so store the result.
- 📏 `length` is a property, and indexes start from `0`.
- 🔠 Use `toUpperCase()`, `toLowerCase()`, and `trim()` to clean text.
- ✂️ Use `slice()` to extract parts, including from the end with negative numbers.
- 🔍 Use `includes()`, `startsWith()`, and `endsWith()` for yes/no checks, and `indexOf()` for positions.
- 🔄 Use `replace()` for the first match and `replaceAll()` for all matches.
- 🔗 `split()` and `join()` convert between strings and arrays.
- ⛓️ Chain methods to write short, powerful code.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Almost every program handles text, so string methods are among the most useful tools you will learn.

**Happy Coding! 💻✨**
