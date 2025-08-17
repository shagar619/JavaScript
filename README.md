<!-- markdownlint-disable MD012 MD026 MD001 MD022 MD032 MD029 MD019 MD034 MD031 MD047 MD040 MD009 MD058 MD024 MD038 MD010 MD056 MD033 MD041 MD045 MD007  -->

<div>

 <img src="https://i.ibb.co.com/B5GmYHrV/Unofficial-Java-Script-logo-2-svg.png" style="width:100%; height:auto;">

</div>

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


#### ✅ Best Practices

- Always prefer **strict equality (`===`)** to avoid unexpected type coercion.
- Use **type-safe comparisons** in conditionals, function logic, and validations.
- If you must use `==`, understand the coercion rules.


#### 🧪 Example Code

```javascript
console.log("42" == 42);        // true
console.log(false == 0);        // true
console.log(null == undefined); // true
console.log([] == 0);           // true
console.log([1] == "1");        // true
console.log({} == "[object Object]"); // false
```


## 🔹What is the difference between `Array.forEach()` and `Array.map()`?

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

#### 7. Array `map()`, `filter()`, `reduce()` (Iteration-like methods)

These aren’t loops per se, but they are widely used for iteration.
```javascript
const prices = [100, 200, 300];

// map - transform
const discounted = prices.map(p => p * 0.9);

// filter - conditionally include
const affordable = prices.filter(p => p < 250);

// reduce - accumulate
const total = prices.reduce((sum, p) => sum + p, 0);

console.log({ discounted, affordable, total });
```

#### 8. `for await...of` loop (ES2018)

Used to iterate over async iterables (e.g., handling promises in sequence).
```javascript
// Example: Handling multiple promises sequentially
const fetchData = async () => {
  const promises = [
    Promise.resolve("Data 1"),
    Promise.resolve("Data 2"),
    Promise.resolve("Data 3")
  ];

  for await (let result of promises) {
    console.log(result);
  }
};

fetchData();
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












#### ❓What would be the result of 3+2+"7"?

```javascript
console.log(3 + 2 + "7"); // Output: 57
```

- `3 + 2` is evaluated first, and since both are numbers, it results in `5`.
- Then, `5 + "7"` is calculated. Since one of the operands is a string ("7"), JavaScript converts the number `5` to a string and concatenates it with `"7"`, resulting in `"57"`.


#### ❓ What is the difference between JavaScript and TypeScript?

JavaScript and TypeScript are closely related, but they have some key differences in purpose, features, and development workflow.

**1. Language Type:**

- **JavaScript** → A dynamic, interpreted language used mainly for web development. No type-checking at compile time — variables can hold any type at any time.

- **TypeScript** → A statically typed superset of JavaScript that adds optional type annotations and compile-time checks.

**2. Compilation:**

- **JavaScript** → Runs directly in browsers or Node.js without a compilation step.

- **TypeScript** → Must be compiled (or "transpiled") into JavaScript before running, because browsers don’t understand TypeScript directly.


**3. Typing System:**

- **JavaScript** → Dynamically typed; types are determined at runtime, so some errors show up only when the code is executed.

- **TypeScript** → Statically typed (with optional types); catches many errors at compile time, before running the code.


**4. Tooling & IDE Support:**

- **JavaScript** → Good tooling support, but less help with catching type errors early.

- **TypeScript** → Excellent tooling support — intelligent autocompletion, type inference, and instant error checking.


**5. Feature Scope:**

- **JavaScript** → Implements the ECMAScript standard; limited to the features defined by that specification (though modern JS is quite powerful).

- **TypeScript** → Adds features like interfaces, enums, generics, and advanced type manipulation on top of JavaScript.


**6. Adoption:**

- **JavaScript** → Universally supported by all browsers and servers (via Node.js).

- **TypeScript** → Increasingly popular for large-scale projects where maintainability, refactoring, and safety are priorities.

**Quick Analogy:**

> If JavaScript is like speaking freely in a conversation, TypeScript is like speaking with a grammar checker and proofreader standing by — you can still say the same things, but you get warned before you make a mistake.

Example: TypeScript
```typescript
function add(x: number, y: number): number {
  return x + y;
}
```
Example: JavaScript
```javascript
function add(x, y) {
  return x + y;
}
```





## 🔹What is a Variable Scope in JavaScript?

In JavaScript, variable scope refers to where in your code a variable can be accessed or modified.
Scope determines the lifetime of a variable and which parts of the program can see it.

There are three main kinds in modern JavaScript:

1. **Global scope** – accessible anywhere.
2. **Function scope** – accessible only inside the function where it’s declared.
3. **Block scope** – accessible only inside the block `{ ... }` where it’s declared (with `let` or `const`).


Professional Example: API Request with Proper Scoping
```javascript
// 🌍 Global scope variable
const API_BASE_URL = "https://api.example.com";

