# Questions about JavaScript

## 🔹 What is JavaScript, and how does it differ from other programming languages like Java?

**JavaScript** is a high-level, interpreted programming language primarily used for building interactive and dynamic web applications. It is one of the core technologies of the World Wide Web, alongside **HTML** and **CSS**, and is supported by all major browsers.

JavaScript enables developers to:

- Create dynamic web pages
- Handle events and user interactions
- Communicate with servers (e.g., using `fetch` or `XMLHttpRequest`)
- Build web applications (frontend and backend via Node.js)
- Control multimedia and animations

It is **event-driven**, **asynchronous**, and **prototype-based**, making it very effective for building responsive user interfaces and single-page applications.

#### Key Features of JavaScript

- **Client-side execution**: Runs in the user's browser.
- **Interpreted**: No need for compilation.
- **Dynamically typed**: Variables do not require a fixed type.
- **Lightweight**: Minimal syntax and structure.
- **Asynchronous programming**: Uses Promises and async/await.
- **Object-oriented**: Uses prototype-based inheritance.

#### How Does JavaScript Differ From Java?

Although their names sound similar, JavaScript and Java are completely different languages with different purposes, syntax, and execution environments.

| Feature               | JavaScript                                              | Java                                                   |
|-----------------------|----------------------------------------------------------|---------------------------------------------------------|
| **Purpose**           | Web development (client & server)                        | General-purpose application development                 |
| **Execution**         | Interpreted in the browser or Node.js                    | Compiled to bytecode and run on the JVM                 |
| **Typing**            | Dynamically typed                                        | Statically typed                                        |
| **Syntax**            | Flexible, minimal structure                              | Strict, verbose, strongly object-oriented               |
| **Object Orientation**| Prototype-based                                          | Class-based                                             |
| **Concurrency**       | Asynchronous (event loop, Promises, async/await)         | Multi-threaded (synchronization, concurrency models)    |
| **Platform Dependency**| Browser or Node.js                                     | JVM-based, cross-platform                               |

> **Note**: The similarity in names was a marketing strategy during the early days of JavaScript. JavaScript was originally called *LiveScript*, but was renamed to JavaScript to capitalize on the popularity of Java at the time.


#### When to Use JavaScript

JavaScript is ideal for:

- Interactive websites
- Frontend frameworks (React, Vue, Angular)
- Backend development (Node.js)
- Progressive Web Apps (PWAs)
- Real-time applications (chats, games)

---
---
---



## 🔹What are the different data types in JavaScript?

JavaScript has two main categories of data types: **Primitive** and **Non-Primitive (Reference)**.

#### 1. Primitive Data Types

These are the most basic data types and are stored by **value**.

| Type         | Description |
|--------------|-------------|
| `String`     | Represents text. Example: `"Hello"` |
| `Number`     | Represents both integers and floats. Example: `42`, `3.14` |
| `Boolean`    | Logical `true` or `false` |
| `Null`       | Represents an intentional empty value |
| `Undefined`  | Declared but not assigned a value |
| `BigInt`     | Large integers beyond Number limit |
| `Symbol`     | Unique identifiers |

#### 🔸 Example Code:

```javascript
let name = "Alice";             // String
let age = 30;                   // Number
let isActive = true;            // Boolean
let salary = null;              // Null
let score;                      // Undefined
let bigNum = 123456789012345678901234567890n; // BigInt
let uniqueId = Symbol("id");    // Symbol
```

#### 2. Non-Primitive (Reference) Data Types

These are more complex and stored by reference.

| Type         | Description |
|--------------|-------------|
| `Object`     | A collection of key-value pairs |
| `Array`     | Ordered list of values |
| `Function`    | Reusable block of code |

#### 🔸 Example Code:   
```javascript
let person = { name: "Bob", age: 25 }; // Object
let fruits = ["apple", "banana", "cherry"]; // Array
let add = function(a, b) { return a + b; }; // Function
```


#### 🔍 Type Checking
Use `typeof` to check the data type of any value:

#### Example Code:

```
console.log(typeof "hello");      // "string"
console.log(typeof 42);           // "number"
console.log(typeof true);         // "boolean"
console.log(typeof undefined);    // "undefined"
console.log(typeof null);         // "object" (known JavaScript quirk)
console.log(typeof Symbol());     // "symbol"
console.log(typeof [1, 2, 3]);    // "object"
console.log(typeof function(){}); // "function"

```

