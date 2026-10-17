# 🚀 JavaScript Prototypes

Welcome to **Prototypes in JavaScript!** 🎯

Prototypes are an important concept in JavaScript that help us understand **inheritance, object relationships, and code reuse**.

In JavaScript, objects can access properties and methods from other objects through a mechanism called the **prototype chain**.

## 🎯 Learning Objectives

After completing this topic, students will be able to:

- ✅ Understand prototypes in JavaScript.
- ✅ Explain the prototype chain.
- ✅ Use `Object.getPrototypeOf()`.
- ✅ Understand `prototype` and `__proto__`.
- ✅ Implement inheritance using prototypes.
- ✅ Understand constructor functions and classes.
- ✅ Add methods to a prototype.
- ✅ Differentiate between own and inherited properties.

---

## 🌟 1. What Is a Prototype?

A **prototype** is an object that another object can use to access inherited properties and methods.

Think of a college library. If a student does not have a particular resource personally, they may access a shared resource from the library.

Similarly, when JavaScript cannot find a property directly on an object, it looks for that property on the object's prototype.

### 🏫 Real-World Analogy

Imagine the following:

- 👨‍🎓 Student object: has its own name.
- 📚 Shared prototype: provides a common `study()` method.
- 🔍 When the student needs `study()`, JavaScript looks for it on the object and then on its prototype.

### 💻 Example

```javascript
const person = {
    greet() {
        console.log("Hello!");
    }
};

const student = Object.create(person);

student.name = "Rahul";

console.log(student.name);
student.greet();
```

**Output:**

```text
Rahul
Hello!
```

### 🔍 Explanation

- `person` contains the `greet()` method.
- `Object.create(person)` creates an object whose prototype is `person`.
- `student.name` is an own property of `student`.
- `student.greet()` works because JavaScript finds `greet()` on the prototype.

---

## 🧱 2. What Is the Prototype Chain?

The **prototype chain** is the sequence of objects JavaScript searches when looking for a property or method.

If a property is not found on the current object, JavaScript checks its prototype, then that prototype's prototype, and so on.

### 📊 Prototype Chain Diagram

```text
       student object
       ┌───────────────┐
       │ name: "Rahul" │
       └───────┬───────┘
               │
               ▼
       person object
       ┌───────────────┐
       │ greet()       │
       └───────┬───────┘
               │
               ▼
     Object.prototype
       ┌───────────────┐
       │ toString()    │
       │ hasOwnProperty│
       └───────┬───────┘
               │
               ▼
             null
```

This is a simplified illustration. The exact chain depends on how the objects are created.

### 💻 Example: Property Lookup

```javascript
const animal = {
    eats: true
};

const dog = Object.create(animal);

dog.barks = true;

console.log(dog.barks);
console.log(dog.eats);
console.log(dog.sleep);
```

**Output:**

```text
true
true
undefined
```

### 🔍 Why?

| Property | Where JavaScript finds it |
|---|---|
| `barks` | Directly on `dog` |
| `eats` | On the prototype, `animal` |
| `sleep` | Not found in the chain |

💡 If JavaScript cannot find a property anywhere in the prototype chain, its value is normally `undefined`.

---

## 🔑 3. Understanding `prototype` and `__proto__`

These two terms look similar, but they have different meanings.

### A. `prototype`

The `prototype` property is found on ordinary constructor functions and is used as the prototype for objects created by calling those functions with `new`.

```javascript
function Student(name) {
    this.name = name;
}

Student.prototype.study = function () {
    console.log(this.name + " is studying.");
};

const s1 = new Student("Rahul");

s1.study();
```

**Output:**

```text
Rahul is studying.
```

Here, `Student.prototype` contains the shared `study()` method.

### B. `__proto__`

`__proto__` is a legacy accessor that exposes an object's internal prototype. Although it is still supported in many JavaScript environments, `Object.getPrototypeOf()` is preferred for reading the prototype.

```javascript
const person = {
    greet() {
        console.log("Hello!");
    }
};

const student = Object.create(person);

console.log(Object.getPrototypeOf(student) === person);
```

**Output:**

```text
true
```

### 📊 Difference Between `prototype` and `__proto__`

