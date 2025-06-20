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

#### 📘 JavaScript Template Literals

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

## 🔹 What is an array in JavaScript? Explain all the methods of arrays in JavaScript.

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

---
---
---

## 🔹How do you convert a string to a number in JavaScript?


#### 📌 Methods to Convert String to Number

#### 1. `Number()` Constructor

Converts the entire string to a number. Returns `NaN` if the string contains invalid characters.

```javascript
const str = "42";
const num = Number(str);
console.log(num); // 42
```

#### 2. `parseInt()` Function
Converts the string to an integer. Returns `NaN` if the string contains non-numeric characters.

```javascript
const str = "42px";
const num = parseInt(str, 10);
console.log(num); // 42
```

#### 3. `parseFloat()` Function
Converts the string to a floating-point number. Returns `NaN` if the string contains non-numeric characters.

```javascript
const str = "3.14";
const num = parseFloat(str);
console.log(num); // 3.14
```
#### 4. Unary Plus (`+`) Operator
The unary `+` operator can be used to convert a string to a number. It returns `NaN` if the string contains non-numeric characters.

```javascript
const str = "42";
const num = +str;
console.log(num); // 42
```

#### 5. Implicit Conversion Using Math Functions
Math functions like `Math.floor()` will implicitly convert the input to a number.

```javascript
const str = "42.7";
const num = Math.floor(str);
console.log(num); // 42
```

#### ⚠️ Notes

- `Number("abc")` → `NaN`

- `parseInt("42abc")` → `42`

- `parseFloat("42.5abc")` → `42.5`

- `+"42"` → `42`

- `"42" * 1` → `42` (another implicit conversion trick)

#### ✅ Best Practices

- Use `Number()` or `+` when the string must be strictly numeric.

- Use `parseInt()` or `parseFloat()` when you expect extra characters.

- Always specify the radix (base) in `parseInt()`: `parseInt(str, 10)`


#### 📦 Usage Example

```javascript
function toNumber(value) {
  const num = Number(value);
  return isNaN(num) ? null : num;
}

console.log(toNumber("123"));    // 123
console.log(toNumber("12abc"));  // null
```

---
---
---

## 🔹 How does JavaScript handle automatic type conversion when comparing values?

#### 🧠 JavaScript Type Coercion in Comparisons

JavaScript automatically converts types when using the `==` (loose equality) operator. This behavior is called **type coercion** and can sometimes lead to unexpected results.


#### ⚖️ Loose vs Strict Equality

#### Loose Equality (`==`)
- Performs type conversion if needed.
- Use with caution—can lead to confusing results.

#### Strict Equality (`===`)
- No type conversion.
- Compares both **type** and **value**.


#### 📋 Type Conversion Rules (Simplified)

When comparing values with `==`, JavaScript follows these basic rules:

- If one operand is a number and the other a string → convert the string to a number.

- If one is `boolean` → convert it to `0` or `1`.

- If one is `object` and the other a primitive → convert the object to a primitive (via `.toString()` or `.valueOf()`).

- `null` and `undefined` are only equal to each other (not to any other value).


#### 🔁 Comparison Table with Type Coercion

| Expression           | Result | Explanation                                |
|----------------------|--------|--------------------------------------------|
| `"42" == 42`         | `true` | String `"42"` is converted to number `42`  |
| `false == 0`         | `true` | `false` becomes `0`                         |
| `null == undefined`  | `true` | Special rule in JavaScript                 |
| `"0" == false`       | `true` | Both become number `0`                     |
| `[] == ""`           | `true` | Empty array converts to empty string       |
| `[] == 0`            | `true` | `[]` → `""`, then `""` → `0`               |
| `[1] == 1`           | `true` | `[1]` becomes string `"1"` then number     |
| `{} == "[object Object]"` | `false` | Object is not coerced to a string in this context |
| `null == 0`          | `false`| `null` only equals `undefined`             |
| `undefined == 0`     | `false`| No coercion rule between these             |
| `"" == false`        | `true` | `""` becomes `0`, `false` becomes `0`      |

---

#### ✅ Best Practices