function fetchUser(userId) {
  // Function scope variable
  const endpoint = `${API_BASE_URL}/users/${userId}`;

  try {
    // Block scope variable
    if (!userId) {
      const errorMessage = "User ID is required";
      throw new Error(errorMessage); // errorMessage is not accessible outside this block
    }

    console.log(`Fetching from: ${endpoint}`);

    // Simulate request
    let responseData; // block scoped but visible within entire function block
    {
      // inner block for simulation
      let mockData = { id: userId, name: "Alice" };
      responseData = mockData;
    }
    console.log("User:", responseData);

  } catch (err) {
    console.error("Error:", err.message);
  }

  // ❌ console.log(errorMessage); // ReferenceError: errorMessage is not defined
}

fetchUser(42);
```

**Why Scope Matters in Professional Code:**

1. **Avoids Naming Collisions**

   - Two developers can use the same variable name in different scopes without overwriting each other’s values.

2. **Prevents Memory Leaks**

   - Variables in a smaller scope get garbage-collected sooner.

3. **Improves Maintainability**

   - Localizing variables makes it easier to reason about code.


## 🔹What is the use of the isNaN function?

The `isNaN()` function in JavaScript is used to check whether a value is NaN (“Not-a-Number”).


**Key Points:**

- NaN is a special numeric value in JavaScript that represents an invalid number result (e.g., `0/0`, `parseInt("abc")`).

- `isNaN(value)` returns:

  - `true` → if the value is NaN (or cannot be coerced into a valid number).
  - `false` → if the value is a valid number after coercion.

- It converts the argument to a number before the check — which sometimes gives surprising results.

Example:
```javascript
console.log(isNaN(123));       // false  ✅ valid number
console.log(isNaN("123"));     // false  ✅ string can be converted to 123
console.log(isNaN("abc"));     // true   ❌ can't convert to number
console.log(isNaN(NaN));       // true   ✅ NaN is NaN
console.log(isNaN(undefined)); // true   ❌ undefined becomes NaN when coerced
```

Professional Use Case: Input Validation
```javascript
function processPayment(amount) {
  if (isNaN(amount)) {
    throw new Error("Invalid amount. Please provide a numeric value.");
  }
  console.log(`Processing $${Number(amount).toFixed(2)}`);
}

processPayment("50");    // ✅ "Processing $50.00"
processPayment("abc");   // ❌ Error: Invalid amount
```




## 🔹What is infinity in JS?

In JavaScript, `Infinity` is a special numeric value that represents a number larger than any other possible number.

It’s part of JavaScript’s number system (IEEE 754 floating-point) and has these characteristics:

- Type: `number`
- Greater than all finite numbers.
- Can result from arithmetic operations like dividing a positive number by zero.

How to Get `Infinity`:
```javascript
console.log(Infinity);              // Infinity
console.log(Number.POSITIVE_INFINITY); // Infinity
console.log(1 / 0);                  // Infinity
console.log(Math.pow(10, 1000));     // Infinity (too large to represent)
```

Behavior in Comparisons:
```javascript
console.log(Infinity > 1e308); // true
console.log(Infinity > 0);     // true
console.log(Infinity > -Infinity); // true
```

Example: Finding the Minimum Value in an Array
```javascript
function findMin(numbers) {
  let min = Infinity; // start with the largest possible number

  for (const num of numbers) {
    if (num < min) {
      min = num;
    }
  }

  return min;
}

console.log(findMin([15, 3, 27, -4, 8])); // -4
```

**Special Notes:**

- `typeof` Infinity returns `"number"`.
- Arithmetic rules with Infinity:

```javascript
console.log(Infinity + 1);    // Infinity
console.log(Infinity - Infinity); // NaN (undefined result)
console.log(1 / Infinity);    // 0
```

- Infinity can also appear in overflow situations where a number exceeds JavaScript’s maximum representable value (Number.MAX_VALUE).


## 🔹 What are "truthy" and "falsy" values in JavaScript?

ChatGPT said:

In JavaScript, every value is either truthy or falsy when evaluated in a boolean context (e.g., inside an if statement).

- `Truthy` → values that evaluate to true in a boolean context.
- `Falsy` → values that evaluate to false in a boolean context.

**Falsy Values (only 8 in JS):**

These are the only values considered falsy:
```javascript
false
0           // the number zero
-0          // negative zero
0n          // BigInt zero
""          // empty string
null
undefined
NaN         // not-a-number
```

**Truthy Values:**

Everything else is truthy — including:

- Non-empty strings (`"hello"`)
- Non-zero numbers (`42`, `-1`)
- Objects (`{}`, `[]`)
- Functions

Dates, regex, and most other non-null objects
Example:
```javascript
console.log(Boolean(0));    // false
console.log(Boolean(1));    // true
console.log(Boolean(""));   // false
console.log(Boolean("hello")); // true
console.log(Boolean([]));   // true
console.log(Boolean({}));   // true
```

Example: Input Validation
```javascript
function processInput(input) {
  if (!input) {
    console.error("Invalid input: value is falsy");
    return;
  }
  console.log("Processing:", input);
}