| `prototype` | `__proto__` |
|---|---|
| A property commonly found on constructor functions | A legacy accessor for an object's internal prototype |
| Used when creating objects with `new` | Can expose an object's prototype |
| Example: `Student.prototype` | Example: `student.__proto__` |
| Use for defining shared methods | Prefer `Object.getPrototypeOf()` for reading a prototype |

📌 Important: A class also has a `prototype` property that supplies the prototype for its instances.

---

## 🏗️ 4. Constructor Functions and Prototypes

Before JavaScript introduced the modern `class` syntax, constructor functions were commonly used to create similar objects.

A **constructor function** initializes an object when called with `new`.

### 💻 Example

```javascript
function Car(brand, color) {
    this.brand = brand;
    this.color = color;
}

Car.prototype.start = function () {
    console.log(this.brand + " car started.");
};

const car1 = new Car("Tata", "Black");
const car2 = new Car("Honda", "White");

car1.start();
car2.start();
```

**Output:**

```text
Tata car started.
Honda car started.
```

### 🔍 Step-by-Step Explanation

1. `Car()` defines a constructor function.
2. `new Car("Tata", "Black")` creates a new object.
3. The constructor assigns `brand` and `color` to that object.
4. `Car.prototype.start` defines one shared method.
5. Both car objects can access `start()` through their prototype.

### 📊 Object Structure

```text
Car.prototype
     │
     └── start()
           ▲
           │
     ┌─────┴─────┐
     │           │
   car1         car2
   brand        brand
   color        color
```

💡 The objects share access to the same `start()` function rather than each storing a separate copy of it.

---

## 🧬 5. Prototype-Based Inheritance

**Prototype-based inheritance** allows one object to inherit properties and methods from another object.

### 💻 Example: Animal and Dog

```javascript
const animal = {
    eat() {
        console.log("Animal is eating.");
    }
};

const dog = Object.create(animal);

dog.bark = function () {
    console.log("Dog is barking.");
};

dog.eat();
dog.bark();
```

**Output:**

```text
Animal is eating.
Dog is barking.
```

### 🔍 Explanation

- `animal` provides the `eat()` method.
- `dog` inherits from `animal`.
- `dog` defines its own `bark()` method.
- Both methods are accessible through the `dog` object.

### 🧠 Remember

Prototype inheritance does not copy every parent property into the child object. Instead, JavaScript looks up missing properties through the prototype chain.

---

## 🔄 6. Prototype Inheritance Using Constructor Functions

A constructor function's `prototype` can be used to establish inheritance between constructor-created objects.

```javascript
function Animal(name) {
    this.name = name;
}

Animal.prototype.eat = function () {
    console.log(this.name + " is eating.");
};

function Dog(name) {
    Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function () {
    console.log(this.name + " is barking.");
};

const dog = new Dog("Bruno");

dog.eat();
dog.bark();
```

**Output:**

```text
Bruno is eating.
Bruno is barking.
```

### 🔍 Explanation

- `Animal.call(this, name)` initializes the `name` property on the current dog object.
- `Object.create(Animal.prototype)` makes `Dog.prototype` inherit from `Animal.prototype`.
- `Dog.prototype.constructor = Dog` restores the conventional constructor reference after replacing the prototype.
- `Dog` instances can use methods from both prototypes.

📌 This is a traditional constructor-function inheritance pattern. Modern JavaScript commonly uses `class`, `extends`, and `super()` for the same general purpose.

---

## 🧪 7. How to Check an Object's Prototype

JavaScript provides built-in methods for examining prototype relationships.

### A. `Object.getPrototypeOf()`

Returns the prototype of an object.

```javascript
const parent = {
    greet() {
        console.log("Hello!");
    }
};

const child = Object.create(parent);

console.log(Object.getPrototypeOf(child) === parent);
```

**Output:**

```text
true
```

### B. `Object.setPrototypeOf()`

Changes the prototype of an existing object. This is useful to understand, but changing prototypes after object creation can negatively affect performance. Prefer setting up inheritance when creating objects.

```javascript
const parent = {
    message: "Hello from parent"
};

const child = {};

Object.setPrototypeOf(child, parent);

console.log(child.message);
```

**Output:**

```text
Hello from parent
```

### C. `instanceof`

Checks whether a constructor's `prototype` appears in an object's prototype chain.

