# 📚 JavaScript Arrays

> 🎯 **Learning Objectives**
> - Understand what an array is and how to create one.
> - Access, add, update, and remove elements.
> - Loop through arrays using `for`, `for...of`, and `forEach()`.
> - Search arrays with `indexOf()`, `includes()`, and `find()`.
> - Transform data using `map()`, `filter()`, and `reduce()`.
> - Sort arrays correctly and avoid the number-sorting trap.
> - Understand destructuring, spread, and copying arrays.

---

## 🌟 1. What is an Array?

An **array** is an ordered list that stores multiple values in a single variable.

Think of a **train with numbered coaches**. 🚆

| Train | JavaScript Array |
|---|---|
| 🚃 Each coach | An **element** |
| 🔢 Coach number (starting from 0) | The **index** |
| 🚆 The whole train | The array |

Instead of creating `fruit1`, `fruit2`, and `fruit3`, we keep them all in one array.

### 🧠 Remember This!

- Arrays are **ordered** and use **indexes starting from 0**.
- An array can hold **any type** of value, even mixed types.
- Arrays are **objects**, so `typeof [] ` is `"object"`.

---

## 💻 2. Creating and Accessing Arrays

```javascript
const fruits = ["Apple", "Banana", "Mango"];

console.log(fruits);
console.log(fruits[0]);
console.log(fruits.length);
console.log(fruits[fruits.length - 1]);
console.log(fruits.at(-1));
console.log(fruits[10]);
```

### 📤 Output

```text
[ 'Apple', 'Banana', 'Mango' ]
Apple
3
Mango
Mango
undefined
```

### 🔍 Explanation

- Square brackets `[ ]` create the array; elements are separated by commas.
- `fruits[0]` is the first element.
- `length` gives the number of elements.
- `fruits.at(-1)` gets the **last** element (negative numbers count from the end).
- A position that doesn't exist gives `undefined`.

### 🗺️ Index Map

```text
Element:  "Apple"  "Banana"  "Mango"
Index:       0        1         2
```

### ✏️ Updating an Element

```javascript
fruits[1] = "Orange";
console.log(fruits);
```

### 📤 Output

```text
[ 'Apple', 'Orange', 'Mango' ]
```

### 🎨 Mixed Types Are Allowed

```javascript
const mixed = ["Aman", 20, true, null];
console.log(mixed);
```

### 📤 Output

```text
[ 'Aman', 20, true, null ]
```

### ✅ Checking if Something is an Array

```javascript
console.log(Array.isArray(fruits));
console.log(Array.isArray("hello"));
console.log(typeof fruits);
```

### 📤 Output

```text
true
false
object
```

💡 **Try It Yourself:** Create an array of your 5 favourite movies and print the first and last one.

---

## ➕ 3. Adding and Removing Elements

### 📊 The Four Basic Methods

| Method | Action | Returns |
|---|---|---|
| `push(x)` | Adds to the **end** | New length |
| `pop()` | Removes from the **end** | The removed element |
| `unshift(x)` | Adds to the **start** | New length |
| `shift()` | Removes from the **start** | The removed element |

```javascript
const nums = [1, 2, 3];

nums.push(4);
console.log(nums);

console.log(nums.pop());
console.log(nums);

nums.unshift(0);
console.log(nums);

console.log(nums.shift());
console.log(nums);
```

### 📤 Output

```text
[ 1, 2, 3, 4 ]
4
[ 1, 2, 3 ]
[ 0, 1, 2, 3 ]
0
[ 1, 2, 3 ]
```

> 💡 All four methods **change the original array** (they are *mutating* methods).

### ✂️ `splice()`: Add, Remove, or Replace Anywhere

```javascript
splice(startIndex, deleteCount, item1, item2, ...)
```

**Remove:**

```javascript
const a = ["a", "b", "c", "d"];
const removed = a.splice(1, 2);

console.log(removed);
console.log(a);
```

### 📤 Output

```text
[ 'b', 'c' ]
[ 'a', 'd' ]
```

**Insert (delete count `0`):**

```javascript
const b = ["a", "d"];
b.splice(1, 0, "x", "y");
console.log(b);
```

