# Higher Order Functions

## Anonymous Functions As Parameters

We can even pass an anonymous function as a parameter!

```javascript
sendMessage("Hello World", function(message) {
    // message refers to the string "Hello World"
    console.log(message + " from a callback function!");
});  // Hello World from a callback function!
```

The previous example is equivalent to doing the following:

```javascript
let myFunction = function(message) {
    // message refers to the string "Hello World"
    console.log(message + " from a callback function!");
};

sendMessage("Hello World", myFunction);
```

However, when programming in JavaScript, you will see anonymous functions being passed as parameters very often, so it’s good to get used to it now.

## Why Higher Order Functions?

One advantage of higher order functions is code reuse. In our previous examples we would have had to do a lot of work to get the same code. Higher order functions allow us to avoid writing seperate functions like this:

```javascript
function sendMessageWithConsoleLog(message) {
    return console.log(message);
}

function sendMessageWithAlert(message) {
    return alert(message);
}

function promptWithMessage(message) {
    return prompt(message);
}

function confirmWithMessage(message) {
    return confirm(message);
}

function sendMessageWithFromCallback(message) { 
    return console.log(message + " from a callback function!");
}
```

Instead of writing five different functions, we can just write one and pass another function to it! We call a function that is passed as an argument to a higher order function a **callback**. The concept of callbacks and higher order functions can be a little tricky to understand at first, so let’s take a look at some more examples.

## Callback Functions

To reiterate, a callback function is the function that is being passed to a higher order function and that callback function will be invoked within the higher order function. In our `sendMessage` example, `sendMessage` is the higher order function and fn is the callback function.

Now, let’s see another use case for higher order functions.

```javascript
function add(a,b) {
    return a+b;
}

function subtract(a,b) {
    return a-b;
}

function math(a,b,callback) {
    return callback(a,b);
}

math(1, 4, add); // returns 5
math(5, 5, subtract); // returns 0

/*
as we start making additional functions that perform operations on
two numbers we can pass them to the math function. So if we make a
divide or multiply function we can call all of them just using the
math function.
*/
```

Let’s take a look at another example – say we want to build a function that accepts an array and returns a new array with only even numbers. We’ll call this function `onlyEvens`

```javascript
function onlyEvens(numbers) {
  let evens = [];
  for (let num of numbers) {
    if (num % 2 === 0) {
      evens.push(num);
    }
  }
  return evens;
}
```

Easy enough! Now, our boss comes back and says, “let’s make this return only odd numbers”. So what can we do? One option is to write another function that looks like this

```javascript
function onlyOdds(numbers) {
  let odds = [];
  for (let num of numbers) {
    if (num % 2 !== 0) {
      odds.push(num);
    }
  }
  return odds;
}
```

Our boss might be happy for the moment, but this is not going to work once we start adding additional conditions. What happens when we want numbers divisible by three? Or numbers that are odd and also prime numbers? Instead of writing a different function for each condition, we’ll add an additional parameter to this function which is a function! We’re going to run our callback function for each value in the array and if the result of that function is truth-y, we will push that value into the array. **This does assume that the person who calls our function understands that the callback has to return true. Instead of us as the writer of the function handling what the condition should be, we are letting the caller of the function determine what the condition should be.**

This might feel a bit strange at first, so let’s first explore the syntax.

```javascript
function filter(numbers, callback) {
  let filteredValues = [];
  for (let num of numbers) {
    let result = callback(num); // we're going to run a function for each value in the array
    // we're then going to see if the result of the callback function is truthy
    if (result) {
      // if so, take the value we are iterating over and push it into the filteredValues array
      filteredValues.push(num);
    }
  }
  return filteredValues;
}
```

So how do we use this function? Let’s see some examples:

```javascript
let numbers = [1,2,3,4,5];

filter(numbers, function (num) {
  console.log(num); // this will refer to each number -> (1,2,3,4,5)
  return num < 3;
}); // returns [1,2]

filter(numbers, function (num) {
  return num % 2 === 0;
}); // returns [2,4]
```

Copy and paste this code, put it in the Chrome Console and play around with some different examples and conditions!