processInput("");     // Invalid input
processInput(0);      // Invalid input
processInput("data"); // Processing: data
```

## 🔹What are undeclared and undefined variables?

In JavaScript, undeclared and undefined variables sound similar but mean very different things — and confusing them can cause serious bugs.

**1. Undeclared Variables:**

- A variable that has never been declared in the current scope with `var`, `let`, or `const`.
- Accessing it throws a `ReferenceError`.
- Usually caused by typos or forgetting `let`/`const`/`var`.

Example:
```javascript
console.log(myVariable); // ReferenceError: myVariable is not defined
```

> If you assign to a variable without declaring it (in non–strict mode), JavaScript implicitly creates a global variable — a dangerous, error-prone behavior.

```javascript
function test() {
  accidentalVar = 42; // No let/const/var → becomes global (non-strict mode only)
}
test();
console.log(accidentalVar); // 42 (global!)
```

In **strict mode**, this throws an error:
```javascript
"use strict";
"use strict";
accidentalVar = 42; // ❌ ReferenceError
```

**2. Undefined Variables:**

- A variable that has been declared but not yet assigned a value.
- Its value is automatically `undefined` until you assign something else.

Example:
```javascript
let myVar;
console.log(myVar); // ✅ undefined
```

also explicitly set `undefined`:
```javascript
let myVar = undefined;
console.log(myVar); // ✅ undefined
```


#### ❓What will be the result of this expression?
```javascript
console.log(null ?? 'default');
console.log(undefined ?? 'default');
console.log(false ?? 'default');
```

**Step-by-step:**

1. `null ?? 'default'`

   - `null` is nullish → returns `'default'`.
     ✅ Output: `default`

2. `undefined ?? 'default'`

   - `undefined` is nullish → returns `'default'`.
     ✅ Output: `default`

3. `false ?? 'default'`

   - `false` is not nullish (it’s a valid boolean) → returns `false`.
   ✅ Output: `false`

Final Output:
```javascript
console.log(null ?? 'default'); // ✅ Output: 'default'
console.log(undefined ?? 'default'); // ✅ Output: 'default'
console.log(false ?? 'default'); // ✅ Output: false
```


#### ❓What is `null` in JavaScript?

In JavaScript, `null` is a primitive value that represents the intentional absence of any object value.

Think of it as “there’s supposed to be something here, but it’s empty on purpose.”

**Key Points about `null`:**

**Type:**
```javascript
typeof null; // "object"  <-- historical bug in JS
```

> Despite returning `"object"`, `null` is not an object — it’s its own primitive type.


- Meaning:
Indicates a variable should point to nothing (explicitly empty), often used for object placeholders.

- Difference from `undefined`:

  - `undefined` → variable has been declared but not assigned a value (no value yet).
  - `null` → variable has been assigned no value on purpose.

Examples:
```javascript
let user = null; // explicitly no user
console.log(user); // null

if (user === null) {
  console.log("No user is currently logged in.");
}
```


#### ❓What will be the output of this code?
```javascript
console.log(0 || "hello"); // "hello"
console.log("" || "hello"); // "hello"
console.log(0 || 1); // 1
console.log("" || 1); // 1
```
**Explanation:**
- `0 || "hello"`: The logical OR operator returns the first truthy value. Since `"hello"` is truthy, it returns `"hello"`.
- `"" || "hello"`: Similarly, `"hello"` is truthy, so it returns `"hello"`.
- `0 || 1`: The first operand is falsy (0), so the second operand (1) is returned.
- `"" || 1`: The first operand is falsy (empty string), so the second operand (1) is returned.

#### ❓What will be the output of this code?
```javascript
let x = 0;
console.log(x++);
console.log(++x);
```
**Explanation:**
- `x++` first returns the current value of `x` (0) and then increments `x` by 1.
- `++x` first increments `x` by 1 and then returns the new value (1).


## 🔹What is the `this` keyword in JavaScript?

In JavaScript, the `this` keyword is a special identifier whose value depends on how a function is called, not where it is defined.

It essentially refers to the "execution context" — the object that is currently invoking the function.


Key Rules for `this`:
| Context                            | Value of `this`                                            |
| ---------------------------------- | ---------------------------------------------------------- |
| **Global scope (non-strict)**      | `window` (in browsers) or `global` (Node.js)               |
| **Global scope (strict mode)**     | `undefined`                                                |
| **Inside a method**                | The object that owns the method                            |
| **Inside a function (non-strict)** | `window`/`global`                                          |
| **Inside a function (strict)**     | `undefined`                                                |
| **Inside a constructor**           | The new object being created                               |
| **Inside a class method**          | The instance of the class                                  |
| **With `call` / `apply` / `bind`** | Explicitly set value                                       |
| **Inside an arrow function**       | Inherits `this` from the enclosing scope (lexical binding) |


**Professional Examples:**

**1. Object Method:**
```javascript
let person = {
  name: "John",
  greet: function() {
    console.log(`Hello, my name is ${this.name}.`);
  }
};
person.greet(); // Output: Hello, my name is John.
```
> Here, `this` → `user` object.

**2. Constructor Function:**
```javascript
function Person(name) {
  this.name = name;
}