#### ✅ Summary

| Category         | Data Types |
|--------------|-------------|
| Primitive     | 	`String`, `Number`, `Boolean`, `Null`, `Undefined`, `BigInt`, `Symbol` |
| Reference     | `Object`, `Array`, `Function` |


📘 Conclusion

- JavaScript is essential for dynamic web development.

- It differs significantly from Java despite the similar name.

- Mastering JavaScript data types is crucial for writing robust code.

- Always be aware of how data is stored and manipulated—by value vs by reference.

---
---
---

## 🔹What is the difference between var, let, and const in JavaScript?

In JavaScript, variables can be declared using `var`, `let`, and `const`. Each has different behavior in terms of **scope**, **hoisting**, **reassignment**, and **redeclaration**. This document explains each with examples.

#### 🔹 1. `var`

#### ✅ Features:
- **Function-scoped**
- **Can be redeclared** and **reassigned**
- **Hoisted** and initialized as `undefined`

#### 🔸 Example:

```javascript
// Function scope
function testVar() {
  if (true) {
    var x = 10;
  }
  console.log(x); // ✅ 10 — function-scoped
}

testVar();

// Redeclaration allowed
var a = 1;
var a = 2; // ✅ No error
console.log(a); // 2

// Hoisting
console.log(b); // ✅ undefined (hoisted)
var b = 5;
console.log(b); // 5
```

#### 🔹 2. `let`

#### ✅ Features:
- **Block-scoped**
- **Can be reassigned, but cannot be redeclared in the same scope**
- **Hoisted, but not initialized**

#### 🔸 Example:

```javascript
// Block scope
function testLet() {
  if (true) {
    let y = 20;
    console.log(y); // ✅ 20
  }
  // console.log(y); ❌ ReferenceError
}

testLet();

// Redeclaration not allowed
let c = 3;
// let c = 4; ❌ SyntaxError: Identifier 'c' has already been declared

// Hoisting
// console.log(d); ❌ ReferenceError
let d = 10;
console.log(d); // 10
```

#### 🔹 3. `const`

#### ✅ Features:
- **Block-scoped**
- **Cannot be redeclared or reassigned**
- **Must be initialized at declaration**
- **Values can be mutated if the variable is an object or array**

#### 🔸 Example:

```javascript
// Block scope
function testConst() {
  if (true) {
    const z = 30;
    console.log(z); // ✅ 30
  }
  // console.log(z); ❌ ReferenceError
}

testConst();

// Reassignment not allowed
const e = 100;
// e = 200; ❌ TypeError: Assignment to constant variable

// Mutating object
const person = { name: "Alice" };
person.name = "Bob"; // ✅ Allowed (mutating property)
console.log(person.name); // "Bob"

// Reassigning object reference
// person = { name: "Charlie" }; ❌ TypeError
```



#### 🔁 Comparison Table

| Feature                   | `var`                    | `let`                        | `const`                      |
|---------------------------|---------------------------|-------------------------------|-------------------------------|
| **Scope**                | Function-scoped           | Block-scoped                 | Block-scoped                 |
| **Hoisting**             | ✅ Yes (initialized as `undefined`) | ✅ Yes (in TDZ\*)     | ✅ Yes (in TDZ\*)           |
| **Redeclarable**         | ✅ Yes                   | ❌ No                        | ❌ No                        |
| **Reassignable**         | ✅ Yes                   | ✅ Yes                       | ❌ No                        |
| **Initialization Required** | ❌ No                | ❌ No                        | ✅ Yes                       |
| **Mutability (objects)**| ✅ Yes                   | ✅ Yes                       | ✅ Yes (props can change)    |


#### ✅ Best Practices

- ✅ Use const by default.
- ✅ Use let if you need to reassign.
- ❌ Avoid var in modern JavaScript (legacy usage only).


#### 📘 Summary

- `var` is function-scoped, hoisted with undefined, and should generally be avoided.
- `let` is block-scoped, hoisted but uninitialized, and allows reassignment.
- `const` is block-scoped, hoisted and initialized, and cannot be reassigned or mutated.

