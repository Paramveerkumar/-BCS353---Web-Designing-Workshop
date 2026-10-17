# 🚀 JavaScript Objects

Welcome to **JavaScript Objects!** 🎯

Objects are one of the most important concepts in JavaScript. They allow us to store related information and functions together in a single structure.

## 🎯 Learning Objectives

After completing this topic, students will be able to:

- ✅ Understand JavaScript objects and their properties.
- ✅ Create objects using different methods.
- ✅ Access, add, update, and delete properties.
- ✅ Use object methods and the `this` keyword.
- ✅ Understand nested objects and object destructuring.
- ✅ Work with object keys, values, and entries.
- ✅ Copy and combine objects.

---

## 🌟 1. What Is an Object?

A JavaScript **object** is a collection of properties, where each property has a key and a value.

Think of a student record in a college. It contains a name, roll number, branch, and marks.

```javascript
const student = {
    name: "Rahul",
    rollNo: 101,
    branch: "CSE",
    marks: 85
};

console.log(student);
```

**Output:**

```text
{
  name: 'Rahul',
  rollNo: 101,
  branch: 'CSE',
  marks: 85
}
```

📌 Here:

- `student` is the object.
- `name`, `rollNo`, `branch`, and `marks` are property keys.
- `"Rahul"`, `101`, `"CSE"`, and `85` are property values.

### 🏫 Real-World Examples

| Object | Properties |
|---|---|
| Student | Name, roll number, marks |
| Car | Brand, model, color |
| Mobile | Company, price, storage |
| Employee | Name, salary, department |

---

## 🧱 2. Creating an Object

The simplest way to create an object is by using **object literal syntax**.

```javascript
const car = {
    brand: "Tata",
    model: "Nexon",
    color: "Black"
};

console.log(car.brand);
```

**Output:**

```text
Tata
```

💡 The curly braces `{}` define the object, and each property is written as `key: value`.

---

## 🔍 3. Accessing Object Properties

JavaScript provides two common ways to access object properties.

### Method 1: Dot Notation (`.`)

```javascript
const student = {
    name: "Priya",
    age: 21,
    branch: "CSE"
};

console.log(student.name);
console.log(student.age);
```

**Output:**

```text
Priya
21
```

### Method 2: Bracket Notation (`[]`)

```javascript
const student = {
    name: "Priya",
    age: 21
};

console.log(student["name"]);
console.log(student["age"]);
```

**Output:**

```text
Priya
21
```

### 🤔 Dot Notation vs Bracket Notation

| Dot Notation | Bracket Notation |
|---|---|
| `student.name` | `student["name"]` |
| Property name is written directly | Property name is provided as a string or expression |
| Simple and readable | Useful for dynamic property names |
| Cannot directly use a variable as the property name | Can use a variable as the property name |

### Example: Dynamic Property Access

```javascript
const student = {
    name: "Amit",
    marks: 90
};

const property = "marks";

console.log(student[property]);
```

**Output:**

```text
90
```

📌 `student[property]` accesses the property whose name is stored in the variable `property`.

---

## ➕ 4. Adding New Properties

You can add a property to an existing object using dot notation or bracket notation.

```javascript
const student = {
    name: "Rahul"
};

student.age = 22;
student["branch"] = "IT";

console.log(student);
```

**Output:**

```text
{
  name: 'Rahul',
  age: 22,
  branch: 'IT'
}
```

---

## ✏️ 5. Updating Object Properties

You can change the value of an existing property.

```javascript
const student = {
    name: "Rahul",
    marks: 75
};

student.marks = 92;

console.log(student.marks);
```

**Output:**

```text
92
```

💡 The property `marks` already exists, so JavaScript updates its value instead of creating a second property with the same key.

---

## ❌ 6. Deleting Object Properties

Use the `delete` operator to remove a property from an object.

```javascript
const student = {
    name: "Rahul",
    age: 22,
    branch: "CSE"
};

delete student.age;

console.log(student);
```

