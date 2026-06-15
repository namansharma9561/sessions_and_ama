# JavaScript Interview Questions & Answers

## 1. Can we use `.includes()` on strings?

**Answer:** Yes. It checks whether a string contains a specified substring.

```javascript
"JavaScript".includes("Script"); // true
```

---

## 2. Difference between `pop()` and `shift()`

| Method | Removes From |
|----------|------------|
| `pop()` | End |
| `shift()` | Beginning |

```javascript
const arr = [1, 2, 3];

arr.pop();   // Removes 3
arr.shift(); // Removes 1
```

---

## 3. How can we merge two objects into a single object?

Using the spread operator:

```javascript
const obj1 = { name: "Naman" };
const obj2 = { age: 22 };

const merged = { ...obj1, ...obj2 };
```

---

## 4. What is `Promise.withResolvers()`?

Creates a Promise along with its `resolve` and `reject` functions.

```javascript
const { promise, resolve, reject } = Promise.withResolvers();
```

---

## 5. What is a Promise in JavaScript?

A Promise represents the eventual completion or failure of an asynchronous operation.

```javascript
const promise = new Promise((resolve, reject) => {
    resolve("Success");
});
```

---

## 6. Difference between `find()` and `findIndex()`

| Method | Returns |
|----------|----------|
| `find()` | Element |
| `findIndex()` | Index |

```javascript
const nums = [10, 20, 30];

nums.find(n => n > 15);      // 20
nums.findIndex(n => n > 15); // 1
```

---

## 7. What are the three Promise states?

1. Pending
2. Fulfilled
3. Rejected

---

## 8. Does `.sort()` return anything?

Yes. It returns the sorted array and modifies the original array.

```javascript
const arr = [3, 1, 2];

arr.sort(); // [1, 2, 3]
```

---

## 9. What is `trim()` used for?

Removes whitespace from both ends of a string.

```javascript
const str = "  Hello  ";

str.trim(); // "Hello"
```

---

## 10. By using which method can we access the index in a string?

Using `indexOf()`.

```javascript
const str = "JavaScript";

str.indexOf("S"); // 4
```

---

## 11. Difference between `indexOf()` and `lastIndexOf()`

| Method | Searches From |
|----------|-------------|
| `indexOf()` | Left to Right |
| `lastIndexOf()` | Right to Left |

```javascript
const str = "hello hello";

str.indexOf("hello");     // 0
str.lastIndexOf("hello"); // 6
```

---

## 12. What is `Object.assign()`?

Copies properties from source objects into a target object.

```javascript
const result = Object.assign(
    {},
    { a: 1 },
    { b: 2 }
);
```

---

## 13. What is Execution Context in JavaScript?

The environment where JavaScript code is executed.

Types:
- Global Execution Context
- Function Execution Context
- Eval Execution Context

---

## 14. How can you add a class to an element using DOM?

Using `classList.add()`.

```javascript
const element = document.getElementById("box");

element.classList.add("active");
```

---

## 15. What is Hoisting in JavaScript?

Hoisting is JavaScript's behavior of moving declarations to the top of their scope before execution.

```javascript
console.log(a);

var a = 10;
```

Output:

```javascript
undefined
```