---
---
---

## 🔹What are the differences between null and undefined? 


In JavaScript, both `null` and `undefined` represent absence of value, but they are used differently and behave differently.

#### 🔹 `undefined`

#### ✅ Definition:
`undefined` means a variable has been **declared but not assigned** a value.

#### 🔸 Characteristics:
- Assigned by **JavaScript by default**
- Returned when:
  - A variable is declared but not assigned
  - A function does not return a value
  - Accessing a non-existent object property
- Type is: `"undefined"`

#### 🔸 Code Example:

```javascript
let x;
console.log(x); // ✅ undefined (not assigned)

function test() {}
console.log(test()); // ✅ undefined (no return)

let user = {};
console.log(user.name); // ✅ undefined (property doesn't exist)
```

#### 🔹 `null`

#### ✅ Definition:
`null` is an explicit value assigned by the programmer to indicate "no value".

#### 🔸 Characteristics:
- Must be manually assigned
- Commonly used to reset or clear a variable
- Type is: `"object"` (this is a known bug in JavaScript)

#### 🔸 Code Example:

```javascript
let y = null;
console.log(y); // ✅ null

let person = {
  name: null // means intentionally empty
};
console.log(person.name); // null
```

#### 🔁 Comparison Table

| Feature             | `undefined`                              | `null`                               |
|---------------------|-------------------------------------------|---------------------------------------|
| **Meaning**         | Declared but not assigned a value         | Intentional absence of any object value |
| **Set by**          | JavaScript automatically                  | Programmer explicitly                 |
| **Type**            | `"undefined"`                             | `"object"` (legacy quirk)             |
| **Usage**           | Default for uninitialized variables       | Used to reset or clear variables      |
| **Equality (`==`)** | `null == undefined` → ✅ `true`           | Same loose equality                  |
| **Strict Equality (`===`)** | `undefined === null` → ❌ `false` | Different types                       |

#### ✅ When to Use

| Use Case                  | Recommended Value |
|---------------------------|-------------------|
| Variable not yet assigned | `undefined`        |
| Clear/reset a variable    | `null`             |
| Missing object property   | `undefined`        |
| Empty value on purpose    | `null`             |

---
---
---

## 🔹Explain all JavaScript operators and their purpose of use?

JavaScript operators are symbols used to perform operations on operands (values and variables). Here's a full list categorized by type:

#### 🔹 1. Arithmetic Operators

| Operator | Description         | Example        | Result |
|----------|---------------------|----------------|--------|
| `+`      | Addition             | `5 + 2`        | `7`    |
| `-`      | Subtraction          | `5 - 2`        | `3`    |
| `*`      | Multiplication       | `5 * 2`        | `10`   |
| `/`      | Division             | `10 / 2`       | `5`    |
| `%`      | Modulus (remainder) | `5 % 2`        | `1`    |
| `**`     | Exponentiation       | `2 ** 3`       | `8`    |
| `++`     | Increment            | `x++`          | `x + 1`|
| `--`     | Decrement            | `x--`          | `x - 1`|

#### 🔹 2. Assignment Operators

| Operator | Description             | Example       | Equivalent To   |
|----------|-------------------------|---------------|-----------------|
| `=`      | Assign                   | `x = 5`       | `x = 5`         |
| `+=`     | Add and assign           | `x += 2`      | `x = x + 2`     |
| `-=`     | Subtract and assign      | `x -= 2`      | `x = x - 2`     |
| `*=`     | Multiply and assign      | `x *= 2`      | `x = x * 2`     |
| `/=`     | Divide and assign        | `x /= 2`      | `x = x / 2`     |
| `%=`     | Modulus and assign       | `x %= 2`      | `x = x % 2`     |
| `**=`    | Exponent and assign      | `x **= 2`     | `x = x ** 2`    |

#### 🔹 3. Comparison Operators

