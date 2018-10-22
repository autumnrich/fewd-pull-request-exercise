class: center, middle

# Unit 7
## JavaScript (JS)
### Interactivity & Custom Behaviors

---

class: center, middle
# Developing in Layers

## .red-text[HTML] -  structural layer of web pages
## .red-text[CSS] - presentational layer of web pages
## .red-text[JavaScript] - behavioral layer of web pages

---

name: js-history
class: center, middle
# Brief History of JavaScript
### - created in 10 days by Brendan Eich at Netscape (1995)
### - standardized by ECMA ("ECMAScript") (1996) 
### - Node.js JavaScript runtime environment in 2008
### - ECMAScript standard 6 released ("ES6") (2015)

???
[Wikipedia: JavaScript](https://en.wikipedia.org/wiki/JavaScript)

[A Brief History of JavaScript](https://auth0.com/blog/a-brief-history-of-javascript/)

[European Computer Manufacturers Association (ECMA)](https://en.wikipedia.org/wiki/Ecma_International)

---

name: js-name
class: middle

> .red-text[JavaScript] is as related to .red-text[Java] as .red-text[Carnival] is to .red-text[Car].

<cite>-- Kyle Simpson</cite>

---

name: js-what-is

# What is JavaScript?

### - client & server-side programming language
### - reliant on runtime capabilities and settings
### - dynamic programming language
### - (runtime interprets code on the fly)
### - loosely typed ( don't have to tell JS what a variable is)

---

name: js-can-do

# What can JavaScript do?

### - controls the "behavioral" layer of web pages
### - all elements, attributes, and text on a web page can be accessed by scripts via the DOM
### - scripts can react to user input (alter contents, styles or browser behavior "on the fly")
### - request content and info from server and inject into page without refresh ("ajax")

---

name: js-sample-script-clean

# Sample Script

```javascript
const today = new Date();
const hourNow = today.getHours();
let greeting;

if (hourNow > 18) {
  greeting = "Good evening";
} else if (hourNow > 12) {
  greeting = "Good afternoon";
} else if (hourNow > 0) {
  greeting = "Good morning";
} else {
  greeting = "Welcome";
}

document.write(greeting);
```

---

name: programming-basics
class: center, middle

# Basic Principles of Programming
## JavaScript

---

name: programming-code
class: middle

# Code

> A .red-text[program], often referred to as .red-text[source code] or just .red-text[code], is a set of .red-text[special instructions] to tell the computer what tasks to perform.

<cite>-- Kyle Simpson</cite>

---

name: programming-syntax
class: middle

# Programming Language

> The .red-text[rules for valid format] and combinations of instructions is called a .red-text[computer language], sometimes referred to as its .red-text[syntax], much the .red-text[same as English] tells you how to spell words and how to create valid sentences using words and punctuation.

<cite>-- Kyle Simpson</cite>

---

name: js-statements

# Statements
### a group of words, numbers, and operators that performs a specific task

```javascript
a = b * 2;
```

### `a` and `b` are <em>variables</em> (symbolic containers)
### `2` is a <em>literal value</em> (stands alone, not stored in a variable)
### `=` and `*` are <em>operators</em> (perform actions: assignment and multiplication)
### most statements in JavaScript end with a semicolon (;)

---

name: js-expressions

# Expressions
### - statements are made up of one or more expressions
### - any reference to a variable or value, or a set of variable(s) and value(s) combined with operators

```javascript
a = b * 2;
```

### 4 expressions:

- `2` is a <em>literal value expression</em>
- `b` is a <em>variable expression</em> (retrieve its current value)
- `b * 2` is an <em>arithmetic expression</em> (do the multiplication)
- `a = b * 2` is an <em>assignment expression</em>

---

name: program-execution

# Executing a Program

### - programs are collections of statements
### - programs need to be executed (run the program)
### - interpreter or compiler translates statements into commands a computer can understand
### - some programming languages are interpreting the code ever time the program runs
### - other languages are compiling code ahead of time
### - JavaScript engine compiles program on the fly and then immediately runs the compiled code

---

name: js-dev-tools-console
class: center, middle

# Start Coding!
## Chrome Dev Tools Console
### `command + option + J`
### `Ctrl + Shift + J`

???
[Mastering The Developer Tools Console](http://blog.teamtreehouse.com/mastering-developer-tools-console)

---

class: center

## operators
## values & types
## variables
## conditionals
## loops
## functions
## scope

---

name: js-operators
class:

# Common Operators in JavaScript

### - assignment (`a = 2`)
### - math (`a * 3`)
### - compound assignment (`a += 2`) (same as `a = a + 2`)
### - increment / decrement (`a++`) (similar to `a = a + 1`)
### - equality (`a == b, a != b`)
### - comparison (`a < b, a > b`)
### - logical (`a && b, a || b`)


---

name: js-values-types
class:

# Values & Types
## In programming, different representations for values are called .red-text[types].

### - to do math, use a .red-text[number]
### - to print a value on the screen, use a .red-text[string]
### - to make a decision in a program, use a .red-text[boolean]

### It's common for programming languages to also provide .red-text[arrays, objects, functions], and more.

---

name: js-value-literals
class:

# Value Literals

```javascript
"I am a string";
'I am also a string';

42;

true;
false;

[1, 2, 3]

{
  name: 'Sam',
  age: 21,
  citizen: true
}
```

---

name: js-built-in-types
class: center

# JavaScript Built-in Types

### - null
### - undefined
### - boolean
### - number
### - string
### - object
### - symbol

???

- All built-in types except `object` are called _primitives_.
- Primitives are values, they have no properties.
- Primitives are immutable.

---

name: js-typeof-operator

# typeof operator

```javascript
typeof undefined        === "undefined"; // true
typeof true             === "boolean";   // true
typeof 42               === "number";    // true
typeof "betamore"       === "string";    // true
typeof { age: 21 }      === "object";    // true
typeof Symbol()         === "symbol";    // true
```

```javascript
typeof null             === "object";    // true

```

```javascript
typeof function fn() {} === "function";  // true

```

```javascript
typeof [1, 2, 3]        === 'object';    // true

```

???

- `typeof` inspects the type of the given value, and always returns one of 7 string values
- not an exact 1-to-1 match with the 7 built-in types

---

name: js-two-types-of-values
class: center

.flex[
.l[
# Primitives
### null
### undefined
### boolean
### string
### number
### symbol
]
.m[
# Objects
### Math
### Date
### JSON
### window
### document
### objects you create
]
]

???
[What it really means when people say "Everything in JavaScript is an object."](http://radar.oreilly.com/2014/05/what-it-really-means-when-people-say-everything-in-javascript-is-an-object.html)

---

name: js-special-objects
class: center

# Specialized Objects /
# Object Sub-types
### - Array
### - Function
### - Date
### - Error 
### - RegExp

---

name: js-natives
class: center

# Common Natives / Constructor Counterparts
.flex[
.l[
#### `String()`
#### `Number()`
#### `Boolean()`
#### `Array()`
#### `Object()`
]
.r[
#### `Function()`
#### `RegExp()`
#### `Date()`
#### `Error()`
#### `Symbol()`
]
]

???

- except for `null` and `undefined`, all primitives have object equivalents that wrap around the primitive values
- `new String('abc')` creates a string wrapper object around the primitive value (`'abc'`), never the primitive itself

---

name: js-internal-class

# Internal [[Class]]

```js
Object.prototype.toString.call(() => {}); // 'object Function'
```
```js
Object.prototype.toString.call([1, 2, 3]); // 'object Array'
```
```js
Object.prototype.toString.call(/regex-literal/); // 'object RegExp'
```

```js
Object.prototype.toString.call(null); // 'object Null'
```

```js
Object.prototype.toString.call(undefined); // 'object Undefined'
```

```js
Object.prototype.toString.call('abc'); // 'object String'
```

```js
Object.prototype.toString.call(42); // 'object Number'
```

---

name: js-boxing wrappers

# Boxing Wrappers

```js
const a = 'abc';
a.length; // 3
```

```js
const age = 42;
age.toString(); // '42'
```

### Unboxing

```js
const a = new String('abc');
const b = new Number(42);
const c = new Boolean(true);
```

```js
a.valueOf(); // 'abc'
b.valueOf(); // 42
c.valueOf(); // true
```

---

# Coercion: Converting Between Types

```javascript
var a = "42";
var b = Number( a ); // built-in function, explicit coercion

console.log( a );   // "42"
console.log( b );   // 42
```

## comparing the same value in two different representations (types)
### equivalent, but not exactly the same

```javascript
var a = "99.99";
var b = 99.99;

a == b // "99.99" == 99.99 becomes 99.99 == 99.99, true
```

---

name: js-variables
class:

# Symbolic Containers: Variables
### track a value as it changes over the course of the program (<em>vary</em> over time)

## static typing (type enforcement):

### - declare a variable (container) to hold a specific type (number, sring, etc)

## weak typing (dynamic typing):

### - allows a variable to hold any type of value at any time

---

name: js-dynamic-typing-example

# hold a running value that changes over time (managing state)

```javascript
var amount = 99.99; // no type information in declaration

amount = amount * 2;

// implicitly coerce number value to a string to print it out

console.log( amount ); // 199.98


// convert `amount` to a string, and add "$" to the beginning
// explicit coercion

amount = "$" + String( amount );

console.log( amount );      // "$199.98"
```

#### flexibility of using `amount` variable for each of the 99.99, 199.98, and the "$199.98" values
#### some prefer separate variable (`amountStr`) to hold final "$199.98" representation of value

---

name: js-basics
class:

# The Basics

### - JavaScript is .red-text[case-sensitive] (`myVariable` is NOT the same as `myvariable`)
### - whitespace such as tabs and spaces are ignored unless its part of a string enclosed in quotes

```javascript
// this is a single-line comment
```

```javascript
/* This is a multi-line comment.

Anything in here will be
completely ignored
when the script runs.

*/
```

---

name: js-sample-script

# Sample Script with Comments

```javascript
const today = new Date(); // each individual instruction is a statement
const hourNow = today.getHours(); // each statement starts on a new line
let greeting; // statements end with a semicolon

// statements enclosed in curly braces are known as code blocks

if (hourNow > 18) {
  greeting = "Good evening";
} else if (hourNow > 12) {
  greeting = "Good afternoon";
} else if (hourNow > 0) {
  greeting = "Good morning";
} else {
  greeting = "Welcome";
}

document.write(greeting);
```

---

name: js-fn
class: center, middle

# JavaScript Functions

---

name: js-fn-why
class: center

# Why functions?
## - wrap, bundle, group code for later reuse
## - reduce repetition
## - organize code / application
## - store steps to achieve a specific task
## - primary mechanism of scope

---

name: js-fn-definition
class: middle

> A funciton is generally a named section of code that can be "called" by name, and the code inside it will run each time.

<cite>-- Kyle Simpson</cite>

???

[Kyle Simpson on functions](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch1.md#functions)

---

name: js-fn-definition

# Defining a function

```javascript
function doSomething() {
  console.log('What do you want me to do?');
}

// function declaration
```

```javascript
const doSomething = function() {
  console.log('What do you want me to do?');
}

// anonymous function expression
// in JS, an expression is any reference to a variable or value
// assign a function to a variable just like any other value
```

---

name: js-fn-values

# Functions as Values

```javascript
const doSomething = function() {
  console.log('What do you want me to do?');
}

// anonymous function expression
```

```javascript
element.addEventListener('click', function(event) {
console.log(event.type);
});
```

```javascript
element.addEventListener('click', event => { console.log(event.type) });
```

---

name: js-fn-call

# Invoking, calling, running or executing a function

```javascript
var doSomething = function() {
  console.log('What do you want me to do?');
}

doSomething();
```

```javascript
const doSomething = function foo() {
  console.log('What do you want me to do?');
}

// named function expression
doSomething();
```

---

name: js-fn-effect-value

# Side effect

```javascript
var sayHello = function() {
  console.log('Hello there!');
}

sayHello(); // Hello there!
```

# Producing a value

```javascript
var sayHello = function() {
  return 'Hello there!';
}

sayHello(); // Hello there!

var myReturnValue = sayHello();
```

---

name: js-fn-scope

# Scope

```javascript
var a = 0;
```

```javascript
function one() {
  var a = 1;
  console.log(a);
}
```

```javascript
function two() {
  var a = 2;
  console.log(a);
}
```

```javascript
console.log(a) // 0
one(); // 1
two(); // 2

console.log(a + one() + two()); // ?
```

???

[Kyle Simpson on scope](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch1.md#scope)

---

name: js-fn-arguments

# Passing information to functions

```javascript
var sayHello = function() {
  console.log('Hello there!');
}

sayHello(); // Hello there!
```

```javascript
var sayHelloTo = function(name) {
  console.log('Hello ' + name + '!');
}

sayHelloTo('Jake'); // Hello Jake!
```

---

name: js-fn-arguments-parameters

# Arguments vs. parameters

> Functions are sent arguments; they receive parameters.

<cite>-- Dudley Storey</cite>

```javascript
function square(x) {
  return x * x;
}

square(4); // 16
```

???

[Dudley Storey on functions](http://thenewcode.com/1033/Introduction-to-JavaScript-Functions)

---

name: js-fn-first-class

# "First class" functions
## functions as "first class" values

### - assign a function to a variable
### - store a function in an array or object
### - pass a function to another function
### - return a function from a function


---

name: js-browser
class: center, middle

# JavaScript and the Browser
## "Front-end JavaScript"

---

name: js-embed

# Adding JavaScript to a Page (embedded )

```html
<script>

var parent = document.querySelector("ul");
var myNavitems = document.querySelectorAll('li a');

parent.addEventListener("click", handler, false);

function handler(e) {
  if (e.target !== e.currentTarget) {

    for(i = 0; i < myNavitems.length; i++) {
      myNavitems[i].classList.remove('active');
    }
    e.target.classList.add('active');
   }
  e.stopPropagation();
}

</script>
```

---

name: js-external-script

# Adding JavaScript to a Page

## External scripts

```html
<script src="js/main.js"></script>
```

???

- apply the same script to multiple pages

- each external script requires an additional HTTP request, which impacts performance

---

name: js-script-placement

# Script Placement

### JavaScript runs where it's found in the HTML
### `<script>` element can go anywhere in the document
### Most common places are in `<head>` and just before `</body>`

- Browser encounters a `<script>` element
- stops to load the script
- then checks if it needs to do anything

### This has implications for `<script>` placement, and can affect the loading time of pages.

???

- Don't sprinkle `<script>` elements throughout the HTML document, because that makes them difficult to find and maintain.

---

name: dom-intro

# Intro to the Document Object Model (DOM)

### - browser builds a .red-text[model of the document's structure] and uses it to draw the page on the screen
### - it serves as a structured map to all elements on a page
### - this representation of the document is manipulated via JavaScript
### - we can read from the model and write to it (change it)
### - live data structure: when modified, the page on the screen updates to reflect the changes
### - it's a programming interface (API) for HTML pages

---

name: dom-node-tree
class:

# Document Structure (DOM node tree)
## Visualizing the DOM

![HTML Document Tree](../assets/html-document-tree.gif)

---

# Document Structure (nested set of boxes)

.float-left[

```html
<!doctype html>
<html>
  <head>
    <title>My home page</title>
  </head>
  <body>
    <h1>My home page</h1>
    <p>Hello, I am Marijn and this is ...</p>
    <p>I also wrote a book! Read it
      <a href="#">here</a>.</p>
  </body>
</html>
```

]

.float-right[
![HTML Document Tree](../assets/html-boxes.svg)
]

???
[Eloquent JavaScript: Chapter 13: The Document Object Model](http://eloquentjavascript.net/13_dom.html)

---

# Data Structure (nested set of boxes)

.float-left[
![HTML Document Tree](../assets/html-boxes.svg)
]

.float-right[
### - each box is an object we can interact with
### - what HTML tag? does it contain other boxes? which ones?
### - global variable `document` gives us access to objects
### - `document.documentElement` (html tag)
### - `document.head` (head tag)
### - `document.body` (body tag)
]

---

name: dom-crawling

# Traversing the DOM

### DOM is a collection of nodes
- element nodes
- attribute nodes
- text nodes

```html
<p id="betamore">
  Real web designers <a href="/code">write code</a>. Always have, always will.
</p>
```

```javascript
var elementNode = document.getElementById("betamore");

var attributeNode = elementNode.getAttribute("href");

var textNode = elementNode.innerHTML;
```