**Output:**

```text
{
  name: 'Rahul',
  branch: 'CSE'
}
```

📌 `delete student.age` removes the `age` property.

---

## ⚙️ 7. Object Methods

A **method** is a function stored as an object property.

### Example: Student Introduction

```javascript
const student = {
    name: "Priya",
    branch: "CSE",

    introduce: function () {
        console.log(
            "My name is " + this.name +
            " and I study " + this.branch
        );
    }
};

student.introduce();
```

**Output:**

```text
My name is Priya and I study CSE
```

### 🧠 Understanding `this`

Inside this method, `this.name` refers to the `name` property of the object associated with the method call.

```javascript
const person = {
    name: "Amit",

    greet() {
        console.log("Hello, " + this.name);
    }
};

person.greet();
```

**Output:**

```text
Hello, Amit
```

⚠️ The value of `this` depends on how a function is called. Arrow functions do not create their own `this`, so regular methods are usually easier for beginners when accessing an object's properties.

---

## 🪆 8. Nested Objects

An object can contain another object as one of its properties. This is called a **nested object**.

### Example: Employee Details

```javascript
const employee = {
    name: "Amit",
    id: 501,

    address: {
        city: "Greater Noida",
        state: "Uttar Pradesh",
        pinCode: 201310
    }
};

console.log(employee.name);
console.log(employee.address.city);
console.log(employee.address.state);
```

**Output:**

```text
Amit
Greater Noida
Uttar Pradesh
```

### 🔍 Explanation

- `employee` is the outer object.
- `address` is a nested object.
- `employee.address.city` accesses the city property inside `address`.

---

## 🔄 9. Looping Through an Object

You can use a `for...in` loop to iterate over an object's enumerable property keys.

```javascript
const student = {
    name: "Rahul",
    branch: "CSE",
    marks: 88
};

for (const key in student) {
    console.log(key + ": " + student[key]);
}
```

**Output:**

```text
name: Rahul
branch: CSE
marks: 88
```

📌 In each iteration:

- `key` contains a property name.
- `student[key]` accesses the corresponding value.

---

## 🗝️ 10. Object.keys(), Object.values(), and Object.entries()

JavaScript provides useful built-in methods for working with an object's properties.

### A. `Object.keys()`

Returns an array of the object's own enumerable property names.

```javascript
const student = {
    name: "Rahul",
    age: 22,
    branch: "CSE"
};

console.log(Object.keys(student));
```

**Output:**

```text
["name", "age", "branch"]
```

### B. `Object.values()`

Returns an array of the corresponding property values.

```javascript
console.log(Object.values(student));
```

**Output:**

```text
["Rahul", 22, "CSE"]
```

### C. `Object.entries()`

Returns an array of key-value pairs.

```javascript
console.log(Object.entries(student));
```

**Output:**

```text
[
  ["name", "Rahul"],
  ["age", 22],
  ["branch", "CSE"]
]
```

### 📊 Quick Comparison

| Method | Returns | Example |
|---|---|---|
| `Object.keys(obj)` | Array of keys | `["name", "age"]` |
| `Object.values(obj)` | Array of values | `["Rahul", 22]` |
| `Object.entries(obj)` | Array of key-value pairs | `[["name", "Rahul"]]` |

---

## 🎁 11. Object Destructuring

**Destructuring** allows you to extract properties from an object and store their values in variables.

### Without Destructuring

```javascript
const student = {
    name: "Priya",
    age: 21
};

const name = student.name;
const age = student.age;

console.log(name, age);
```

### With Destructuring

```javascript
const student = {
    name: "Priya",
    age: 21
};

const { name, age } = student;

console.log(name);
console.log(age);
```

**Output:**

```text
Priya
21
```

💡 Destructuring is a shorter way to extract property values from objects.

### Renaming a Property During Destructuring

```javascript
const student = {
    name: "Rahul"
};

const { name: studentName } = student;

console.log(studentName);
```

