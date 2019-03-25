# **Javascript Scopes**

## Scope :

The current context of execution. The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.

### In JavaScript only functions create scopes and there are **two main types of scopes**:

- Global scope

```javascript
// global scope
var a = 1;

function one() {
  alert(a); // alerts '1'
}
```

- Local scope

```javascript
// global scope
var a = 1;

function two(a) {
  // passing (a) makes it local scope
  alert(a); // alerts the given argument, not the global value of '1'
}

// local scope again
function three() {
  var a = 3;
  alert(a); // alerts '3'
}
```

![pic](https://www.datchley.name/content/images/2015/08/js-es5-scope-2.png)

### **ES6's Let & Const**

ES6 introduced a new type of scopes with both the let and the const keywords which is **block scope**, and with that any block will create it's own scope which means variables only declared with **let** or **const** can be accessed only within their block of declaration (are block scoped).

```javascript
function four() {
  if (true) {
    let a = 4;
    alert(a); // will alert 4
  }

  alert(a); /* will cause an error because a can only be accessed within it's block of declaration, 
              (a isn't defined/delared in function four scope)*/
}
```

```javascript
let a = 1;
function four() {
  if (true) {
    let a = 4;
    alert(a); // will alert 4
  }

  alert(a); // will alert 1
}
```

### **Hoisting**

Hoisting was thought up as a general way of thinking about how execution contexts (specifically the creation and execution phases) work in JavaScript.

Conceptually, for example, a strict definition of hoisting suggests that variable and function declarations are physically moved to the top of your code, but this is not in fact what happens. Instead, the variable and function declarations are put into memory during the compile phase, but stay exactly where you typed them in your code.

But, for a much simpler way to understand hoisting in javascript it can be decriped as follows :

```javascript
console.log(x); // will log 'undefiend'
var x = 5; // declaration & initialised
console.log(x); // will log '5'
```

The code above can be simplified as :

```javascript
var x; // declaration
console.log(x); // ==> undefiend
x = 5; // initialised
console.log(x); // ==> 5
```

### **Closure**

#### Take a look at this code and guess what will happen :

```javascript
function foo() {
  var x = 5;
  console.log(x);
  return;
}
foo(); // #1
console.log(x); // #2
```

> Can you explain your answers?

#### Now consider this code :

```javascript
function foo() {
  var x = 5;
  console.log(x);
  return function() {
    console.log(x);
  };
}
var fn = foo(); // #1
fn(); // #2
```

> Can you explain what happened?

What happened in the previous example is called a closure, a closure is the combination of a function and the lexical environment within which that function was declared. This environment consists of any local variables that were in-scope at the time the closure was created