| Operator | Description                    | Example         | Result         |
|----------|--------------------------------|------------------|----------------|
| `==`     | Equal (loose)                  | `5 == '5'`       | `true`         |
| `===`    | Strict equal (type + value)    | `5 === '5'`      | `false`        |
| `!=`     | Not equal (loose)              | `5 != '5'`       | `false`        |
| `!==`    | Strict not equal               | `5 !== '5'`      | `true`         |
| `>`      | Greater than                   | `5 > 3`          | `true`         |
| `<`      | Less than                      | `3 < 5`          | `true`         |
| `>=`     | Greater than or equal to       | `5 >= 5`         | `true`         |
| `<=`     | Less than or equal to          | `4 <= 3`         | `false`        |

#### 🔹 4. Logical Operators

| Operator | Description             | Example              | Result   |
|----------|-------------------------|-----------------------|----------|
| `&&`     | Logical AND              | `true && false`       | `false`  |
| `||`     | Logical OR               | `true || false`       | `true`   |
| `!`      | Logical NOT              | `!true`               | `false`  |

#### 🔹 5. Bitwise Operators

| Operator | Description     | Example   | Result |
|----------|-----------------|-----------|--------|
| `&`      | AND              | `5 & 1`   | `1`    |
| `|`      | OR               | `5 | 1`   | `5`    |
| `^`      | XOR              | `5 ^ 1`   | `4`    |
| `~`      | NOT              | `~5`      | `-6`   |
| `<<`     | Left shift       | `5 << 1`  | `10`   |
| `>>`     | Right shift      | `5 >> 1`  | `2`    |
| `>>>`    | Zero-fill right shift | `-5 >>> 1` | Big unsigned int |

#### 🔹 6. String Operators

| Operator | Description      | Example             | Result         |
|----------|------------------|----------------------|----------------|
| `+`      | Concatenation     | `'Hello' + ' World'` | `'Hello World'` |
| `+=`     | Append to string  | `str += '!'`         | `'Hello!'`     |

#### 🔹 7. Type Operators

| Operator     | Description                | Example                 | Result       |
|--------------|----------------------------|--------------------------|--------------|
| `typeof`     | Returns data type          | `typeof 123`             | `"number"`   |
| `instanceof` | Checks if object is instance of class | `arr instanceof Array` | `true`       |

#### 🔹 8. Ternary Operator

Shorthand for `if...else`.

```javascript
let age = 18;
let status = age >= 18 ? "Adult" : "Minor";
console.log(status); // "Adult"
```

#### 🔹 9. Comma Operator

Allows multiple expressions where only one is expected (returns the last).

```javascript
let result = (1 + 2, 3 + 4);
console.log(result); // 7
```

#### 🔹 10. Optional Chaining (?.) and Nullish Coalescing (??)

✅ Optional Chaining:

```javascript
let user = {};
console.log(user?.profile?.name); // undefined (no error)
```

✅ Nullish Coalescing:

```javascript
let username = null;
let display = username ?? 'Guest';
console.log(display); // Guest
```

---
---
---

## 🔹 What is the difference between `==` and `===` in JavaScript?

🔁 `==` (Equality Operator)

- Performs type coercion: If the operands are of different types, it tries to convert them to the same type before comparing.
- Known as loose equality.

#### 🔸 Code Example:

```javascript
5 == '5'     // true (string '5' is converted to number 5)
0 == false   // true (false is coerced to 0)
null == undefined  // true (they are considered loosely equal)
```



🔒 `===` (Strict Equality Operator)

- No type conversion: It compares both value and type.
- Known as strict equality.

#### 🔸 Code Example:

```javascript
5 === '5'     // false (number !== string)
0 === false   // false (different types)
null === undefined  // false (different types)
5 === 5       // true
```

#### ✅ Summary Table : `==` vs `===`

| Expression               | `==` Result | `===` Result | Explanation                                |
|--------------------------|-------------|--------------|--------------------------------------------|
| `5 == '5'`               | `true`      | `false`      | Loose equality coerces `'5'` to number `5` |
| `0 == false`             | `true`      | `false`      | `false` becomes `0` in loose comparison    |
| `null == undefined`      | `true`      | `false`      | Loosely equal but not strictly             |
| `1 == true`              | `true`      | `false`      | `true` becomes `1` with `==`               |
| `[] == false`            | `true`      | `false`      | Array coerces to empty string, then 0      |
| `10 == 10`               | `true`      | `true`       | Same value and type                        |
| `'hello' == 'hello'`     | `true`      | `true`       | Same string                                |
| `NaN == NaN`             | `false`     | `false`      | NaN is never equal to itself               |