- Always prefer **strict equality (`===`)** to avoid unexpected type coercion.
- Use **type-safe comparisons** in conditionals, function logic, and validations.
- If you must use `==`, understand the coercion rules.

---

## 🧪 Example Code

```javascript
console.log("42" == 42);        // true
console.log(false == 0);        // true
console.log(null == undefined); // true
console.log([] == 0);           // true
console.log([1] == "1");        // true
console.log({} == "[object Object]"); // false
```

---
---
---

## 🔹What is the difference between Array.forEach() and Array.map()?

#### 🔄 JavaScript : `Array.forEach()` vs `Array.map()`

Understanding the difference between `forEach()` and `map()` is essential for writing clean and effective JavaScript code. Both are used to iterate over arrays, but they serve different purposes.


#### 📌 Key Differences

| Feature               | `forEach()`                          | `map()`                                |
|-----------------------|---------------------------------------|-----------------------------------------|
| **Purpose**           | To execute a function on each item               | To create a new array with transformed values |
| **Returns**           | `undefined`                          | 	New array with transformed elements                             |
| **Mutates original?** | No (but can modify manually)         | No                                      |
| **Chainable?**        | ❌ Not chainable                      | ✅ Chainable (returns an array)                             |
| **Use case**          | Logging, updating DOM, side effects  | Data transformation                     |


#### 🧪 Example Usage

#### ✅ `forEach()`: Perform an action for each element

```javascript
const numbers = [1, 2, 3];

numbers.forEach(num => {
  console.log(num * 2); // Logs: 2, 4, 6
});

console.log(numbers); // [1, 2, 3]
```

#### ✅ `map()`: Create a new array with transformed elements
```javascript
const numbers = [1, 2, 3];
const doubledNumbers = numbers.map(num => num * 2);
console.log(doubledNumbers); // [2, 4, 6]
console.log(numbers); // [1, 2, 3]
```

#### ✅ Summary

- Use `forEach()` when you’re doing side effects (e.g., logging, updating DOM, calling APIs).

- Use `map()` when you want to create a new array based on the original.


---
---
---


## 🔹What is an Object in JavaScript? How is it different from an array? Explain all methods of Object in javaScript?

An **object** in JavaScript is a collection of properties, where each property is a **key-value pair**. It can be used to store data in a structured way, and it can have methods, which are functions that are associated with the object.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  },
  sayHello: function() {
    console.log("Hello, my name is " + this.name);
  }
};
console.log(person.name); // "John"
console.log(person.address.city); // "New York"
person.sayHello(); // "Hello, my name is John"
```

- Keys are strings (or Symbols).

- Values can be any type: string, number, boolean, array, object, function, etc.

#### 🔄 How is an Object different from an Array?

| Feature               | Object                          | Array                                |
|-----------------------|---------------------------------------|-----------------------------------------|
| **Structure**           | Key-value pairs               | Indexed collection of values |
| **Access**           | By key (`obj.key`)                          | 	By index (`arr[0]`)                             |
| **Order** | Unordered (in general)         | Ordered (in general)                               |                                      |
| **Use Case**        | Storing related data as named fields                      | Storing lists, sequences                             |
| **Syntax**          | `{ key: value }`  | `[value1, value2]`                     |

#### 📚 Methods of Object in JavaScript

#### 🔍 Object.keys(obj)
Returns an array of the object's own property names.
```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.keys(person)); // ["name", "age", "address"]
```

#### 🔍 Object.values(obj)
Returns an array of the object's own property values.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.values(person)); // ["John", 30, {…}]
```

#### 🔍 Object.entries(obj)
Returns an array of the object's own key-value pairs.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.entries(person)); // [["name", "John"], ["age", 30], ["address", {…}]]
```

#### 🔁 Object.assign(target, ...sources)
Copies all enumerable own properties from one or more source objects to a target object.

```javascript
const target = {};
const source1 = { a: 1, b: 2 };
const source2 = { c: 3, d: 4 };
Object.assign(target, source1, source2);
console.log(target); // {a: 1, b: 2, c: 3, d: 4}
```

#### 🔐 Object.freeze(obj)
Freezes an object, preventing any changes to its properties.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
Object.freeze(person);
person.name = "Jane"; // No error, but the property is not writable
console.log(person.name); // "John"
```

