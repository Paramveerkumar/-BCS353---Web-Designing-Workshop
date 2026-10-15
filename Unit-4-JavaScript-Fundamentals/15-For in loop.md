# 🗝️ JavaScript for...in Loop

> 🎯 **Learning Objectives**
> - Understand what the `for...in` loop does and when to use it.
> - Loop through the keys and values of an object.
> - Know why `for...in` is not recommended for arrays.
> - Understand inherited properties and how to filter them.
> - Differentiate between `for...in` and `for...of`.

---

## 🌟 1. What is the for...in Loop?

The **`for...in` loop** goes through the **keys (property names)** of an object, one by one.

Imagine a **school notice board with labelled folders**. 🗂️

| Folder label (key) | Contents (value) |
|---|---|
| 🏷️ name | `"Aman"` |
| 🏷️ age | `20` |
| 🏷️ branch | `"CSE"` |

A `for...in` loop walks along the board and reads **each label**. You then use the label to open the folder and get the value.

### 🧠 Remember This!

- `for...in` gives you **keys**, not values.
- It is designed for **objects**.
- The key is always a **string**.

---

## 💻 2. Your First for...in Loop

```javascript
const student = {
    name: "Aman",
    age: 20,
    branch: "CSE"
};

for (const key in student) {
    console.log(key + ": " + student[key]);
}
```

### 📤 Output

```text
name: Aman
age: 20
branch: CSE
```

### 🧩 Syntax

```javascript
for (const key in object) {
    // use key and object[key]
}
```

### 🔍 Explanation

| Part | Meaning |
|---|---|
| `key` | A variable that holds the current property name (`"name"`, then `"age"`, then `"branch"`) |
| `in student` | The object to loop through |
| `student[key]` | Gets the **value** using bracket notation |

> ⚠️ Use **`student[key]`**, not `student.key`. The dot version looks for a property literally named `"key"` and gives `undefined`.

```javascript
for (const key in student) {
    console.log(student.key);   // ❌ undefined, undefined, undefined
}
```

💡 **Try It Yourself:** Create an object `book` with title, author, and price, and print every key and value.

---

## 🛠️ 3. Common Uses

### 🔢 Counting Properties

```javascript
let count = 0;

for (const key in student) {
    count++;
}

console.log("Total properties: " + count);
```

### 📤 Output

```text
Total properties: 3
```

### ➕ Adding Up Values

```javascript
const marks = { math: 80, science: 90, english: 70 };
let total = 0;

for (const subject in marks) {
    total += marks[subject];
}

console.log("Total: " + total);
console.log("Average: " + total / 3);
```

### 📤 Output

```text
Total: 240
Average: 80
```

### 🔍 Using `break` and `continue`

Both work inside `for...in`.

```javascript
for (const subject in marks) {
    if (subject === "science") {
        continue;
    }
    console.log(subject);
}
```

### 📤 Output

```text
math
english
```

### 🪆 Nested Objects

```javascript
const user = {
    name: "Riya",
    address: { city: "Delhi", pin: 110001 }
};

for (const key in user) {
    if (typeof user[key] === "object") {
        for (const inner in user[key]) {
            console.log(`${key}.${inner}: ${user[key][inner]}`);
        }
    } else {
        console.log(`${key}: ${user[key]}`);
    }
}
```

### 📤 Output

```text
name: Riya
address.city: Delhi
address.pin: 110001
```

---

## 🔢 4. Order of Keys

`for...in` follows a specific order:

1. **Whole-number keys** come first, in **ascending** order.
2. **Other keys** follow, in the order they were **added**.

```javascript
const obj = { b: 1, a: 2, 2: "x", 1: "y" };

for (const key in obj) {
    console.log(key);
}
```

### 📤 Output

```text
1
2
b
a
```

---

## ⚠️ 5. for...in with Arrays (Not Recommended)

It works, but it has surprises.

```javascript
const colors = ["red", "green"];

for (const i in colors) {
    console.log(i, typeof i);
}
```

### 📤 Output

```text
0 string
1 string
```

### 🪤 Problem 1: The Index is a String

```javascript
for (const i in colors) {
    console.log(i + 1);
}
```

### 📤 Output

```text
01
11
```

`"0" + 1` joins as text instead of adding numbers.

### 🪤 Problem 2: Extra Properties Appear

```javascript
colors.extra = "surprise";

for (const i in colors) {
    console.log(i);
}
```

### 📤 Output

```text
0
1
extra
```

### ✅ Better Choices for Arrays

```javascript
for (const color of colors) {          // values
    console.log(color);
}

colors.forEach((color, index) => {     // values and index
    console.log(index, color);
});
```

---

## 🧬 6. Inherited Properties

`for...in` also visits properties an object **inherits** from its prototype (parent object).

```javascript
const parent = { country: "India" };
const child = Object.create(parent);
child.name = "Aman";

for (const key in child) {
    console.log(key);
}
```

### 📤 Output

```text
name
country
```

`country` belongs to `parent`, but `child` inherits it, so the loop shows it too.

### 🧹 Filtering Only the Object's Own Properties

```javascript
for (const key in child) {
    if (Object.hasOwn(child, key)) {
        console.log(key);
    }
}
```

### 📤 Output

```text
name
```

> 💡 For plain objects like `{ name: "Aman" }`, there are no inherited custom properties, so this problem rarely appears. It matters when objects are created from other objects or classes.

---

## 🆚 7. for...in vs for...of

