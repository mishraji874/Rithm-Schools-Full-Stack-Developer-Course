# Function Parameters and Scope

## Function Parameters

So far our functions have not been taking in any input; they simply are returning an output. So when would we want an input to our functions? Let’s imagine we want to calculate the sum of two numbers. If our numbers are 5 and 5, well, that’s easy.

```
5 + 5; // 10
```

But what happens if we don’t know what our numbers are? How could we possibly do this? Better yet, what if we want to do 4 + 6, and 2 + 8 and 7 + 3…we would have to start writing a whole bunch of code that’s does basically the same function. This is a great example of when we want to add inputs and use a function. Inputs to a function are called parameters or arguments.

So what does a function look like with parameters? Let’s write a function called add that takes in two parameters – `number1` and `number2` – and returns their sum.

```javascript
function add(number1, number2){
    return number1 + number2;
}
```

Now our add function will work for any two numbers that we want to add together. It’s important to note that the name of the parameters, `number1` and `number2`, are arbitrary names that we have chosen. If we change the names of the parameters to a and b, the function would do exactly the same thing:

```javascript
// This function will do the same thing as our previous function
function add(a, b){
    return a + b;
}
```

Now that we have defined a function with parameters, let’s see how we invoke that function

```javascript
add(4, 6); // returns 10
add(2, 8); // returns 10
add(7, 1); // returns 8
```

In the example above, we invoked the add function with parameters. A parameter can be a literal number like we have above, or we could even use variables:

```javascript
let num1 = 5;
let num2 = 8;
add(num1, num2);  // returns 13
```

It is important to understand that the variable names we are using when we invoke the function are not related at all to the variable names we have defined inside of the function. The values of `num1` and `num2` are being copied into the parameters `number1` and `number2` that are defined in the function.

## Function Scope

Now that we have an idea of what functions do, let’s talk about what happens when we define variables inside of functions. To do that, we first need to define what `scope` is.

MDN defines `scope` as “The context in which values and expressions are ‘visible,’ or can be referenced”. In JavaScript (before ES2015, which is where we will start), there are only 2 kinds of scope: global scope and function scope.

The important takeaways here are

1. **all variables that are defined outside of functions (and inside of functions without the let keyword) are declared in the global scope, and**
2. **all variables defined inside of functions can only be accessed by those functions (and any inner functions).**

Let’s see an example.

```javascript
let globalvariable = "I live in the global scope";

function makeNewScope(){
    let functionScopevariable = "I live in the scope of the makeNewScope function";
}

globalvariable; // "I live in the global scope";
makeNewScope(); // maybe this will define the functionScopevariable...

functionScopevariable; // This gives us an error! To be specific, a ReferenceError because the functionScopevariable is not defined.
```

What happens when we remove the `let` keyword?

```javascript
// Since this variable declaration is in the global scope, it will
// be a global variable with or without the let keyword.  It is a best
// practice to always use the let keyword though.
globalvariable = "I live in the global scope";

function makeNewScope(){
    // You do not want to do this in practice.  You should
    // always define your variables with the let keyword.
    functionScopevariable = "What happens now?";
}

globalvariable; // "I live in the global scope"
makeNewScope(); // now this will define the functionScopevariable!

// The value of the variable will be "What happens now?"
functionScopevariable;
```

If we omit the `let` keyword inside of a function, we actually declare that variable in the global scope. While this may seem like the way to go, this is not best practice. If we need to change some variable in a function, we should at least declare it in the global scope and assign it in a function so that our code is more readable.

```javascript
let globalvariable = "I live in the global scope";

// we are just declaring the variable now; its value will be set to undefined.
let globalvariableToBeChanged;

function makeNewScope() {
    // Here we are assigning the value "What happens now" to the
    // globalvariableToBeChanged variable.
    globalvariableToBeChanged = "Undefined no more!";
}

globalvariable; // "I live in the global scope"
makeNewScope(); // now this will assign a new value to the globalvariableToBeChanged!

// The value of globalvariableToBeChanged is "Undefined no more!"
globalvariableToBeChanged;
```

## You’ve seen scope already!

If you remember back in the section on `if` and `else` statements, we mentioned that if you declare a variable inside of a block using `let` or `const`, you can not access it outside of that block. This is another kind of scope that is called `block` scope and when you use `let` or `const` inside of a block (`if`/`else` statements and `for` and `while` loops), that variable is only accessible inside of the block.