#### 🔸 Code Example:

```javascript
console.log('== vs === in JavaScript');

// Example 1: Number vs String
let a = 5;
let b = '5';

console.log(a == b);   // true (type coercion)
console.log(a === b);  // false (strict type check)

// Example 2: Boolean vs Number
console.log(0 == false);   // true
console.log(0 === false);  // false

console.log(1 == true);    // true
console.log(1 === true);   // false

// Example 3: null vs undefined
console.log(null == undefined);   // true
console.log(null === undefined);  // false

// Example 4: Object and primitive
console.log([] == false);         // true (array coerced to '')
console.log([] === false);        // false

// Example 5: Identical values and types
console.log(10 == 10);    // true
console.log(10 === 10);   // true
```

✅ Output Explanation (in console)

```bash
true   // 5 == '5' → '5' is coerced to number
false  // 5 === '5' → different types
true   // 0 == false → coerced
false  // 0 === false → number !== boolean
true   // null == undefined
false  // null !== undefined
true   // [] == false → coerced to ''
false  // [] === false
true   // 10 == 10
true   // 10 === 10
```

---
---
---

## 🔹 What are template literals, and how do you use them in JavaScript?

# 📘 JavaScript Template Literals

Template literals are a powerful feature in JavaScript (introduced in ES6) that make string manipulation easier and more readable.