const p1 = new Person("Bob");
console.log(p1.name); // Bob
```
> Here, `this` → the newly created instance (`p1`).

**3. Using `call`, `apply`, `bind`:**
```javascript
function greet(lang) {
  console.log(`Hello in ${lang}, I'm ${this.name}`);
}

const user = { name: "Clara" };

greet.call(user, "English"); // Hello in English, I'm Clara
greet.apply(user, ["French"]); // Hello in French, I'm Clara
const boundGreet = greet.bind(user, "Spanish");
boundGreet(); // Hello in Spanish, I'm Clara
```

> Here, `this` is manually bound to `user`.

**4. Arrow Function Lexical `this`:**
```javascript
const team = {
  name: "Dev Team",
  members: ["Ann", "Ben"],
  listMembers() {
    this.members.forEach(member => {
      console.log(`${member} is on ${this.name}`);
    });
  }
};

team.listMembers();
// Ann is on Dev Team
// Ben is on Dev Team
```
> Here, `this` refers to the `team` object.

**5. In Event Listeners:**
```javascript
document.querySelector("#btn").addEventListener("click", function () {
  console.log(this); // The button element
});
```

> Here, `this` refers to the button element.

**6. In `setInterval` and `setTimeout`:**
```javascript
const intervalId = setInterval(() => {
  console.log("Hello");
}, 1000);
const timeoutId = setTimeout(() => {
  console.log("Timeout");
}, 2000);
```
> Here, `this` refers to the global object (`window` in browsers).



## 🔹 What is the difference between ViewState and SessionState?

**ViewState** is a feature in ASP.NET that allows you to persist the state of a page across postbacks. It stores the state of the page in a hidden field called `__VIEWSTATE`. ViewState is useful when you need to maintain the state of a page across multiple postbacks, such as when a user clicks a button or submits a form.

**SessionState** is a feature in ASP.NET that allows you to store session data on the server. It stores the data in a session state manager, which is accessed by the application using the `Session` object. SessionState is useful when you need to store data that is specific to a user's session, such as user preferences or shopping cart contents.




## 🔹How to submit a form using JavaScript?

In JavaScript, you can submit a form programmatically without the user clicking the submit button by using the `.submit()` method on the form element.

Basic Example:
```html
<form id="myForm" action="/submit" method="POST">
  <input type="text" name="username" value="JohnDoe" />
</form>

<script>
  // Get the form element
  const form = document.getElementById("myForm");

  // Submit the form programmatically
  form.submit();
</script>
```

**How it works:**

- `.submit()` directly triggers form submission.
- It does not fire the `submit` event listeners — it bypasses them.


With Validation Before Submit:
```html
<form id="loginForm" action="/login" method="POST">
  <input type="text" name="username" placeholder="Username" required />
  <input type="password" name="password" placeholder="Password" required />
</form>

<script>
  const form = document.getElementById("loginForm");

  function validateAndSubmit() {
    if (form.checkValidity()) {
      form.submit(); // Only submit if valid
    } else {
      alert("Please fill in all required fields.");
    }
  }

  // Call validateAndSubmit() from anywhere
  validateAndSubmit();
</script>
```

Triggering Submit via Button Click:
```html
<form id="contactForm" action="/contact" method="POST">
  <input type="email" name="email" placeholder="Email" required />
  <button type="button" onclick="submitContactForm()">Submit</button>
</form>

<script>
  function submitContactForm() {
    document.getElementById("contactForm").submit();
  }
</script>
```

> Here, the button has `type="button"` so it doesn’t automatically submit; you control when to call `.submit()`.



## 🔹What is a higher-order function in JavaScript?

A higher-order function in JavaScript is a function that either:

1. Takes another function as an argument (callback), or
2. Returns a function as its result.

This is possible because in JavaScript, functions are first-class citizens — they can be stored in variables, passed around, and returned just like data.

**Professional Definition:**

A higher-order function abstracts actions, not just values, enabling more reusable, modular, and declarative code.

Example 1 – Takes a Function as an Argument:
```javascript
function processArray(arr, callback) {
  const result = [];
  for (let item of arr) {
    result.push(callback(item));
  }
  return result;
}

// Usage: Pass a function to transform items
const doubled = processArray([1, 2, 3], num => num * 2);
console.log(doubled); // [2, 4, 6]
```
> Here, `processArray` is higher-order because it accepts a function (`callback`) as an argument.

Example 2 – Returns a Function:
```javascript
function multiplier(factor) {
  return function (number) {
    return number * factor;
  };
}

// Usage: Create specialized functions
const double = multiplier(2);
console.log(double(5)); // 10
```

> Here, `multiplier` is higher-order because it returns a new function.

Example 3 – Both Accepts and Returns:
```javascript
function compose(f, g) {
  return function (x) {
    return f(g(x));
  };
}

const addOne = x => x + 1;
const square = x => x * x;