```javascript
function Student(name) {
    this.name = name;
}

const s1 = new Student("Rahul");

console.log(s1 instanceof Student);
console.log(s1 instanceof Object);
```

**Output:**

```text
true
true
```

📌 `instanceof` is useful, but it is not a universal test for every kind of inheritance relationship, especially across different JavaScript realms.

---

## 🔎 8. Own Properties vs Inherited Properties

An **own property** belongs directly to an object. An **inherited property** is found on one of its prototypes.

```javascript
const animal = {
    eats: true
};

const dog = Object.create(animal);

dog.barks = true;

console.log(Object.hasOwn(dog, "barks"));
console.log(Object.hasOwn(dog, "eats"));
console.log("eats" in dog);
```

**Output:**

```text
true
false
true
```

### 📊 Comparison

| Own Property | Inherited Property |
|---|---|
| Stored directly on the object | Found on a prototype |
| `Object.hasOwn(obj, key)` returns `true` | `Object.hasOwn(obj, key)` returns `false` |
| Example: `dog.barks` | Example: `dog.eats` |

💡 The `in` operator checks both own and inherited properties.

---

## ⚡ 9. Why Use Prototypes?

Prototypes allow objects to share methods and support inheritance.

### ❌ Defining a Method on Every Object

```javascript
function Student(name) {
    this.name = name;

    this.introduce = function () {
        console.log("I am " + this.name);
    };
}
```

Each call to the constructor creates a new `introduce` function for that object.

### ✅ Defining a Shared Prototype Method

```javascript
function Student(name) {
    this.name = name;
}

Student.prototype.introduce = function () {
    console.log("I am " + this.name);
};

const s1 = new Student("Rahul");
const s2 = new Student("Priya");

console.log(s1.introduce === s2.introduce);
```

**Output:**

```text
true
```

Both objects access the same function.

### 🏆 Benefits

- ♻️ **Code reuse:** Share common methods between objects.
- 💾 **Memory efficiency:** Avoid creating a separate copy of a shared method for each instance.
- 🧬 **Inheritance:** Build relationships between objects.
- 🛠️ **Maintainability:** Shared behaviour can be updated in one place.

---

## 🔗 10. How Do JavaScript Classes Use Prototypes?

JavaScript `class` syntax is built on the prototype-based object model.

```javascript
class Student {
    constructor(name) {
        this.name = name;
    }

    introduce() {
        console.log("I am " + this.name);
    }
}

const s1 = new Student("Rahul");
const s2 = new Student("Priya");

console.log(s1.introduce === s2.introduce);

s1.introduce();
s2.introduce();
```

**Output:**

```text
true
I am Rahul
I am Priya
```

### 🔍 Explanation

- `name` is initialized on each object.
- `introduce()` is defined on `Student.prototype`.
- Both instances share access to the same method.

📌 Classes provide a cleaner syntax for creating objects and setting up prototype-based inheritance.

---

## 📊 11. Quick Revision

| Concept | Meaning |
|---|---|
| Prototype | An object used for property and method inheritance |
| Prototype chain | The sequence of objects searched during property lookup |
| `Constructor.prototype` | Prototype used by instances created with that constructor |
| `Object.getPrototypeOf()` | Reads an object's prototype |
| `Object.create()` | Creates an object with a specified prototype |
| `Object.setPrototypeOf()` | Changes an object's prototype |
| `instanceof` | Checks a constructor's prototype against an object's prototype chain |
| `Object.hasOwn()` | Checks whether a property belongs directly to an object |

---

## 🧪 12. Practice Tasks

Try these programs yourself. 🚀

- [ ] **Task 1:** Create a `person` object with a `greet()` method.
- [ ] **Task 2:** Create a `student` object using `Object.create(person)`.
- [ ] **Task 3:** Add an own property to `student` and compare it with an inherited property.
- [ ] **Task 4:** Create a `Car` constructor function with `brand` and `color`.
- [ ] **Task 5:** Add a shared `start()` method to `Car.prototype`.
- [ ] **Task 6:** Create `Animal` and `Dog` constructor functions and establish inheritance.
- [ ] **Task 7:** Check the prototype of an object using `Object.getPrototypeOf()`.
- [ ] **Task 8:** Compare `Object.hasOwn()` with the `in` operator.
- [ ] **Task 9:** Create two instances of a class and check whether they share the same prototype method.
- [ ] **Task 10:** Draw the prototype chain for an object created using `{}`.

