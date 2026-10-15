# 🧾 JavaScript Objects

> 🎯 **Learning Objectives**
> - Understand what an object is and why we need it.
> - Create objects and access, add, update, and delete properties.
> - Write methods and understand the `this` keyword.
> - Work with nested objects and loop through properties.
> - Use destructuring, spread, and optional chaining.
> - Understand that objects are copied by reference.

---

## 🌟 1. What is an Object?

An **object** is a collection of related data stored as **key-value pairs**. Each pair is called a **property**.

Think of a **student ID card**. 🪪

| Key (label) | Value (data) |
|---|---|
| 🏷️ name | `"Aman"` |
| 🏷️ age | `20` |
| 🏷️ branch | `"CSE"` |

Instead of creating separate variables like `studentName`, `studentAge`, and `studentBranch`, we keep everything about one student together in **one object**.

### 🧠 Remember This!

- An object stores data as **key: value** pairs.
- Keys are names (strings); values can be **any type**, including other objects and functions.
- A function stored inside an object is called a **method**.

---

## 💻 2. Creating an Object

The most common way is the **object literal** using `{ }`.

```javascript
const student = {
    name: "Aman",
    age: 20,
    branch: "CSE"
};

console.log(student);
```

### 📤 Output

```text
{ name: 'Aman', age: 20, branch: 'CSE' }
```

### 🔍 Explanation

- Curly braces `{ }` create the object.
- Each property is written as `key: value`.
- Properties are separated by **commas**.
- We used `const` because we will not reassign the variable (we can still change what is inside).

### 🧩 Syntax

```javascript
const objectName = {
    key1: value1,
    key2: value2
};
```

💡 **Try It Yourself:** Create an object `book` with `title`, `author`, and `price`, then print it.

---

## 🔑 3. Accessing Properties

### 🟢 Dot Notation

```javascript
console.log(student.name);
console.log(student.age);
```

### 🔵 Bracket Notation

```javascript
console.log(student["branch"]);

let key = "name";
console.log(student[key]);
```

### 📤 Output

```text
Aman
20
CSE
Aman
```

### ❔ Property That Does Not Exist

```javascript
console.log(student.city);
```

### 📤 Output

```text
undefined
```

### 🆚 Dot vs Bracket

| Dot `obj.key` | Bracket `obj["key"]` |
|---|---|
| Shorter and cleaner | Needed when the key is stored in a **variable** |
| Key must be a valid name | Works for keys with **spaces** or special characters |
| Example: `student.name` | Example: `student["first name"]` |

---

## ✏️ 4. Adding, Updating, and Deleting

```javascript
const student = { name: "Aman", age: 20, branch: "CSE" };

student.age = 21;            // update
student.city = "Delhi";      // add
delete student.branch;       // delete

console.log(student);
```

### 📤 Output

```text
{ name: 'Aman', age: 21, city: 'Delhi' }
```

> 💡 Even though `student` is declared with `const`, its **contents** can change. `const` only prevents reassigning the variable itself.

---

## ⚙️ 5. Methods and `this`

A **method** is a function stored as a property.

```javascript
const student = {
    name: "Aman",
    marks: 85,

    greet() {
        console.log(`Hi, I am ${this.name}`);
    },

    isPassed() {
        return this.marks >= 40;
    }
};

student.greet();
console.log(student.isPassed());
```

### 📤 Output

```text
Hi, I am Aman
true
```

### 🔍 Explanation

- `greet()` and `isPassed()` are methods.
- Inside a method, **`this`** refers to the object the method was called on.
- So `this.name` means `student.name`.

### ⚠️ Arrow Functions and `this`

Arrow functions do **not** have their own `this`, so avoid them for object methods.

```javascript
const person = {
    name: "Aman",
    sayHi: () => {
        console.log(this.name);   // does NOT print "Aman"
    }
};

person.sayHi();
```

✅ Use the normal method syntax (`sayHi() { ... }`) when you need `this`.

---

## 🪆 6. Nested Objects

An object can contain other objects.

```javascript
const user = {
    name: "Riya",
    address: {
        city: "Delhi",
        pin: 110001
    },
    skills: ["HTML", "CSS", "JavaScript"]
};

console.log(user.address.city);
console.log(user.skills[2]);
```

### 📤 Output

```text
Delhi
JavaScript
```

### 🛟 Optional Chaining `?.`

Accessing a property of something that does not exist causes an error. `?.` prevents it.

```javascript
console.log(user.contact?.phone);
console.log(user.contact.phone);
```

### 📤 Output

```text
undefined
TypeError: Cannot read properties of undefined (reading 'phone')
```

- `user.contact` does not exist, so it is `undefined`.
- With `?.`, JavaScript stops safely and returns `undefined`.
- Without it, you get a `TypeError`.

---

## 🔁 7. Looping Through an Object