### 📤 Output

```text
[ 'a', 'x', 'y', 'd' ]
```

**Replace:**

```javascript
const c = ["a", "b", "c"];
c.splice(1, 1, "Z");
console.log(c);
```

### 📤 Output

```text
[ 'a', 'Z', 'c' ]
```

---

## 🍰 4. Copying and Combining Arrays

### 🟢 `slice(start, end)`: Extract a Portion (does not change the original)

```javascript
const nums = [10, 20, 30, 40, 50];

console.log(nums.slice(1, 4));
console.log(nums.slice(-2));
console.log(nums);
```

### 📤 Output

```text
[ 20, 30, 40 ]
[ 40, 50 ]
[ 10, 20, 30, 40, 50 ]
```

The `end` index is **not included**.

### 🔵 Combining Arrays

```javascript
const x = [1, 2];
const y = [3, 4];

console.log(x.concat(y));
console.log([...x, ...y]);
console.log([0, ...x, 99, ...y]);
```

### 📤 Output

```text
[ 1, 2, 3, 4 ]
[ 1, 2, 3, 4 ]
[ 0, 1, 2, 99, 3, 4 ]
```

The `...` **spread operator** expands an array into individual elements.

### 🔴 Arrays Are Copied by Reference

```javascript
const original = [1, 2, 3];
const sameArray = original;
sameArray.push(4);

console.log(original);

const copy = [...original];
copy.push(5);

console.log(original);
console.log(copy);
```

### 📤 Output

```text
[ 1, 2, 3, 4 ]
[ 1, 2, 3, 4 ]
[ 1, 2, 3, 4, 5 ]
```

- `sameArray` is **not** a copy. Both names point to the same array.
- `[...original]` creates a real (shallow) copy.

### 🔒 `const` and Arrays

```javascript
const list = [1, 2];
list.push(3);          // ✅ allowed
console.log(list);

list = [9, 9];         // ❌ TypeError
```

### 📤 Output

```text
[ 1, 2, 3 ]
TypeError: Assignment to constant variable.
```

`const` stops you from **reassigning the variable**, but you can still change the **contents**.

---

## 🔍 5. Searching Arrays

### 📍 `indexOf()` and `includes()`

```javascript
const letters = ["a", "b", "c"];

console.log(letters.indexOf("b"));
console.log(letters.indexOf("z"));
console.log(letters.includes("c"));
```

### 📤 Output

```text
1
-1
true
```

- `indexOf()` returns the position, or `-1` if not found.
- `includes()` returns `true` or `false`.

### 🎯 `find()` and `findIndex()`

Use these when you need to search with a **condition**.

```javascript
const numbers = [5, 12, 8, 130, 44];

console.log(numbers.find((n) => n > 10));
console.log(numbers.findIndex((n) => n > 10));
console.log(numbers.find((n) => n > 1000));
```

### 📤 Output

```text
12
1
undefined
```

- `find()` returns the **first element** that passes the test.
- `findIndex()` returns its **position** (`-1` if none).

### ✅ `some()` and `every()`

```javascript
const marks = [45, 60, 80];

console.log(marks.some((m) => m > 75));
console.log(marks.every((m) => m >= 40));
```

### 📤 Output

```text
true
true
```

- `some()` is `true` if **at least one** element passes.
- `every()` is `true` only if **all** elements pass.

---

## 🔁 6. Looping Through Arrays

```javascript
const colors = ["red", "green", "blue"];

// 1. Classic for loop
for (let i = 0; i < colors.length; i++) {
    console.log(i + ": " + colors[i]);
}

// 2. for...of loop (values only)
for (const color of colors) {
    console.log(color);
}

// 3. forEach() method
colors.forEach((color, index) => {
    console.log(`${index} -> ${color}`);
});
```

### 📤 Output

```text
0: red
1: green
2: blue
red
green
blue
0 -> red
1 -> green
2 -> blue
```

### 📊 Which Loop to Use?