const addOneThenSquare = compose(square, addOne);
console.log(addOneThenSquare(4)); // 25
```

> Here, `compose` is higher-order because it accepts two functions and returns a new function that combines their effects.

**Common Higher-Order Functions in JavaScript:**

- `map()`
- `filter()`
- `reduce()`
- `forEach()`
- `setTimeout()`
- `setInterval()`




## 🔹How can Error Handling using javascript?

Error handling in JavaScript can be done in multiple ways, depending on whether the code is synchronous or asynchronous.
Below is a professional, comprehensive guide with examples for all major approaches.

**1. `try...catch` (Synchronous Errors):**

Wrap potentially failing code in `try` and handle errors in `catch`.
```javascript
try {
  let result = riskyOperation(); // might throw an error
  console.log("Result:", result);
} catch (error) {
  console.error("Something went wrong:", error.message);
} finally {
  console.log("Cleanup actions (always runs).");
}
```

**Use case:**

- Parsing JSON
- DOM manipulation when element may not exist
- Any synchronous code

**2. Throwing Custom Errors:**

You can throw built-in errors or create your own error types.
```javascript
function divide(a, b) {
  if (b === 0) {
    throw new Error("Division by zero is not allowed.");
  }
  return a / b;
}

try {
  console.log(divide(10, 0));
} catch (error) {
  console.error(error.name, error.message);
}
```


**3. Error Handling in Asynchronous Code (Callbacks):**

In callback-based APIs, errors are usually passed as the first argument.
```javascript
function fetchData(callback) {
  setTimeout(() => {
    const error = Math.random() > 0.5 ? new Error("Network failed") : null;
    if (error) return callback(error);
    callback(null, { data: "Hello World" });
  }, 1000);
}

fetchData((err, result) => {
  if (err) {
    console.error("Error:", err.message);
  } else {
    console.log("Data:", result.data);
  }
});
```

**4. Error Handling in Promises:**

Use `.catch()` to handle errors from promise chains.
```javascript
fetch("https://api.example.com/data")
  .then(res => {
    if (!res.ok) throw new Error("HTTP error " + res.status);
    return res.json();
  })
  .then(data => console.log(data))
  .catch(err => console.error("Promise error:", err.message));
```

**5. Error Handling with `async/await`:**

Combine `try...catch` with `await` for clean asynchronous error handling.
```javascript
async function loadData() {
  try {
    const res = await fetch("https://api.example.com/data");
    if (!res.ok) throw new Error(`HTTP error ${res.status}`);
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error("Async error:", err.message);
  }
}

loadData();
```

**6. Global Error Handling:**

**a) Synchronous (Window Errors in Browsers):**
```javascript
window.onerror = function (message, source, lineno, colno, error) {
  console.error("Error:", error);
};
```

**b) Unhandled Promise Rejections:**
```javascript
process.on("unhandledRejection", (reason, promise) => {
  console.error("Unhandled rejection:", reason);
});
```

**7. Defensive Programming:**

Avoid errors by checking conditions before risky operations.
```javascript
const user = {};
if (user && user.profile) {
  console.log(user.profile.name);
} else {
  console.log("Profile not found");
}
```

**8. Using Error Subclasses:**

Professional projects often use custom error classes for clarity.
```javascript
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

function validateUser(user) {
  if (!user.name) throw new ValidationError("Name is required");
}

try {
  validateUser({});
} catch (err) {
  if (err instanceof ValidationError) {
    console.error("Validation failed:", err.message);
  } else {
    throw err; // rethrow unexpected errors
  }
}
```


## 🔹What is lexical scope in JavaScript?

Lexical scope (also called static scope) means that the scope of a variable is determined by its position in the source code, and nested functions have access to variables declared in their parent functions.

In other words:

- Where you write your code defines which variables you can access.
- Scope is fixed at the time of writing code, not when the code runs.

✅ Example of Lexical Scope:
```javascript
function outerFunction() {
  let outerVar = "I am outside!";
  
  function innerFunction() {
    console.log(outerVar); // ✅ Accessible because of lexical scope
  }
  
  innerFunction();
}

outerFunction();
```

**🔍 Explanation:**

- `innerFunction` is defined inside outerFunction.
- Because of lexical scope, `innerFunction` has access to variables declared in its parent (`outerVar`).
- Even though `outerVar` is not inside `innerFunction`, JavaScript allows access because the function was written inside that scope.

**Lexical Scope & Closures:**

Closures are directly based on lexical scope.
A closure allows a function to "remember" the scope in which it was created, even after that scope is gone.
```javascript
function createCounter() {
  let count = 0;
  
  return function() {
    count++;
    return count;
  };
}

const counter = createCounter();

console.log(counter()); // 1
console.log(counter()); // 2
```

> 👉 The inner function remembers `count` because of lexical scope, even after `createCounter()` has finished execution.


**🔑 Key Takeaways:**

1. Lexical scope is based on where you write the code, not where it’s called.
2. Inner functions have access to outer function variables.
3. This concept is the foundation of closures in JavaScript.



## 🔹What is hoisting in JavaScript?

Hoisting is JavaScript’s default behavior of moving declarations (not initializations) to the top of their scope during the compilation phase (before code execution).

- **Function declarations** and **variable declarations** are hoisted.
- **Only the declarations are hoisted**, not the assignments.

Variable Hoisting (with `var`):
```javascript
console.log(x); // 👉 undefined (not ReferenceError!)
var x = 5;
console.log(x); // 👉 5
```

Explanation:

The declaration `var x`; is hoisted to the top.
But the assignment `x = 5`; stays in place.

Internally, JavaScript treats it like:
```javascript
var x;          // hoisted
console.log(x); // undefined
x = 5;          // assignment remains
console.log(x); // 5
```

Function Hoisting:
```javascript
sayHello(); // 👉 "Hello!"

