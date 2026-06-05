
# AMA QUESTIONS

### 1. Can we use the `length` property for objects?
No. The `length` property is available for arrays and strings, not plain objects.

```js
const arr = [1, 2, 3];
console.log(arr.length); // 3

const obj = { a: 1, b: 2 };
console.log(Object.keys(obj).length); // 2
```

---

### 2. Difference between `map()` and `forEach()`

| map() | forEach() |
|--------|-----------|
| Returns a new array | Returns `undefined` |
| Used for transforming data | Used for performing actions |
| Does not modify original array | Usually used for side effects |

```js
const nums = [1, 2, 3];

const doubled = nums.map(n => n * 2);
console.log(doubled); // [2, 4, 6]

nums.forEach(n => console.log(n));
```

---

### 3. What is Hoisting?

Hoisting is JavaScript's behavior of moving declarations to the top of their scope before execution.

```js
console.log(a); // undefined
var a = 10;
```

Function declarations are fully hoisted:

```js
greet();

function greet() {
  console.log("Hello");
}
```

---

### 4. Difference between Function and Arrow Function

| Function | Arrow Function |
|-----------|----------------|
| Has its own `this` | Inherits `this` from parent scope |
| Can be used as constructor | Cannot be used as constructor |
| Has `arguments` object | No `arguments` object |

```js
function add(a, b) {
  return a + b;
}

const addArrow = (a, b) => a + b;
```

---

### 5. Difference between Array and Object

| Array | Object |
|---------|---------|
| Stores ordered data | Stores key-value pairs |
| Uses numeric indexes | Uses keys |
| Ordered collection | Unordered collection |

```js
const arr = ["apple", "banana"];

const obj = {
  name: "John",
  age: 25
};
```

---

### 6. Which elements are hoisted in JavaScript?

- `var` declarations (initialized as `undefined`)
- Function declarations (fully hoisted)

Not fully hoisted:
- `let`
- `const`
- Function expressions
- Arrow functions

```js
console.log(a); // undefined
var a = 10;
```

---

### 7. What does `map()` do?

`map()` creates a new array by applying a function to every element of an existing array.

```js
const nums = [1, 2, 3];

const squared = nums.map(n => n * n);

console.log(squared); // [1, 4, 9]
```

---

### 8. Difference between `slice()` and `splice()`

| slice() | splice() |
|----------|-----------|
| Does not modify original array | Modifies original array |
| Returns a portion of array | Adds/removes elements |

```js
const arr = [1, 2, 3, 4];

console.log(arr.slice(1, 3)); // [2, 3]

arr.splice(1, 2);
console.log(arr); // [1, 4]
```

---

### 9. What are different data types in JavaScript?

#### Primitive Data Types
- String
- Number
- Boolean
- Undefined
- Null
- BigInt
- Symbol

#### Non-Primitive Data Types
- Object
- Array
- Function

```js
let name = "Naman";
let age = 22;
let isStudent = true;
```

---

### 10. How to insert an element in an array?

Using `push()`, `unshift()`, or `splice()`.

```js
const arr = [1, 2, 3];

arr.push(4);      // End
arr.unshift(0);   // Beginning
arr.splice(2, 0, 10); // Middle
```

---

### 11. Is it possible to run a JavaScript file without Node.js installed?

Yes.

Options:
- Run inside a browser using a `<script>` tag.
- Browser Developer Console.
- Other JavaScript runtimes like Deno.

```html
<script src="app.js"></script>
```

---

### 12. Difference between `shift()` and `pop()`

| shift() | pop() |
|----------|--------|
| Removes first element | Removes last element |
| Changes array length | Changes array length |

```js
const arr = [1, 2, 3];

arr.shift(); // Removes 1
arr.pop();   // Removes 3
```

---

### 13. Can a `const` object be modified?

Yes. The object's properties can be modified, but the object cannot be reassigned.

```js
const user = {
  name: "John"
};

user.name = "Naman"; // Allowed

// user = {}; ❌ Error
```

---

### 14. Difference between `filter()` and `find()`

| filter() | find() |
|------------|---------|
| Returns all matching elements | Returns first matching element |
| Returns an array | Returns a single value or undefined |

```js
const nums = [1, 2, 3, 4, 5];

console.log(nums.filter(n => n > 2));
// [3, 4, 5]

console.log(nums.find(n => n > 2));
// 3
```

---

### 15. Is JavaScript single-threaded or multi-threaded?

JavaScript is a **single-threaded** language.

It executes one task at a time using the **Call Stack**.

However, asynchronous operations (`setTimeout`, Promises, Fetch API) are handled by the browser/Web APIs and Event Loop, making JavaScript appear concurrent.

```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

console.log("End");
```

Output:

```text
Start
End
Timeout
```