| Loop | Best for |
|---|---|
| `for` | When you need full control (counting, skipping, stopping early with `break`) |
| `for...of` | Simply reading each value ⭐ |
| `forEach()` | Running a function for each element (cannot be stopped with `break`) |

---

## 🔄 7. Transforming Arrays: `map`, `filter`, `reduce` ⭐

These three are the most important array methods in modern JavaScript. They **return a new result** and do **not** change the original array.

### 🗺️ `map()`: Transform every element

```javascript
const nums = [1, 2, 3];
const doubled = nums.map((n) => n * 2);

console.log(doubled);
console.log(nums);
```

### 📤 Output

```text
[ 2, 4, 6 ]
[ 1, 2, 3 ]
```

### 🧹 `filter()`: Keep only elements that pass a test

```javascript
const all = [1, 2, 3, 4, 5, 6];
const evens = all.filter((n) => n % 2 === 0);

console.log(evens);
```

### 📤 Output

```text
[ 2, 4, 6 ]
```

### ➕ `reduce()`: Combine all elements into one value

```javascript
const prices = [1, 2, 3, 4];
const total = prices.reduce((sum, n) => sum + n, 0);

console.log(total);
```

### 📤 Output

```text
10
```

### 🔍 How `reduce()` Works

```text
reduce((sum, n) => sum + n, 0)

Start:    sum = 0
Step 1:   sum = 0 + 1 = 1
Step 2:   sum = 1 + 2 = 3
Step 3:   sum = 3 + 3 = 6
Step 4:   sum = 6 + 4 = 10   ← final result
```

The `0` at the end is the **starting value** of `sum`.

### 📊 Summary

| Method | Input → Output | Purpose |
|---|---|---|
| `map()` | Array → **Array of the same length** | Change each element |
| `filter()` | Array → **Shorter (or equal) array** | Keep matching elements |
| `reduce()` | Array → **Single value** | Combine into one result |

### ⛓️ Chaining Them Together

```javascript
const scores = [35, 80, 55, 90, 20];

const result = scores
    .filter((s) => s >= 40)
    .map((s) => s + 5);

console.log(result);
```

### 📤 Output

```text
[ 85, 60, 95 ]
```

---

## 🔢 8. Sorting and Reversing

### 🔤 Sorting Text

```javascript
const names = ["Mango", "Apple", "Banana"];
names.sort();
console.log(names);
```

### 📤 Output

```text
[ 'Apple', 'Banana', 'Mango' ]
```

### ⚠️ The Number-Sorting Trap

By default, `sort()` converts elements to **strings** and compares them alphabetically.

```javascript
const nums = [10, 9, 1, 100];
nums.sort();
console.log(nums);
```

### 📤 Output

```text
[ 1, 10, 100, 9 ]
```

That is wrong for numbers! Provide a **compare function**:

```javascript
const nums2 = [10, 9, 1, 100];

nums2.sort((a, b) => a - b);
console.log(nums2);

nums2.sort((a, b) => b - a);
console.log(nums2);
```

### 📤 Output

```text
[ 1, 9, 10, 100 ]
[ 100, 10, 9, 1 ]
```

### 🔍 Compare Function Rule

| Return value | Meaning |
|---|---|
| Negative (`a - b < 0`) | `a` comes **before** `b` |
| Positive (`a - b > 0`) | `a` comes **after** `b` |
| Zero | Keep the order |

### 🔃 `reverse()`

```javascript
const arr = [1, 2, 3];
arr.reverse();
console.log(arr);
```

### 📤 Output

```text
[ 3, 2, 1 ]
```

> ⚠️ `sort()` and `reverse()` **change the original array**. To get a sorted copy without changing the original, use `[...arr].sort(...)` or the modern `toSorted()` and `toReversed()` methods.

### 🪢 `join()`: Array → String

```javascript
const skills = ["HTML", "CSS", "JS"];
console.log(skills.join(", "));
console.log(skills.join(" | "));
```

### 📤 Output

```text
HTML, CSS, JS
HTML | CSS | JS
```

---

## ✨ 9. Destructuring

Pull values out of an array into variables.