```javascript
const student = { name: "Aman", age: 20, branch: "CSE" };

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

### 🧰 Useful Helper Methods

```javascript
console.log(Object.keys(student));
console.log(Object.values(student));

for (const [key, value] of Object.entries(student)) {
    console.log(`${key} => ${value}`);
}
```

### 📤 Output

```text
[ 'name', 'age', 'branch' ]
[ 'Aman', 20, 'CSE' ]
name => Aman
age => 20
branch => CSE
```

| Method | Returns |
|---|---|
| `Object.keys(obj)` | An array of the keys |
| `Object.values(obj)` | An array of the values |
| `Object.entries(obj)` | An array of `[key, value]` pairs |

---

## 🔍 8. Checking if a Property Exists

```javascript
const student = { name: "Aman", age: 20 };

console.log("name" in student);
console.log("city" in student);
console.log(Object.hasOwn(student, "age"));
```

### 📤 Output

```text
true
false
true
```

> 💡 Comparing with `undefined` (`student.city === undefined`) is not a reliable check, because a property can exist and still hold `undefined`.

---

## ✨ 9. Modern Shortcuts

### 🟢 Property Shorthand

If the variable name matches the key, you can write it once.

```javascript
const name = "Aman";
const age = 20;

const student = { name, age };
console.log(student);
```

### 📤 Output

```text
{ name: 'Aman', age: 20 }
```

### 🟡 Computed Keys

Use `[ ]` to build a key from a variable.

```javascript
const field = "score";
const result = { [field]: 90 };
console.log(result);
```

### 📤 Output

```text
{ score: 90 }
```

### 🔵 Destructuring

Pull properties out into variables.

```javascript
const student = { name: "Aman", age: 20, branch: "CSE" };

const { name, age } = student;
console.log(name, age);

const { branch: course } = student;     // rename
console.log(course);

const { city = "Unknown" } = student;   // default value
console.log(city);
```

### 📤 Output

```text
Aman 20
CSE
Unknown
```

### 🔴 Spread Operator (Copy and Merge)

```javascript
const original = { name: "Aman", age: 20 };
const copy = { ...original, age: 25 };

console.log(original);
console.log(copy);
```

### 📤 Output

```text
{ name: 'Aman', age: 20 }
{ name: 'Aman', age: 25 }
```

> ⚠️ Spread makes a **shallow** copy. Nested objects inside are still shared between the original and the copy.

---

## 🧬 10. Objects Are Copied by Reference

```javascript
const a = { score: 1 };
const b = a;
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

- `a` and `b` both point to the **same** object in memory.
- Changing it through one variable changes it for both.

### ⚖️ Comparing Objects

```javascript
console.log({} === {});

const x = { n: 1 };
const y = x;
console.log(x === y);
```

### 📤 Output

```text
false
true
```

Two separately created objects are never equal, even if they look identical. Objects are equal only when they are the **same reference**.

### 🔒 Preventing Changes with `Object.freeze()`

```javascript
const settings = Object.freeze({ theme: "dark" });
settings.theme = "light";

console.log(settings.theme);
```

### 📤 Output

```text
dark
```

The change is ignored (or throws a `TypeError` in strict mode). Note that `freeze` is shallow too.

---

## 📚 11. Array of Objects

Real applications store many records, so objects and arrays are often combined.

```javascript
const students = [
    { name: "Aman", marks: 80 },
    { name: "Priya", marks: 92 },
    { name: "Riya", marks: 67 }
];

console.log(students[1].name);

students.forEach((s) => {
    console.log(`${s.name}: ${s.marks}`);
});
```

### 📤 Output

```text
Priya
Aman: 80
Priya: 92
Riya: 67
```

---

## 📄 12. Objects and JSON

**JSON** is a text format for sending data between programs. JavaScript can convert objects to JSON text and back.

```javascript
const student = { name: "Aman", age: 20 };

const text = JSON.stringify(student);
console.log(text);
console.log(typeof text);

const obj = JSON.parse(text);
console.log(obj.name);
```

### 📤 Output

```text
{"name":"Aman","age":20}
string
Aman
```

| Method | Purpose |
|---|---|
| `JSON.stringify(obj)` | Object → JSON string |
| `JSON.parse(text)` | JSON string → Object |

---

## 🏦 13. Mini Example: Bank Account

```javascript
const account = {
    owner: "Aman",
    balance: 1000,

    deposit(amount) {
        this.balance += amount;
        return this.balance;
    },

    withdraw(amount) {
        if (amount > this.balance) {
            console.log("Insufficient balance ❌");
            return this.balance;
        }
        this.balance -= amount;
        return this.balance;
    }
};

console.log(account.deposit(500));
console.log(account.withdraw(200));
account.withdraw(5000);
console.log(account.balance);
```

### 📤 Output

```text
1500
1300
Insufficient balance ❌
1300
```

### 🔍 What Happens?

- Data (`owner`, `balance`) and behaviour (`deposit`, `withdraw`) live together in one object.
- Methods use `this` to read and change the object's own data.