function sayHello() {
  console.log("Hello!");
}
```

Explanation:

- Function declarations are fully hoisted (both name and body).
- You can call the function before it’s defined in the code.


`let` and `const` (Temporal Dead Zone):
```javascript
console.log(a); // ❌ ReferenceError
let a = 10;

console.log(b); // ❌ ReferenceError
const b = 20;
```

Explanation:

- `let` and `const` are also hoisted, but they are placed in a Temporal Dead Zone (TDZ) until the line of declaration is executed.
- This means you cannot access them before declaration.

Function Expression (Not Hoisted Fully):
```javascript
sayHi(); // ❌ TypeError: sayHi is not a function

var sayHi = function() {
  console.log("Hi!");
};
```

Explanation:

- `var sayHi` is hoisted (as `undefined`).
- The function expression assignment happens later.
- At the time of call, `sayHi` is still `undefined`, so calling it throws an error.


**🔑 Key Takeaways:**

1. `var` declarations → Hoisted and initialized with `undefined`.
2. `let` and `const` → Hoisted but live in the Temporal Dead Zone until initialized.
3. Function declarations → Fully hoisted (can be called before they appear).
4. Function expressions / arrow functions → Behave like variables (`var`, `let`, `const`).





## 🔹What are the types of Pop up boxes available in JavaScript?

**Types of Popup Boxes in JavaScript:**

**1. Alert Box:**

- Displays a message with an OK button.
- Used to give information or warnings.
- Execution pauses until the user clicks "OK".

```javascript
alert("This is an alert message!");
```

> 💡 Example use case: showing a warning like “Form submission failed!”.


2. Confirm Box

Displays a message with **OK** and **Cancel** buttons.

Returns:
  - `true` → if user clicks **OK**
  - `false` → if user clicks **Cancel**

```javascript
let response = confirm("Are you sure you want to delete this item?");
if (response) {
  console.log("Item deleted!");
} else {
  console.log("Action canceled.");
}
```

> 💡 Example use case: asking for confirmation before performing critical actions (e.g., deleting data).


**3. Prompt Box:**

- Displays a message with a text field and **OK/Cancel** buttons.
- Returns:
  - The entered string (if user clicks **OK**)
  - `null` (if user clicks **Cancel**)

```javascript
let name = prompt("What is your name?", "Guest");
if (name !== null) {
  console.log("Hello, " + name + "!");
} else {
  console.log("User canceled input.");
}
```

> 💡 Example use case: taking small inputs from the user (like a name or password).



## 🔹What is the use of `void(0)` in javascript?

- The `void` operator in JavaScript evaluates an expression and returns `undefined`.
- So, `void(0)` → evaluates `0` (or any expression) and then returns `undefined`.

In practice, `void(0)` is often used to prevent an unwanted action like page refresh or navigation, while still allowing an event handler (e.g., `onclick`) to run.


Preventing Link Navigation:
```html
<a href="javascript:void(0)" onclick="alert('Hello!')">
  Click me
</a>
```

- Normally, clicking a link reloads or navigates the page.
- Using `javascript:void(0)` as the `href` ensures that nothing happens (the link doesn’t go anywhere).
- Only the `onclick` event executes.

Prevent Form Submission:
```html
<button type="button" onclick="void(0); alert('Button clicked!');">
  Click Me
</button>
```

- Here `void(0)` does nothing but ensures no unintended value is returned.

Explicitly Returning `undefined`:
```javascript
function test() {
  return void 123; // always returns undefined
}

console.log(test()); // undefined
```

- Regardless of the expression (`123`), `void` ensures the result is always `undefined`.


**Important Notes:**

- Modern best practice: Instead of `javascript:void(0)`, developers prefer:

  - `href="#"` with `event.preventDefault()` in JavaScript, or
  - Using a `<button>` element if it’s not an actual link.

Example:

```html
<a href="#" onclick="event.preventDefault(); alert('Link clicked!');">
  Click me
</a>

<button type="button" onclick="alert('Button clicked!');">
  Click Me
</button>
```



## 🔹What are JavaScript modules?

A module in JavaScript is simply a file that contains reusable code.

- By default, everything inside a module is scoped locally to that file.
- To use code from one module in another, we use exports and imports.

Modules make code more modular, maintainable, and easier to test.

**Types of JavaScript Modules:**

**1. ES6 Modules (Standard, Modern Way):**

Introduced in **ES6** (**ECMAScript 2015**).
They use `export` and `import` keywords.

Example: **Named Exports**

📁 `math.js`
```javascript
export const PI = 3.14;
export function add(x, y) {
  return x + y;
}
```

📁 `app.js`
```javascript
import { PI, add } from './math.js';