```javascript
const [first, second] = ["a", "b", "c"];
console.log(first, second);

const [x, , z] = [1, 2, 3];       // skip the middle one
console.log(x, z);

const [head, ...tail] = [1, 2, 3, 4];   // rest of the elements
console.log(head);
console.log(tail);
```

### 📤 Output

```text
a b
1 3
1
[ 2, 3, 4 ]
```

### 🔄 Swapping Two Variables

```javascript
let p = 1;
let q = 2;

[p, q] = [q, p];
console.log(p, q);
```

### 📤 Output

```text
2 1
```

---

## 🪆 10. Nested Arrays and Arrays of Objects

### 🧱 Nested Arrays (2D Arrays)

```javascript
const matrix = [
    [1, 2],
    [3, 4]
];

console.log(matrix[1][0]);
console.log(matrix[0].length);
```

### 📤 Output

```text
3
2
```

### 🧾 Array of Objects ⭐

Real applications usually store records as an array of objects.

```javascript
const students = [
    { name: "Aman", marks: 80 },
    { name: "Priya", marks: 92 },
    { name: "Riya", marks: 67 }
];

const toppers = students
    .filter((s) => s.marks >= 75)
    .map((s) => s.name);

console.log(toppers);

const best = students.find((s) => s.marks > 90);
console.log(best.name);
```

### 📤 Output

```text
[ 'Aman', 'Priya' ]
Priya
```

---

## 🛒 11. Mini Example: Shopping Cart Total

```javascript
const cart = [
    { item: "Pen", price: 10, qty: 3 },
    { item: "Book", price: 150, qty: 1 },
    { item: "Bag", price: 500, qty: 1 }
];

const total = cart.reduce((sum, i) => sum + i.price * i.qty, 0);
const names = cart.map((i) => i.item).join(", ");

console.log("Items: " + names);
console.log("Total: " + total);
```

### 📤 Output

```text
Items: Pen, Book, Bag
Total: 680
```

### 🔍 What Happens?

- `map()` collects the item names, and `join()` makes them a single string.
- `reduce()` multiplies price by quantity for each item and adds them up.

---

## 📋 12. Mutating vs Non-Mutating Methods

| 🔴 **Changes the original array** | 🟢 **Returns a new result (original unchanged)** |
|---|---|
| `push()`, `pop()` | `slice()` |
| `shift()`, `unshift()` | `concat()` |
| `splice()` | `map()`, `filter()` |
| `sort()`, `reverse()` | `reduce()` |
| | `join()`, `indexOf()`, `includes()`, `find()` |

---

## ⚠️ 13. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Using `arr.length()` | `length` is a property: `arr.length` |
| `[10, 9, 1].sort()` for numbers | `sort((a, b) => a - b)` |
| `const b = a` and expecting a copy | `const b = [...a]` |
| Confusing `slice()` (copy) with `splice()` (changes the array) | `slice` extracts; `splice` modifies |
| Forgetting that `slice(1, 3)` excludes index 3 | The `end` index is not included |
| Forgetting the initial value in `reduce()` | Always provide one, like `reduce(fn, 0)` |
| Expecting `forEach()` to return a new array | Use `map()` to build a new array |
| Using `map()` just to loop | Use `forEach()` or `for...of` when you don't need a result |

---

## 🧪 14. Practice Tasks

- [ ] 🟢 **Beginner:** Create an array of 5 cities and print the first, last, and total count.
- [ ] 🟢 **Beginner:** Add a city at the end and remove the first one.
- [ ] 🟡 **Intermediate:** Loop through an array of numbers and print the square of each using `forEach()`.
- [ ] 🟡 **Intermediate:** From `[1, 2, 3, 4, 5, 6]`, create a new array with only the odd numbers using `filter()`.
- [ ] 🔵 **Practice:** Find the sum and average of an array of marks using `reduce()`.
- [ ] 🔵 **Practice:** Sort `[40, 5, 100, 21]` in ascending and descending order.
- [ ] 🔴 **Challenge:** Given an array of student objects, print the names of those who passed (marks 40 or more) in uppercase.
- [ ] 🔴 **Challenge:** Write a function that finds the largest number in an array without using `Math.max()`.

---