| Feature | `for...in` | `for...of` |
|---|---|---|
| Gives you | **Keys** (property names) | **Values** |
| Works on | Objects ⭐ | Arrays, strings, Maps, Sets (iterables) |
| Works on plain objects? | ✅ Yes | ❌ No (objects are not iterable) |
| Good for arrays? | ❌ No | ✅ Yes |
| Includes inherited properties? | ✅ Yes | Not applicable |

```javascript
const arr = ["a", "b"];

for (const x in arr) console.log(x);    // 0, 1  (keys)
for (const x of arr) console.log(x);    // a, b  (values)
```

### 📤 Output

```text
0
1
a
b
```

### ❌ `for...of` Does Not Work on Plain Objects

```javascript
const obj = { a: 1 };

for (const x of obj) {
    console.log(x);
}
```

### 📤 Output

```text
TypeError: obj is not iterable
```

### 🌟 A Modern Alternative for Objects

`Object.entries()` gives `[key, value]` pairs, and avoids inherited properties.

```javascript
for (const [key, value] of Object.entries(student)) {
    console.log(`${key} => ${value}`);
}
```

### 📤 Output

```text
name => Aman
age => 20
branch => CSE
```

---

## 🧭 8. Which Loop Should I Use?

| Situation | Best choice |
|---|---|
| Read every key/value of an **object** | `for...in` or `Object.entries()` with `for...of` |
| Read every value of an **array** | `for...of` |
| Need the **index** of an array | `for` or `forEach()` |
| Repeat something a fixed number of times | `for` |

---

## ⚠️ 9. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| `student.key` inside the loop | `student[key]` |
| Using `for...in` on arrays | Use `for...of` or `forEach()` |
| Treating the array index as a number | The index is a **string**; convert with `Number(i)` if needed |
| Using `for...of` on a plain object | Use `for...in` or `Object.entries()` |
| Ignoring inherited properties | Filter with `Object.hasOwn(obj, key)` |
| Relying on key order for non-numeric keys when order is critical | Use an array of objects instead |

---

## 🧪 10. Practice Tasks

- [ ] 🟢 **Beginner:** Create an object with 4 properties and print every key and value using `for...in`.
- [ ] 🟢 **Beginner:** Count how many properties an object has.
- [ ] 🟡 **Intermediate:** Given an object of subject marks, find the total and the average.
- [ ] 🟡 **Intermediate:** Given `{ apple: 50, banana: 20, mango: 80 }`, print only the fruits that cost more than 30.
- [ ] 🔵 **Practice:** Find the subject with the highest marks in an object of marks.
- [ ] 🔴 **Challenge:** Write a function that takes an object and returns a new object with all the **values doubled**.

---

## 🎤 11. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is the `for...in` loop?**

**Answer:** A loop that iterates over the enumerable property names (keys) of an object.

**Q2. What is the syntax of `for...in`?**

**Answer:** `for (const key in object) { // code }`

**Q3. What does the loop variable contain in `for...in`?**

**Answer:** The key (property name) as a string.

**Q4. How do you get the value of the current property inside the loop?**

**Answer:** Using bracket notation, `object[key]`.

**Q5. Why does `object.key` not work inside the loop?**

**Answer:** The dot notation looks for a property literally named `"key"`, so it returns `undefined`. Bracket notation uses the value stored in the variable.

### 🟡 Intermediate Questions

**Q6. What is the difference between `for...in` and `for...of`?**

**Answer:** `for...in` iterates over keys and is meant for objects, while `for...of` iterates over values of iterable objects like arrays and strings.

**Q7. Why is `for...in` not recommended for arrays?**

**Answer:** The index is returned as a string, it can include extra properties added to the array, and the order is not guaranteed to suit all situations. `for...of` or `forEach()` is better.

**Q8. Does `for...in` include inherited properties?**

**Answer:** Yes, it includes enumerable properties inherited through the prototype chain. They can be filtered with `Object.hasOwn(obj, key)`.

**Q9. In what order does `for...in` visit keys?**

**Answer:** Whole-number keys first in ascending order, followed by other keys in the order they were added.

**Q10. Can you use `break` and `continue` in `for...in`?**

**Answer:** Yes, both work as in other loops.

### 🔵 Practical Questions

**Q11. What is the output of the following code?**

```javascript
const arr = ["a", "b"];
for (const i in arr) {
    console.log(i);
}
```

**Answer:** `0` and `1`. It prints the indexes (as strings), not the values.

**Q12. What is the output of `for (const x of { a: 1 }) {}`?**

**Answer:** A `TypeError`, because plain objects are not iterable and cannot be used with `for...of`.

**Q13. What is a modern alternative to `for...in` for objects?**

**Answer:** Looping over `Object.entries(obj)` with `for...of`, which gives `[key, value]` pairs and only includes the object's own properties.

---

## 🏆 12. Key Takeaways

- 🗝️ `for...in` loops over the **keys** of an object.
- 🔍 Use `object[key]` (bracket notation) to get each value.
- 🔢 Keys are always strings, and whole-number keys come first in ascending order.
- ⚠️ Avoid `for...in` for arrays. Use `for...of` or `forEach()`.
- 🧬 It also visits inherited properties, so filter with `Object.hasOwn()` when needed.
- 🌟 `Object.entries()` with `for...of` is a clean modern alternative.

---

### 🚀 Keep Practising!

> 💡 **Remember:** `for...in` is for **i**nspecting object keys, and `for...of` is for going through the values.

**Happy Coding! 💻✨**