**Output:**

```text
Rahul
```

Here, `name` is the property key, while `studentName` is the new variable.

---

## 🧬 12. Copying and Combining Objects

### A. `Object.assign()`

Copies enumerable own properties from one or more source objects into a target object.

```javascript
const student = {
    name: "Rahul",
    marks: 85
};

const copy = Object.assign({}, student);

console.log(copy);
```

**Output:**

```text
{ name: 'Rahul', marks: 85 }
```

### B. Spread Syntax (`...`)

The spread syntax provides a concise way to copy or combine object properties.

```javascript
const student = {
    name: "Rahul",
    marks: 85
};

const updatedStudent = {
    ...student,
    branch: "CSE"
};

console.log(updatedStudent);
```

**Output:**

```text
{
  name: 'Rahul',
  marks: 85,
  branch: 'CSE'
}
```

### C. Combining Two Objects

```javascript
const personal = {
    name: "Amit",
    age: 23
};

const academic = {
    branch: "IT",
    marks: 90
};

const student = {
    ...personal,
    ...academic
};

console.log(student);
```

**Output:**

```text
{
  name: 'Amit',
  age: 23,
  branch: 'IT',
  marks: 90
}
```

⚠️ These copying techniques create **shallow copies**. If an object contains nested objects, those nested objects are still shared between the original and the copy.

---

## 🔐 13. Checking Whether a Property Exists

Use the `in` operator to check whether a property exists on an object or anywhere in its prototype chain.

```javascript
const student = {
    name: "Rahul",
    marks: 85
};

console.log("name" in student);
console.log("age" in student);
```

**Output:**

```text
true
false
```

To check only an object's own properties, use `Object.hasOwn()`.

```javascript
console.log(Object.hasOwn(student, "name"));
console.log(Object.hasOwn(student, "toString"));
```

**Output:**

```text
true
false
```

📌 `toString` is normally inherited from the object's prototype, so it is not an own property of `student`.

---

## 🧊 14. Object.freeze() and Object.seal()

JavaScript provides methods to restrict changes to objects.

### A. `Object.freeze()`

Prevents adding or deleting properties and prevents changing existing property values through ordinary assignment.

```javascript
const user = {
    name: "Rahul"
};

Object.freeze(user);

user.name = "Amit";

console.log(user.name);
```

**Output in non-strict mode:**

```text
Rahul
```

In strict mode, attempting to change the frozen property throws a `TypeError`.

### B. `Object.seal()`

Prevents adding or deleting properties, but existing writable properties can still be updated.

```javascript
const user = {
    name: "Rahul"
};

Object.seal(user);

user.name = "Amit";

console.log(user.name);
```

**Output:**

```text
Amit
```

### 📊 Comparison

| Feature | `Object.freeze()` | `Object.seal()` |
|---|---|---|
| Add new properties | No | No |
| Delete properties | No | No |
| Update existing writable properties | No | Yes |
| Restricts object structure | Yes | Yes |

💡 Both are shallow operations: nested objects are not automatically frozen or sealed.

---

## 🧪 15. Practice Tasks

Try solving these problems yourself. 🚀

- [ ] **Task 1:** Create a `Student` object with name, roll number, branch, and marks.
- [ ] **Task 2:** Display each property using dot notation and bracket notation.
- [ ] **Task 3:** Add an `email` property to the student object.
- [ ] **Task 4:** Update the student's marks and delete the branch property.
- [ ] **Task 5:** Create a `Car` object with a method that displays its details.
- [ ] **Task 6:** Create an `Employee` object with a nested address object.
- [ ] **Task 7:** Print all keys and values using `Object.keys()` and `Object.values()`.
- [ ] **Task 8:** Extract `name` and `marks` using destructuring.
- [ ] **Task 9:** Combine two objects using spread syntax.
- [ ] **Task 10:** Create a shopping cart object containing product names, quantities, and prices.