#### 🔒 Object.seal(obj)
Seals an object, preventing any changes to its properties.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
Object.seal(person);
person.name = "Jane"; // No error, but the property is not writable
console.log(person.name); // "John"
```

#### ❌ Object.is(a, b)
Determines if two values are the same primitive value.

```javascript
console.log(Object.is(5, 5)); // true
console.log(Object.is("foo", "foo")); // true
console.log(Object.is({}, {})); // false
```

#### 🔧 Object.defineProperty(obj, key, descriptor)
Defines a new property directly on an object and returns the object.

```javascript
const person = {};
Object.defineProperty(person, "name", {
  value: "John",
  writable: true,
  enumerable: true,
  configurable: true
});
person.name = "Jane"; // No error, but the property is not writable
console.log(person.name); // "John"
```

#### 🔍 Object.hasOwn(obj, key) (ES2022+)
Checks if an object has a specified own property.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.hasOwn(person, "name")); // true
console.log(Object.hasOwn(person, "address")); // true
console.log(Object.hasOwn(person, "gender")); // false
```


#### 🧱 Object.create(proto)
Creates a new object with the specified prototype object and properties.

```javascript
const person = Object.create(null);
person.name = "John";
person.age = 30;
console.log(person); // {name: "John", age: 30}
```







#### 🔍 Object.getOwnPropertyDescriptors(obj)
Returns an object containing all own property descriptors of a given object.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.getOwnPropertyDescriptors(person)); // {name: {…}, age: {…}, address: {…}}
```

#### 🔍 Object.getOwnPropertyNames(obj)
Returns an array of a given object's own enumerable property names.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.getOwnPropertyNames(person)); // ["name", "age", "address"]
```
#### 🔍 Object.getPrototypeOf(obj)
Returns the prototype of an object.

```javascript
const person = {
  name: "John",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: 10001
  }
};
console.log(Object.getPrototypeOf(person)); // {constructor: ƒ, __defineGetter__: ƒ, __defineSetter__: ƒ, hasOwnProperty: ƒ, __lookupGetter__: ƒ, __lookupSetter__: ƒ, isPrototypeOf: ƒ, …}
```


#### 🔁 iterate over an object’s properties

#### 1. `for...in` loop :

```javascript
for (let key in person) {
  console.log(`${key}: ${person[key]}`);
}
```

#### 2. `Object.keys()` + `forEach()`:

```javascript
Object.keys(person).forEach(key => {
  console.log(`${key}: ${person[key]}`);
});
```

#### 3. `Object.entries()`:

```javascript
Object.entries(person).forEach(([key, value]) => {
  console.log(`${key}: ${value}`);
});
```

#### 🧱 Add a new property to an object

```javascript
person.email = "john@example.com";
```

#### 📥 Difference between Object.assign() and spread syntax

Both are used for shallow copying and merging, but with different syntax.

`Object.assign()`:

```javascript
const newPerson = Object.assign({}, person, { email: "john@example.com" });
```

Spread syntax :

```javascript
const newPerson = { ...person, email: "john@example.com" };
```

#### 🌊  A shallow copy of an object

A shallow copy copies only the first level of properties. If properties are objects or arrays, they are still referenced, not cloned.

```javascript
const original = { name: "Alice", scores: [90, 80] };
const shallowCopy = { ...original };

shallowCopy.scores.push(100);
console.log(original.scores); // [90, 80, 100] ⚠️ affected!
```

#### 🔗  Merge two objects in JavaScript

Using spread :

```javascript
const person = { name: "John", age: 30 };
const address = { city: "New York", country: "USA" };
const merged = { ...person, ...address };
```

Using `Object.assign()`:

```javascript
const person = { name: "John", age: 30 };
const address = { city: "New York", country: "USA" };
const merged = Object.assign({}, person, address);
```

#### 🔄  Convert an array into an object

