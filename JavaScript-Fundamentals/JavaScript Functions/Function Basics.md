# Function Basics

## What is a function

A function is a repeatable process of procedure. A real world analogy of a function is the brew button on a coffee machine. The coffee machine has inputs (hot water, and coffee grounds), and outputs (hot coffee). When you press the button to brew a pot of coffee, you are starting a process that should return an expected output to you. The same thing is true in programming. A function takes a set of variables as inputs and returns a value as an output.

We have already seen many functions in action. For example, in the array chapter, we learned about `push` and `pop`. These are both functions that operate on an array. Consider the following example:

```javascript
let arr = [5,4,3,2,1];
let poppedVal = arr.pop();
console.log(arr);
console.log(poppedVal);
```

In the example, we are using the pop function. It takes no inputs, and it returns a value which is the last item in the array that has been removed from the array. When you run the code in your console, you’ll see the array is now `[5,4,3,2]` and the value of `poppedVal` is `1`.

## Declaring Functions

So far we have only used functions, but to be a knowledgeable JavaScript programmer, we need to learn to write our own functions as well. There are multiple ways to write functions in JavaScript. We will cover the differences in more detail later. For now, let’s start with one way: a function declaration.

In general, we declare a function in the following way:

```javascript 
function anyNameYouWantForTheFunction() {
    // As many lines of code as you want
}
```

In general, this type of function syntax consists of four parts:

- The `function` keyword,
- The name of the function (in this case, `anyNameYouWantForTheFunction`),
- Any parameters for the function (we’ll ignore this for now, but parameters will go inside of the parentheses after the function name),
- The function body (the code for the function, which lives inside of the curly braces).

It might seem silly, but it would be good to practice typing this syntax out a few times. You’ll be writing functions constantly in JavaScript, so the syntax is something you should commit to muscle memory. Try typing these out:

```javascript
function myFunction() {
}

function myOtherFunction() {
}

function yetAnotherFunction() {
}

function okayIGetItThisIsTheSyntaxForFunctions() {
}
```

The functions above aren’t very interesting, because none of them have a function body. Let’s look at an example of a function that actually does something:

```javascript
// this is called the function definition - we are ONLY defining the function here
function firstFunction(){
    console.log("I just wrote my first function!");
}
```

Now we have declared a function called `firstFunction`, but we have not used the function yet. To execute the code within the function, we must invoke the function. A function is invoked by adding a () after the name of the function:

```javascript
// to call or invoke the function
firstFunction();
```

If you run this code in the Chrome console, you will see the output is “I just wrote my first function” and on the next line, `undefined`. Next, we’ll learn where the `undefined` is coming from.

## Returning Values From Functions

In JavaScript, if we do not specifically tell the function to `return` something, it will return `undefined` when it is finished executing. So how do we tell a function to return something? We use the `return` keyword!

```javascript
// this is called the function definition -
// we are ONLY defining the function here
function firstFunction(){
    return "I just wrote my first function!";
}

// to call or invoke the function
firstFunction(); // now we don't see undefined anymore!
```

Now our function is returning “I just wrote my first function”. To capture that string, let’s use a variable:

```javascript
let returnValue = firstFunction();
console.log(returnValue);
```

Now in the console, you should see “I just wrote my first function”. That is the value that was returned from our function call and that is now saved in the `returnValue` variable.

Remember, the `return` keyword can **ONLY** be used inside of a function. let’s take a look at another example.

```javascript
function secondFunction(){
    return "Hello";
    return "Goodbye";
}

secondFunction(); // "Hello"
```

We see from this example that the **return** keyword can only be executed once in a function. Once it is executed, the function is complete and no other lines of code will be executed.

## Conditional Logic With Return Statements

Now that we have an idea of how functions work, let’s explore a previous topic and see how we can refactor some boolean logic. Let’s imagine we want to write a function that returns true if a random number is over .5 – otherwise the function should return false. Here is one way we can write it

```javascript
function isOverPointFive(){
    if (Math.random() > .5){
        return true;
    } else {
        return false;
    }
}
```

This code will work just fine, but remember, the return keyword exits from a function. So if the random number is greater than .5 we will exit the function early and never reach the else condition. So we don’t even need the “else” condition! We can refactor our code to look like this:

```javascript
function isOverPointFive(){
    if(Math.random() > .5){
        return true;
    }
    return false;
}
```

Much better! If the number is greater than .5, return true and exit the function. Otherwise just return false.

Finally if we wanted to be really fancy – we could use a ternary operator!

```javascript
function isOverPointFive(){
    return Math.random() > .5 ? true : false;
}
```

Simplifying it even further, we can take advantage of the fact that `Math.random() > .5` returns `true` or `false`. So we don’t actually need the ternary operator:

```javascript
function isOverPointFive(){
    return Math.random() > .5;
}
```