---

# 🎤 16. Viva Voce Questions and Answers

## 🟢 Basic Questions

**Q1. What is an object in JavaScript?**

An object is a collection of properties that store related data and can also contain methods.

**Q2. How do you create an object in JavaScript?**

The simplest way is by using object literal syntax:

```javascript
const person = {
    name: "Rahul",
    age: 22
};
```

**Q3. What is a property?**

A property is a key-value association within an object.

**Q4. What is a method?**

A method is a function stored as an object property.

**Q5. How can you access an object's properties?**

Using dot notation, such as `person.name`, or bracket notation, such as `person["name"]`.

**Q6. How can you add a new property?**

Use assignment, for example, `person.city = "Delhi"`.

## 🟡 Intermediate Questions

**Q7. What is the difference between dot notation and bracket notation?**

Dot notation uses a property name directly. Bracket notation allows a string or expression, making it useful for dynamic property names.

**Q8. What is the purpose of the `this` keyword in an object method?**

It refers to the object associated with the method call, subject to JavaScript's `this` rules.

**Q9. What is a nested object?**

A nested object is an object stored as a property value inside another object.

**Q10. What does the `delete` operator do?**

It removes a configurable property from an object.

**Q11. What is the purpose of `Object.keys()`?**

It returns an array of an object's own enumerable property names.

**Q12. What is the difference between `Object.values()` and `Object.entries()`?**

`Object.values()` returns property values, while `Object.entries()` returns arrays containing each key-value pair.

**Q13. What is object destructuring?**

It is syntax for extracting property values into variables.

**Q14. What is the spread syntax used for with objects?**

It copies enumerable own properties into a new object or combines properties from multiple objects.

**Q15. What is the difference between a shallow copy and a deep copy?**

A shallow copy shares references to nested objects. A deep copy creates independent copies of nested data as well.

## 🔵 Practical Questions

**Q16. Can an object contain a function?**

Yes. A function stored as an object property can be called as a method.

**Q17. What happens if you access a property that does not exist?**

The result is normally `undefined`.

**Q18. What does the `in` operator do?**

It checks whether a property exists on an object or anywhere in its prototype chain.

**Q19. What is the difference between `Object.freeze()` and `Object.seal()`?**

Both restrict adding and deleting properties. `Object.freeze()` also prevents updating existing data properties, whereas `Object.seal()` allows updates to existing writable properties.

**Q20. Can a JavaScript object contain another object?**

Yes. An object can store another object as a property value.

**Q21. What is the difference between `const` and an immutable object?**

`const` prevents reassignment of the variable binding, but it does not automatically prevent changes to the object's properties.

**Q22. What does `Object.hasOwn()` check?**

It checks whether a property belongs directly to the object rather than being inherited.

**Q23. Are JavaScript objects mutable?**

Generally, yes. Their properties can be added, changed, or removed unless restrictions or other conditions prevent those changes.

**Q24. What is the difference between an array and an object?**

Arrays are specialized objects designed for ordered, index-based collections. Ordinary objects are commonly used for named properties.

**Q25. Why are objects useful in real-world applications?**

They help group related information and operations, making code easier to organize, reuse, and maintain.

---

## 🏆 17. Key Takeaways

- ✅ Objects store related data as key-value properties.
- ✅ Use dot notation or bracket notation to access properties.
- ✅ Objects can contain methods and nested objects.
- ✅ `this` helps methods access the associated object's data.
- ✅ `Object.keys()`, `Object.values()`, and `Object.entries()` help inspect properties.
- ✅ Destructuring and spread syntax make object operations concise.
- ✅ Shallow copies do not independently copy nested objects.
- ✅ `Object.freeze()` and `Object.seal()` restrict modifications in different ways.

> 💡 **Remember:** Objects are everywhere in JavaScript—from student records and shopping carts to API responses and application settings.

🎉 **Happy Coding! Keep Practicing JavaScript!** 🚀