---

## ⚠️ 14. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Forgetting commas between properties | Separate properties with `,` |
| Using `=` instead of `:` inside `{ }` | Write `key: value` |
| Using `student.key` when the key is in a variable | Use `student[key]` |
| Using an arrow function as a method that needs `this` | Use the normal method syntax |
| Expecting `const` to make an object unchangeable | Use `Object.freeze()` |
| Thinking `const copy = original` makes a copy | Use `{ ...original }` |
| Reading deep properties without checking | Use optional chaining `?.` |

---

## 🧪 15. Practice Tasks

- [ ] 🟢 **Beginner:** Create an object `book` with title, author, and price, and print each property.
- [ ] 🟢 **Beginner:** Add a new property `pages` to `book` and delete `price`.
- [ ] 🟡 **Intermediate:** Add a method `describe()` to `book` that prints "Title by Author".
- [ ] 🟡 **Intermediate:** Loop through an object and print every key and value.
- [ ] 🔵 **Practice:** Create a `user` object with a nested `address` object and print the city.
- [ ] 🔵 **Practice:** Use destructuring to extract `name` and `age` from a student object.
- [ ] 🔴 **Challenge:** Create an array of 3 student objects (name, marks) and print the name of the topper.
- [ ] 🔴 **Challenge:** Copy an object, change the copy, and prove that the original stays the same.

---

## 🎤 16. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is an object in JavaScript?**

**Answer:** An object is a collection of related data stored as key-value pairs, called properties.

**Q2. How do you create an object?**

**Answer:** Using an object literal, for example `const student = { name: "Aman", age: 20 };`.

**Q3. What are the two ways to access an object's property?**

**Answer:** Dot notation (`student.name`) and bracket notation (`student["name"]`).

**Q4. What is a method?**

**Answer:** A function stored as a property of an object.

**Q5. How do you delete a property from an object?**

**Answer:** Using the `delete` operator, for example `delete student.age;`.

### 🟡 Intermediate Questions

**Q6. When must you use bracket notation instead of dot notation?**

**Answer:** When the key is stored in a variable, or when the key contains spaces or special characters.

**Q7. What does the `this` keyword refer to inside an object method?**

**Answer:** The object on which the method was called.

**Q8. Why should arrow functions not be used as object methods?**

**Answer:** Arrow functions do not have their own `this`, so `this` will not refer to the object.

**Q9. What do `Object.keys()`, `Object.values()`, and `Object.entries()` return?**

**Answer:** Arrays of the object's keys, values, and `[key, value]` pairs respectively.

**Q10. How can you check whether a property exists in an object?**

**Answer:** Using the `in` operator (`"name" in obj`) or `Object.hasOwn(obj, "name")`.

**Q11. Can you modify an object declared with `const`?**

**Answer:** Yes. `const` prevents reassignment of the variable, but the properties of the object can still be changed.

**Q12. What is optional chaining?**

**Answer:** The `?.` operator safely accesses a property and returns `undefined` instead of throwing an error if the value before it is `null` or `undefined`.

### 🔵 Practical Questions

**Q13. What is destructuring?**

**Answer:** A syntax that extracts properties from an object into separate variables, for example `const { name, age } = student;`.

**Q14. What is the output of the following code?**

```javascript
const a = { n: 1 };
const b = a;
b.n = 2;
console.log(a.n);
```

**Answer:** `2`, because objects are copied by reference, so `a` and `b` point to the same object.

**Q15. What is the output of `console.log({} === {});`?**

**Answer:** `false`, because two separately created objects are different references, even if they look the same.

**Q16. How do you create a copy of an object?**

**Answer:** Using the spread syntax, for example `const copy = { ...original };`. This creates a shallow copy.

**Q17. What is the difference between a shallow copy and a deep copy?**

**Answer:** A shallow copy duplicates only the top-level properties, so nested objects are still shared. A deep copy duplicates everything, including nested objects (for example with `structuredClone()`).

**Q18. What is the difference between `JSON.stringify()` and `JSON.parse()`?**

**Answer:** `JSON.stringify()` converts an object to a JSON string, and `JSON.parse()` converts a JSON string back to an object.

---

## 🏆 17. Key Takeaways

- 🧾 An object stores related data as key-value pairs.
- 🔑 Access properties with dot notation or bracket notation.
- ✏️ Properties can be added, updated, or deleted at any time, even on a `const` object.
- ⚙️ A method is a function inside an object, and `this` refers to that object.
- 🪆 Objects can be nested; use `?.` to access deep properties safely.
- 🔁 Use `Object.keys()`, `Object.values()`, and `Object.entries()` to loop.
- ✨ Destructuring and spread make working with objects cleaner.
- 🧬 Objects are copied by reference, so use spread to copy them.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Almost everything in JavaScript is built on objects, so mastering them makes everything else easier.

**Happy Coding! 💻✨**