1. Use `Object.fromEntries()`:

```javascript
const array = [["name", "John"], ["age", 30]];
const object = Object.fromEntries(array);
```

2. Use `reduce()`:

```javascript
const array = [["name", "John"], ["age", 30]];
const object = array.reduce((acc, [key, value]) => {
  acc[key] = value;
  return acc;
}, {});
```  
---
---
---


## 🔹What are conditional statements in JavaScript, and how do you use them?
Conditional statements in JavaScript are used to execute different blocks of code based on certain conditions. They allow you to make decisions in your programs. The most common conditional statements are `if`, `else`, `if-else`, and `switch`.

#### 📋 JavaScript Conditional Statements

| Statement              | Syntax Example                                        | Description                                    |
|------------------------|------------------------------------------------------|------------------------------------------------|
| `if`                   | `if (a > b) { ... }`                                  | Executes code block if condition is `true`     |
| `if...else`            | `if (a > b) { ... } else { ... }`                    | Executes one of two blocks                     |
| `if...else if...else`  | `if (a > b) { ... } else if (...) { ... } else {}`   | Handles multiple conditions                    |
| `switch`               | `switch(x) { case 'a': ... break; default: ... }`    | Matches value to multiple cases                |
| Ternary (`? :`)        | `let result = a > b ? "yes" : "no";`                 | Short `if...else` for simple expressions       |
| Logical `&&`, `||`, `!`| `if (a && b) { ... }`                                | Combines or inverts conditions                 |
| `??` Nullish Coalescing| `let name = user.name ?? "Guest";`                  | Uses fallback if `null` or `undefined`         |
| `?.` Optional Chaining | `let city = user?.address?.city;`                   | Safely access deeply nested properties         |



#### ✅ 1. `if` Statement

Executes a block of code if the condition is true.

```javascript
let x = 10;
if (x > 5) {
  console.log("x is greater than 5");
}
```

#### ✅ 2. `if...else` Statement
Executes one block of code if the condition is true, and another if it's false.

```javascript
if (score >= 60) {
  console.log("Passed");
} else {
  console.log("Failed");
}
```

#### ✅ 3. `if...else if...else` Statement
Executes one of several blocks of code based on multiple conditions.

```javascript
if (score >= 90) {
  console.log("Grade A");
} else if (score >= 75) {
  console.log("Grade B");
} else if (score >= 60) {
  console.log("Grade C");
} else {
  console.log("Fail");
}

```
#### ✅ 4. `switch` Statement
Executes different blocks of code based on the value of an expression.

```javascript
const color = "green";

switch (color) {
  case "red":
    console.log("Stop");
    break;
  case "green":
    console.log("Go");
    break;
  case "yellow":
    console.log("Wait");
    break;
  default:
    console.log("Unknown color");
}
```
#### ⚠️ Always use break to prevent fall-through (unless intentional).

#### ✅ 5. Ternary Operator (`? :`)
A shorthand for an `if...else` statement.

```javascript
const isAdult = age >= 18 ? true : false;
console.log(isAdult);
```

#### ✅ 6. Logical Operators in Conditions

You can combine multiple conditions using logical operators:

- `&&` (AND)

- `||` (OR)

- `!` (NOT)

```javascript
if (age > 18 && hasLicense) {
  console.log("You can drive.");
}

if (age < 13 || isWithAdult) {
  console.log("You can enter.");
}

if (!isVerified) {
  console.log("Access denied.");
}
```

#### ✅ 7. Optional: Nullish Coalescing (`??`) & Optional Chaining (`?.`)

Not conditional statements, but often used in conditional logic.

```javascript
const name = user.name ?? "Guest";   // If user.name is null or undefined
const city = user?.address?.city;    // Avoid errors if nested property missing
```

---
---
---

## 🔹What a loop in JavaScript is and how to use it?

#### 🔁 JavaScript Loops

Loops are used to repeat a block of code as long as a condition is true.

#### 1 . `for` Loop

Used when the number of iterations is known.

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

#### 🔹 Initializes `i = 0`, loops while `i < 5`, and increments `i` after each loop.