## 🎤 15. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is an array?**

**Answer:** An array is an ordered collection of values stored in a single variable, accessed by index numbers starting from 0.

**Q2. How do you create an array?**

**Answer:** Using square brackets, for example `const fruits = ["Apple", "Banana"];`.

**Q3. How do you find the number of elements in an array?**

**Answer:** Using the `length` property, for example `fruits.length`.

**Q4. How do you access the last element of an array?**

**Answer:** Using `arr[arr.length - 1]` or `arr.at(-1)`.

**Q5. What do `push()`, `pop()`, `shift()`, and `unshift()` do?**

**Answer:** `push()` adds to the end, `pop()` removes from the end, `unshift()` adds to the start, and `shift()` removes from the start.

### 🟡 Intermediate Questions

**Q6. How do you check whether a value is an array?**

**Answer:** Using `Array.isArray(value)`, because `typeof` returns `"object"` for arrays.

**Q7. What is the difference between `slice()` and `splice()`?**

**Answer:** `slice()` returns a copy of a portion without changing the original array. `splice()` adds, removes, or replaces elements and changes the original array.

**Q8. What is the difference between `indexOf()` and `includes()`?**

**Answer:** `indexOf()` returns the position of an element (or `-1`), while `includes()` returns `true` or `false`.

**Q9. What is the difference between `find()` and `filter()`?**

**Answer:** `find()` returns the first matching element (or `undefined`), while `filter()` returns a new array of all matching elements.

**Q10. What is the difference between `forEach()` and `map()`?**

**Answer:** `forEach()` runs a function for each element and returns `undefined`, while `map()` returns a new array containing the results of the function.

**Q11. What does `reduce()` do?**

**Answer:** It processes every element and combines them into a single value, using an accumulator and an optional initial value.

**Q12. Can you change a `const` array?**

**Answer:** Yes, you can change its contents (for example with `push()`), but you cannot reassign the variable to a new array.

### 🔵 Practical Questions

**Q13. Why does `[10, 9, 1, 100].sort()` give `[1, 10, 100, 9]`?**

**Answer:** The default `sort()` converts elements to strings and compares them alphabetically. For numbers, use `sort((a, b) => a - b)`.

**Q14. What is the output of the following code?**

```javascript
const a = [1, 2, 3];
const b = a;
b.push(4);
console.log(a);
```

**Answer:** `[1, 2, 3, 4]`, because `a` and `b` refer to the same array.

**Q15. How do you create a copy of an array?**

**Answer:** Using the spread operator `[...arr]` or `arr.slice()`. Both create a shallow copy.

**Q16. Which array methods change the original array?**

**Answer:** `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, `sort()`, and `reverse()`.

**Q17. What does the following code return?**

```javascript
[1, 2, 3, 4].reduce((sum, n) => sum + n, 0);
```

**Answer:** `10`.

**Q18. How do you convert an array to a string?**

**Answer:** Using `join()`, for example `["a", "b"].join("-")` gives `"a-b"`.

**Q19. What is the difference between `some()` and `every()`?**

**Answer:** `some()` returns `true` if at least one element passes the test; `every()` returns `true` only if all elements pass.

**Q20. How do you swap two variables using array destructuring?**

**Answer:** `[a, b] = [b, a];`

---

## 🏆 16. Key Takeaways

- 📚 An array is an ordered list of values, indexed from `0`.
- ➕ `push`, `pop`, `shift`, `unshift`, and `splice` add or remove elements and change the original array.
- 🍰 `slice` and `concat` create new arrays without changing the original.
- 🔍 Use `includes`, `indexOf`, `find`, `some`, and `every` to search.
- 🔁 Use `for...of` or `forEach` to loop.
- 🔄 `map` transforms, `filter` selects, and `reduce` combines. They are the core of modern JavaScript.
- 🔢 Always pass a compare function when sorting numbers.
- 🧬 Arrays are copied by reference, so use `[...arr]` for a real copy.
- ✨ Destructuring and spread keep array code short and clean.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Almost every real application works with lists of data, so arrays are among the most valuable things you will learn.

**Happy Coding! 💻✨**
