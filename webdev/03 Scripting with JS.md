# Lesson 3: Scripting with JS

HTML and CSS are great, and using our knowledge we already know how to create a basic static website.

However, the web nowadays is a complex space, static websites are simply not enough.

We need to find a way to make websites interactive, in order to add actual functionality.

HTML and CSS is ultimately a tool that you can use to control what is displayed to the user. The actual logic of your
website is controlled with code.

On the web, the standard scripting language is called JavaScript (not to be confused with Java).

## JavaScript basics

To put it simply, JavaScript adds interactivity to your website. It is versatile and beginner friendly.

It can even be used outside of websites, using a JS runtime such as Node.js, allowing you to create and run
programs natively on your computer.

JavaScript files are denoted with a `.js` extension.

### Adding JavaScript to your website

To add JavaScript to your website, we use a `<script></script>` tag.

Code can be defined inline, as so:

```html
<!DOCTYPE html>
<html>
  <head>
    ...
    <link rel="stylesheet" href="index.css" />
    <script defer>
      alert("Hello, world!");
    </script>
  </head>
  <body></body>
</html>
```

Or added from a separate file:

```html
<!DOCTYPE html>
<html>
  <head>
    ...
    <link rel="stylesheet" href="index.css" />
    <script src="index.js" defer></script>
  </head>
  <body></body>
</html>
```

To get started, create an `index.js` file in your sandbox. Append the following code to your `<head>` element:

```html
<script src="index.js" defer></script>
```

The `src` (source) property indicates where the JS file is located. The `defer` keyword simply delays the execution
of the JavaScript code until the website is fully loaded. This prevents errors from occurring due to elements not yet
existing in the DOM (document object model) when the code runs.

Now, turn to your index.js file.

### Hello World!

There are two ways of displaying text in JavaScript, either through an alert window or through the console.

If you have used a programming language before, you may be familiar with the **developer console**.

To output text to the console in JS, we simply use the `console.log()` function:

```js
console.log("Hello, world!");
```

Alternatively, the `alert()` function can be used to create a pop-up window. This can be useful if we need to
notify the user of something important:

```js
alert("Hello, world");
```

However, most of the time, `console.log` is more convenient for output purposes.

### Variables

There are three ways to declare a variable in JavaScript:

- Using `let`
- Using `const`
- Using `var`

Since 2015, the standard way of declaring a variable is as follows:

```js
let n = 1;
```

If we want to define a variable where the value does not change, we can use the `const` keyword:

```js
const n = 1;
```

In older JS code, you might see the `var` keyword. This should not be used nowadays, use `let` instead:

```js
var n = 1;
```

### Data types

The basic data types in JavaScript are:

- string `"some text"`
- number `5`
- boolean `true`, `false`
- null `null`
- array `[1, 2, 3, 4]`
- object `{firstName: "John", lastName:"Doe"}`

Objects in JavaScript are similar to dictionaries in Python.

Their syntax is very similar to Python.

### Operators

We can use operators in JavaScript to manipulate data.

Maths (a and b are numbers):

- `a + b` add
- `a - b` subtract
- `a * b` multiply
- `a / b` divide
- `a ** b` raise to power

Logical (a and b are booleans):

- `a && b` a AND b
- `a || b` a OR b
- `!a` NOT a

Equality (outputs boolean)

- `a == b` equality
- `a != b` inequality

JavaScript has weak types, meaning that types are not strictly enforced.

For example, in this example:

```js
console.log(5 == "5");
```

The value `true` is printed. In JS, numbers are considered equal to their string representation. Although it might seem useful,
this behaviour is often undesirable and leads to errors in code.

Therefore, it is recommended that the strict typing equality operators are used instead.

These use a similar syntax, but with an additional equals sign:

- `===` is (strictly) equal to
- `!==` is (strictly) not equal to

```js
console.log(5 === "5");
```

As you can see in this example, it prints `false` as the values themselves do not match.

### Code constructs

#### If statements

The `if/else` statement is used to execute code based on a condition.

```js
let age = 18;

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
```

In this example, the text "You are an adult." is outputted to the console.

#### For loops

A `for` loop is used to repeat a block of code a certain number of times.

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

In this example, the for loop has 3 separate parts:

- A variable called `i` is declared, with its value set to 0.
- The loop condition is declared - `i < 5` - the loop will keep running while this criteria is met
- The iteration action is defined - `i++` - this tells the loop to increase `i` by 1 every iteration

Overall, this runs the code inside the loop a total of 5 times. This can be altered by changing the loop condition.

#### While loops

A `while` loop is designed to continue running a block of code while a condition is `true`.

```js
const correctPassword = "abc123";
let password = "";

while (password !== correctPassword) {
  password = prompt("Enter your password:");
}

console.log("Access granted");
```

This loop will continue on forever until the correct password is entered.

#### Functions

Functions are reusable blocks of code that perform a specific task.

A function can be declared using the `function` keyword:

```js
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet("Alice"));
```

This function takes a `name` parameter and returns a greeting message. It will print "Hello, Alice!" to the console.

A function can also be defined as an expression:

```js
const add = function (a, b) {
  return a + b;
};

console.log(add(3, 4));
```

This is extremely useful, as we can pass functions as arguments to other functions. This is called a "callback function".
This will be very useful later on, when we discuss adding event listeners to our website.

This function expression can be simplified, using "arrow functions":

```js
const add = (a, b) => a + b;
console.log(add(3, 4));
```

Arrow functions provide a shorter syntax for writing functions.

### Making a website interactive

JS is designed to integrate with HTML, allowing us to detect events and change elements on the web page.

### Click events

An example of this is reacting to when a user clicks a button.

First of all, we need to add a button element to our HTML:

```html
<button id="button">Click me!<button></button></button>
```

As you can see, we added an `id` to the button. The `id` property is used to uniquely identify a single element on the page.
No two elements on the page are allowed to have the same `id`.

This allows us to select the element in our JS code, using the `document.getElementById()` function:

```js
const button = document.getElementById("button");
```

Now that we have selected the button, we can attach an event listener to it.

```js
button.addEventListener("click", () => {
  console.log("Clicked!");
});
```

Every time you click the button, you should see the text appear in the console window.

### Manipulating elements

We can edit an element by selecting it and changing its properties. Consider the following example:

**index.html**

```html
<p id="counter">0</p>
<button id="button">Add</button>
```

**index.js**

```js
const counter = document.getElementById("counter");
const button = document.getElementById("button");
let n = 0;
button.addEventListener("click", () => {
  n++;
  counter.innerText = n;
});
```

JavaScript allows us to edit the value of the `p` tag in response to the user clicking on the button.