console.log(PI); // 3.14
console.log(add(2, 3)); // 5
```



Example: **Default Export**

📁 `logger.js`
```javascript
function log(message) {
  console.log(message);
}

export default log;
```

📁 `app.js`
```javascript
import log from './logger.js';

log("This is a default export example.");
```
> 👉 Only one default export per file, but many named exports allowed.

**2. CommonJS Modules (Node.js Standard Before ES6):**

Used in **Node.js** before **ES6** modules were supported.
They use `require` and `module.exports`.

📁 `math.js`
```javascript
const PI = 3.14;
function add(x, y) {
  return x + y;
}
module.exports = { PI, add };
```
📁 `app.js`
```javascript
const { PI, add } = require('./math.js');

console.log(PI); // 3.14
console.log(add(2, 3)); // 5
```

**3. UMD (Universal Module Definition):**

- Designed to work in both browsers and Node.js.
- Often used in libraries (like Lodash). 
- Detects environment and exports accordingly.

Example (simplified):
```javascript
(function (root, factory) {
  if (typeof define === "function" && define.amd) {
    // AMD
    define([], factory);
  } else if (typeof exports === "object") {
    // Node.js
    module.exports = factory();
  } else {
    // Browser globals
    root.myLibrary = factory();
  }
}(this, function () {
  // Library code here
}));
```

**4. AMD (Asynchronous Module Definition):**

- Mainly used in browsers (before ES6 modules).
- Works asynchronously using define.
- Common in older libraries (e.g., RequireJS).

```javascript
define([], function() {
  function greet(name) {
    return "Hello, " + name;
  }
  return { greet };
});
```

Usage:
```javascript
require(['greet'], function(greet) {
  console.log(greet('World')); // Outputs: "Hello, World"
});
```

**🔑 Key Takeaways:**

1. **ES6 Modules** → Modern standard (`import` / `export`). Best choice for modern apps.
2. **CommonJS** → Node.js’ older module system (`require` / `module.exports`).
3. **UMD** → Works in both Node.js and browsers. Good for libraries.
4. **AMD** → Asynchronous, used in browsers with RequireJS (less common today).


**✅ Professional Example: Splitting Business Logic:**

📁 `services/userService.js`
```javascript
export function getUser(id) {
  return { id, name: "Alice", role: "Admin" };
}
```

📁 `controllers/userController.js`
```javascript
import { getUser } from "../services/userService.js";

export function showUser(id) {
  const user = getUser(id);
  console.log(`User: ${user.name}, Role: ${user.role}`);
}
```

📁 `app.js`
```javascript
import { showUser } from "./controllers/userController.js";

showUser(1); // User: Alice, Role: Admin
```

> 👉 This is clean, modular, testable, and scalable.


## 🔹What is the **Strict** mode in JavaScript and how can it be enabled?

**Strict Mode:**

- Introduced in **ECMAScript 5** (**ES5**).
- It changes the way JavaScript executes code by enforcing stricter rules.
- Helps catch common coding mistakes and unsafe actions.
- Eliminates some silent errors by throwing exceptions.

**Enable Strict Mode:**

**1. For the entire script:**

Place `"use strict"`; at the top of a JavaScript file.
```javascript
"use strict";

x = 10; // ❌ ReferenceError (must declare variable with let/const/var)
```

**2. For a specific function:**

Place `"use strict"`; inside the function body.
```javascript
function demo() {
  "use strict";
  y = 20; // ❌ ReferenceError
}

