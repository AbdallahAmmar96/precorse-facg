# First-Class & Higher-Order functions

## First-Class Functions

### What is first-class functions?

A programming language is said to have First-class functions when functions in that language are treated as a value (like any other variable). For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable.

### First-Class functions in javascript

Functions in JavaScript are treated as **objects**. They have the type `Object`, they can be assigned as the value of a variable, and they can be passed and returned just like any other reference variable. Which means they can be:

- stored in a variable, object, or array
- passed as an argument to a function
- returned from a function

### Storing a function

Functions can be stored in three ways:

- stored in a variable :

```javascript
let fn = function() {};
```

- stored in an object :

```javascript
let obj = { doSomething: function() {} };
```

- stored in an array :

```javascript
arr.push(function() {});
```

## Higher-Order Functions

### What are higher-order functions?

Higher order functions are functions that operate on other functions, either by taking them as arguments or by returning them. In simple words, A Higher-Order function is a function that receives a function as an argument or returns the function as output.

### Examples of built in higher-order functions in javascript

- `Array.prototype.map`
- `Array.prototype.filter`
- `Array.prototype.forEach`
- `Array.prototype.reduce`
- `Array.prototype.find`

### Example of a higher-order function

- Passing a function as an argument

```javascript
function doWithLoading(fn) {
  console.log("start loading");
  fn();
  console.log("end loading");
  return returnValue;
}
function process() {
  console.log("loading ...");
}
doWithLoading(process);
// start loading
// loading ...
// end loading
```

- Returning a function

```javascript
function doWithLoading() {
  console.log("start loading");
  return function() {
    console.log("end loading");
  };
}

const fn = doWithLoading(); // start loading
console.log("loading ..."); // loading ...
fn(); // end loading
```