Template literals (also called template strings) are string literals that allow embedded expressions. You define them using **backticks (`)** instead of single `'` or double `"` quotes.

#### ✅ Features

- Multi-line strings
- Variable and expression interpolation
- Expression evaluation
- Tagged templates (advanced)

#### 1. Syntax Example

```javascript
const name = "Alice";
const message = `Hello, ${name}!`;
console.log(message);  // Output: Hello, Alice!
```

#### 2. Multi-line Strings

You don't need `\n` or concatenation :

```javascript
const multiLine = `This is
a multi-line
string.`;
console.log(multiLine);
```

#### 3. Expression Interpolation

You can directly evaluate expressions inside `${}` :

```javascript
const a = 5;
const b = 10;
console.log(`The sum is ${a + b}`); // Output: The sum is 15
```

#### 4. Tagged Template Literals (Advanced)

You can define a function to process a template string :

```javascript
function highlight(strings, ...values) {
  return strings.reduce((result, str, i) =>
    `${result}${str}<b>${values[i] || ''}</b>`, '');
}

const name = "Bob";
const age = 30;
const result = highlight`Name: ${name}, Age: ${age}`;
console.log(result);
// Output: Name: <b>Bob</b>, Age: <b>30</b>
```

#### 🆚 Traditional vs Template Literals

| Feature              | Traditional String            | Template Literal                |
|----------------------|-------------------------------|----------------------------------|
| Variable Insertion   | `"Hello " + name`             | ``Hello ${name}``                |
| Multi-line Strings   | `"Line1\nLine2"`              | ``Line1<br>Line2``               |
| Expression Evaluation| `"Total: " + (a + b)`         | ``Total: ${a + b}``              |
| Complex Templates    | Harder to read                | Cleaner and more readable        |


---
---
---

## 🔹 What is an array in JavaScript?Explain all the methods of arrays in JavaScript.

In JavaScript, an array is a data structure used to store multiple values in a single variable. Arrays are ordered, zero-indexed, and can contain mixed data types (numbers, strings, objects, functions, etc.).

```javascript
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // Output: apple
```

#### 1. Creation & Access

| Method/Usage   | Description                     |
|----------------|---------------------------------|
| `[]`           | Literal syntax to create array  |
| `Array()`      | Constructor to create array     |
| `array[index]` | Access element by zero-based index |

```javascript
const nums = [1, 2, 3];
console.log(nums[1]);        // 2

const moreNums = Array(4, 5, 6);
console.log(moreNums[0]);    // 4
```

#### 2. Adding/Removing Elements

| Method              | Description            | Example                |
|----------------------|-------------------------------|----------------------------------|
| `push()`   | Adds to the end             | `arr.push(4)`                |
| `pop()`   | Removes from the end             | `arr.pop()`               |
| `unshift()`| Removes from the beginning         |`arr.unshift(0)`              |
| `shift()`    | Removes from the beginning                | `arr.shift() `      |
| `splice()`    | Adds/removes from any position                | `arr.splice(1, 0, "x")`        |
| `slice()`    | Returns a portion (shallow copy)                | `arr.slice(1, 3)`        |


```javascript
let arr = [1, 2, 3];
arr.push(4);          // [1, 2, 3, 4]
arr.shift();          // [2, 3, 4]
arr.splice(1, 1, 'x'); // [2, 'x', 4]
console.log(arr.slice(0, 2)); // [2, 'x']
```

#### 3. Iteration Methods

| Method   | Description                     |
|----------------|---------------------------------|
| `forEach()` | Execute callback for each item |
| `map() `           | Return new array of transformed values  |
| `filter()`      | Return items that meet a condition     |
| `reduce()` | Accumulate to single return value |
| `some()` | true if at least one item matches |
| `every()` | true if all items match |

```javascript
const numbers = [1, 2, 3, 4];

numbers.forEach(n => console.log(n));

const doubled = numbers.map(n => n * 2);      // [2, 4, 6, 8]
const evens   = numbers.filter(n => n % 2 === 0); // [2, 4]
const total   = numbers.reduce((a, n) => a + n, 0); // 10
const hasOdd  = numbers.some(n => n % 2);     // true
const allOdd  = numbers.every(n => n % 2);    // false
```

#### 4. Searching and Indexing

| Method   | Description                     |
|----------------|---------------------------------|
| `includes()` | Checks if an item is in the array |
| `indexOf()` | Returns index of first occurrence |
| `lastIndexOf()` | Returns index of last occurrence |
| `find()` | Returns first match |
| `findIndex()` | Returns index of first match |


```javascript
const colors = ['red', 'green', 'blue', 'green'];

console.log(colors.indexOf('green'));      // 1
console.log(colors.lastIndexOf('green'));  // 3
console.log(colors.includes('blue'));      // true

const longColor = colors.find(c => c.length > 4); // 'green'
const longIndex = colors.findIndex(c => c.length > 4); // 1
```

#### 5. Sorting and Reversing

| Method   | Description                     |
|----------------|---------------------------------|
| `sort()` | Sorts array in place |
| `reverse()` | Reverses array in place |
| `splice()` | Remove and/or add elements |

```javascript
const letters = ['c', 'a', 'b'];
letters.sort();     // ['a', 'b', 'c']
letters.reverse();  // ['c', 'b', 'a']

const nums = [10, 2, 5];
nums.sort((a, b) => a - b); // [2, 5, 10]
```

#### 6. Converting Data Types

| Method   | Description                     |
|----------------|---------------------------------|
| `toString()` | Converts to string |
| `valueOf()` | Returns primitive value |
| `Number()` | Converts to number |
| `String()` | Converts to string |
| `Boolean()` | Converts to boolean |
| `join()` | 	Concatenate items into string |
| `flat()` | Flatten nested arrays (depth param) |
| `concat()` | Return new array merging given arrays |
| `isArray()` | Static method to test for array |

```javascript
const num = 42;
console.log(num.toString());  // '42'
console.log(num.valueOf());   // 42
const words = ['hello', 'world'];
console.log(words.join(' '));        // 'hello world'
console.log(words.toString());       // 'hello,world'

const nested = [1, [2, [3]]];
console.log(nested.flat(2));         // [1, 2, 3]

console.log(Array.isArray(nested));  // true

const merged = [1, 2].concat([3, 4]); // [1, 2, 3, 4]
const str = 'hello';
console.log(str.split(''));         // ['h', 'e', 'l', 'l', 'o']
```

#### 7. Date and Time
| Method   | Description                     |
|----------------|---------------------------------|
| `Date()` | Creates a new Date object |
| `getFullYear()` | Returns year |


#### 8. Filling and Copying

| Method   | Description                     |
|----------------|---------------------------------|
| `fill()` | Overwrite all / part of array with static value |
| `copyWithin()` | Copy part of array to another location in same array |

```javascript
const filled = new Array(3).fill(0);    // [0, 0, 0]

const seq = [1, 2, 3, 4];
seq.copyWithin(0, 2);                   // [3, 4, 3, 4]
```