---

# 🎤 13. Viva Voce Questions and Answers

## 🟢 Basic Questions

**Q1. What is a prototype in JavaScript?**

A prototype is an object through which another object can access inherited properties and methods.

**Q2. What is the prototype chain?**

It is the sequence of prototype objects JavaScript searches when a property is not found directly on an object.

**Q3. What is `Object.create()` used for?**

It creates a new object with a specified prototype.

**Q4. What is the `prototype` property of a constructor function?**

It is an object that becomes the prototype of instances created using that constructor with `new`.

**Q5. What is `__proto__`?**

It is a legacy accessor for an object's internal prototype. `Object.getPrototypeOf()` is generally preferred.

## 🟡 Intermediate Questions

**Q6. What is the difference between `prototype` and `__proto__`?**

`prototype` is a property used by constructors to supply an instance prototype. `__proto__` is a legacy accessor that exposes an object's internal prototype.

**Q7. What happens when JavaScript cannot find a property on an object?**

JavaScript searches the object's prototype chain. If the property is not found, the result is normally `undefined`.

**Q8. Why are prototypes useful?**

They enable shared methods, code reuse, and inheritance between objects.

**Q9. What is prototype-based inheritance?**

It is a mechanism where objects inherit access to properties and methods through their prototype relationships.

**Q10. What is the purpose of `Object.getPrototypeOf()`?**

It returns the prototype of a specified object.

**Q11. What is the purpose of `Object.setPrototypeOf()`?**

It changes the prototype of an existing object, although doing so after creation is generally discouraged for performance reasons.

**Q12. What does `instanceof` check?**

It checks whether a constructor's `prototype` appears in an object's prototype chain.

**Q13. What is the difference between an own property and an inherited property?**

An own property belongs directly to the object, while an inherited property is found on one of its prototypes.

**Q14. How do JavaScript classes relate to prototypes?**

Class methods are generally stored on the class's `prototype` object and shared by its instances.

**Q15. Why is a prototype method often preferable to defining the same function inside a constructor?**

A prototype method can be shared by all instances instead of creating a separate function for every instance.

## 🔵 Practical Questions

**Q16. What does `Object.create(null)` do?**

It creates an object with no prototype. Such an object does not inherit methods from `Object.prototype`.

**Q17. What does `Object.hasOwn()` check?**

It checks whether a property exists directly on an object, without considering inherited properties.

**Q18. Does JavaScript support multiple inheritance through the `extends` keyword?**

No. A class can directly extend only one class, though composition and other techniques can combine behaviours.

**Q19. Is `__proto__` recommended for everyday use?**

No. Prefer `Object.getPrototypeOf()` to read a prototype and `Object.create()` to create an object with a chosen prototype.

**Q20. Are prototype methods shared among instances?**

Yes. Instances created using the same constructor or class can access the same method through their shared prototype.

**Q21. What is the default prototype of an object created with `{}`?**

It is normally `Object.prototype`.

**Q22. What is the end of the ordinary object prototype chain?**

The chain ends at `null`.

**Q23. Are JavaScript arrays also objects?**

Yes. Arrays are specialized objects whose prototype chain includes `Array.prototype`.

**Q24. What happens if an object defines a property with the same name as an inherited property?**

The object's own property normally takes precedence during property lookup. This is called property shadowing.

**Q25. What is property shadowing?**

Property shadowing occurs when an object's own property hides an inherited property with the same name.

---

## 🏆 14. Key Takeaways

- ✅ JavaScript uses prototypes to provide inheritance between objects.
- ✅ Property lookup follows the prototype chain.
- ✅ `Constructor.prototype` supplies the prototype for instances created with `new`.
- ✅ `Object.create()` lets you choose an object's prototype.
- ✅ `Object.getPrototypeOf()` is the preferred way to read an object's prototype.
- ✅ Shared prototype methods reduce unnecessary function duplication.
- ✅ JavaScript classes use the prototype mechanism behind the scenes.

> 💡 **Remember:** In JavaScript, objects do not need to copy methods from another object to use them. They can access inherited methods through the prototype chain.

🎉 **Happy Coding! Keep Exploring JavaScript!** 🚀