demo();
```

> 👉 If `"use strict"`; is not at the very beginning, it will be ignored.



**Effects of Strict Mode:**

**1. Prevents using undeclared variables:**
```javascript
"use strict";
x = 100; // ❌ ReferenceError
```

**2. Prevents deleting variables, functions, or objects:**
```javascript
"use strict";
let num = 5;
delete num; // ❌ SyntaxError
```

**3. Prevents duplicate parameter names:**
```javascript
"use strict";
function test(a, a) { // ❌ SyntaxError
  return a;
}
```

**4. Makes this behave more predictably:**
```javascript
"use strict";
function show() {
  console.log(this); 
}
show(); // ❌ undefined (instead of global object)
```

**5. Reserved keywords for future use cannot be used as variable names:**
```javascript
"use strict";
let public = 5; // ❌ SyntaxError
let private = 10; // ❌ SyntaxError
```

**6. Silent errors become visible:**

Without strict mode:
```javascript
num = 10; // Creates a global variable implicitly
```

With strict mode:
```javascript
"use strict";
num = 10; // ❌ ReferenceError
```

**🔑 Why Use Strict Mode?**

- ✔️ Helps write cleaner, more secure code
- ✔️ Catches common mistakes early
- ✔️ Makes code more consistent with modern JavaScript
- ✔️ Recommended for all modern applications


## 🔹What are the purpose of using `async/await` over traditional `callbacks` or `promises`?

Background: **Callbacks** vs **Promises** vs **Async/Await**

1. **Callbacks:**

- Functions passed into other functions to be executed later.
- Problems:

  - "Callback hell" → deeply nested code, hard to read/maintain.
  - Error handling scattered (need to manually check err).
  - Flow control is tricky.

```javascript
// Example with callbacks
function fetchUser(id, callback) {
  database.getUser(id, function (err, user) {
    if (err) return callback(err);
    api.getPosts(user.id, function (err, posts) {
      if (err) return callback(err);
      callback(null, { user, posts });
    });
  });
}
```

**Promises:**

- A cleaner abstraction for async results.
- Problems:

  - Still leads to chaining (`.then().catch().finally()`).
  - Can get verbose when mixing multiple async operations.
  - Less natural for sequential-looking code.

```javascript
// Example with promises
function fetchUser(id) {
  return database.getUser(id)
    .then(user => api.getPosts(user.id)
      .then(posts => ({ user, posts })))
    .catch(err => { throw err });
}
```

**Async/Await:**

- Syntactic sugar on top of Promises.
- Makes async code look synchronous.
- Easier to read, debug, and maintain.

```javascript
// Example with async/await
async function fetchUser(id) {
  try {
    const user = await database.getUser(id);
    const posts = await api.getPosts(user.id);
    return { user, posts };
  } catch (err) {
    throw err;
  }
}
```

**Purposes of Using Async/Await:**

**1. Improved Readability (Synchronous Style):**

- Code looks like synchronous flow, easier for humans to understand.
- Avoids "pyramid of doom" in callbacks and heavy `.then()` chaining.

**2. Better Error Handling:**

- Works naturally with `try/catch`, rather than mixing `.catch()` everywhere.
- Easier debugging since stack traces are cleaner.

**3. Maintainability:**

- Business logic expressed in a linear, step-by-step style.
- Reduces mental overhead for future developers.

**4. Integration with Modern JS:**

- Works seamlessly with `Promise.all`, `for-await-of`, etc.
- Allows concurrent and sequential flows in a clean manner.


**Sequential API Calls:**

Imagine you’re writing a backend that fetches user info, then needs their orders, then calculates totals.

With Promises:
```javascript
function getUserOrderTotal(userId) {
  return getUser(userId)
    .then(user => getOrders(user.id))
    .then(orders => calculateTotal(orders))
    .catch(err => { throw err; });
}
```

With Async/Await:
```javascript
async function getUserOrderTotal(userId) {
  try {
    const user = await getUser(userId);
    const orders = await getOrders(user.id);
    return calculateTotal(orders);
  } catch (err) {
    throw err;
  }
}
```

**Concurrent API Calls:**

Fetching independent data (e.g., products, categories, and reviews).

With Promises:
```javascript
Promise.all([getProducts(), getCategories(), getReviews()])
  .then(([products, categories, reviews]) => {
    console.log(products, categories, reviews);
  })
  .catch(console.error);
```

With Async/Await:
```javascript
async function loadDashboard() {
  try {
    const [products, categories, reviews] = await Promise.all([
      getProducts(),
      getCategories(),
      getReviews()
    ]);
    console.log(products, categories, reviews);
  } catch (err) {
    console.error(err);
  }
}
```

**Looping with Async Operations:**

Fetching user activity logs sequentially.

With Promises:
```javascript
users.reduce((p, user) => {
  return p.then(() => getActivity(user.id).then(log => console.log(log)));
}, Promise.resolve());
```

With Async/Await:
```javascript
async function processLogs(users) {
  for (const user of users) {
    const log = await getActivity(user.id);
    console.log(log);
  }
}
```




## 🔹What are closures in JavaScript, and when to use them?

Closures are a fundamental concept in JavaScript, allowing functions to "remember" the environment in which they were created. A closure is formed when a function is defined inside another function, giving the inner function access to the outer function's variables.

#### When to Use Closures:

Closures are used when you want to:

**1. Data Encapsulation / Information Hiding:**
  - Keep certain variables private and only expose controlled access.

**2. Function Factories (Dynamic Function Creation):**
  - Generate functions that remember specific configuration.

**3. Maintaining State Across Function Calls:**
  - Keep track of values without relying on global variables.

**4. Callbacks and Asynchronous Code:**
  - Closures help preserve context in async operations (e.g., event listeners, setTimeout).

### Example of a Closure:

```javascript
function outer() {
  let counter = 0;
  
  function inner() {
    counter++;
    return counter;
  }
  
  return inner;
}

const increment = outer();
console.log(increment()); // 1
console.log(increment()); // 2
console.log(increment()); // 3
```

Here:

- `inner()` is a closure.
- It remembers `counter` from `outer()’s` scope even though `outer()` has already finished execution.


**Encapsulation (Private Variables in Modules):**

Imagine you’re building a logging utility where you don’t want direct access to internal state:
```javascript
function createLogger() {
  let logs = []; // private

  return {
    addLog(message) {
      logs.push({ message, timestamp: new Date() });
    },
    getLogs() {
      return [...logs]; // safe copy
    }
  };
}

const logger = createLogger();
logger.addLog("System started");
logger.addLog("User logged in");

console.log(logger.getLogs());
// Direct access to `logs` is not possible
```

> Here, `logs` is encapsulated — only accessible through the closure methods.