#### 2 . `while` Loop

Used when the number of iterations is not known.

```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```
#### 🔹 Checks the condition before executing the block.


#### 3 . `do...while` Loop

Similar to `while`, but the block runs at least once before the condition is checked.

```javascript
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);
```

#### 🔹 Executes the block at least once, then checks the condition.

#### 4 . `for...in` Loop

Used to iterate over the properties of an object.

```javascript
const obj = { a: 1, b: 2, c: 3 };
for (const key in obj) {
  console.log(key, obj[key]);
}
```

#### 🔸 Used for objects, not arrays (unless you want to iterate over custom properties).


#### 5 . `for...of` Loop

Used to iterate over the elements of an iterable object (arrays, strings, maps, sets, etc.).

```javascript
const arr = [1, 2, 3];
for (const value of arr) {
  console.log(value);
}
```
#### 🔸 Used for values, not keys.

#### 6 . `Array.forEach()` Method

Loops through an array without breaking or returning.

```javascript
const arr = [1, 2, 3];
arr.forEach((value) => {
  console.log(value);
});
```

#### 🔸 Cannot use break or return to exit early.


#### 🛑 Breaking and Continuing in Loops

#### `break` – exits the loop completely :

```javascript
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    break;
  }
  console.log(i);
}
```

#### `continue` – skips to the next iteration :

```javascript
for (let i = 0; i < 10; i++) {
  if (i % 2 === 0) {
    continue;
  }
  console.log(i);
}
```

#### 🔁 Summary of JavaScript Loops

| Loop Type     | Syntax Example                          | Can Break/Continue | Best For                       | Notes                                    |
|---------------|------------------------------------------|---------------------|--------------------------------|------------------------------------------|
| `for`         | `for (let i = 0; i < 5; i++) {}`         | ✅ Yes              | Indexed arrays                 | Use when iteration count is known        |
| `while`       | `while (i < 5) {}`                       | ✅ Yes              | Condition-based loops          | Checks condition before every iteration  |
| `do...while`  | `do { ... } while (i < 5);`              | ✅ Yes              | Run at least once              | Executes block before checking condition |
| `for...in`    | `for (let key in obj) {}`               | ✅ Yes              | Objects                        | Iterates over keys (not values)          |
| `for...of`    | `for (let value of iterable) {}`        | ✅ Yes              | Arrays, strings, iterables     | Iterates over values                     |
| `.forEach()`  | `arr.forEach((val) => {})`              | ❌ No               | Simple array iteration         | Can't break/return early                 |


#### ❓ `break` and `continue` work in loops

- `break` exits the loop **immediately**.
- `continue` skips the **current iteration** and proceeds to the next.

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) break;      // Stops the loop
  if (i === 1) continue;   // Skips number 1
  console.log(i);
}
// Output: 0, 2
```

#### ❓ Difference between a `while` loop and a `do...while` loop

| Feature              | `while` loop Example                                        | `do...while` loop                                    |
|------------------------|------------------------------------------------------|------------------------------------------------|
| Condition Check                   | Before executing the loop body                                  | After executing the loop body     |
| Minium Runs            | May run zero times                    | Always runs at least once                     |

```javascript
// while
let a = 5;
while (a < 5) {
  console.log("Never runs");
}

// do...while
let b = 5;
do {
  console.log("Runs once");
} while (b < 5);
// Output: Runs once
```


#### ❓ Different between q `for` loop and a `forEach()` loop


| Feature              | `for` loop Example                                        | `forEach()` loop                                    |
|------------------------|------------------------------------------------------|------------------------------------------------|
| Type                   | Keyword-based loop                                  | Array method     |
| Break/Continue            | 	✅ Supported                    | ❌ Not supported                     |
| Flexibility  | Can loop over any logic   | 	Only loops over array elements                    |

```javascript
const arr = [1, 2, 3];

// for
for (let i = 0; i < arr.length; i++) {
  if (arr[i] === 2) break;
  console.log(arr[i]);
}

// forEach
arr.forEach((num) => {
  console.log(num); // Can't break early!
});
```

