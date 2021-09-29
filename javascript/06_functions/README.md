# Functions

Our programs will get more and more complicated as we introduce new concepts and we will find ourselves repeating some chunks of code. This is widely considered to be a Bad Thing, as programmers are generally quite lazy and don't like doing things twice if it can be avoided. We often talk about **DRY** code, where DRY stands for **D**on't **R**epeat **Y**ourself. If we want to keep our code DRY we're going to need some sort of tool to help avoid repetition, which is where functions come into play.

## What is a function?

A **function** is a block of code which performs a specific task. We have already seen code blocks: we use them to define what should happen when conditions are satisfied in an if-statement and we use them to define how we iterated through an array in a for loop. The important difference here is that functions can used anywhere in our programs.

We've been doing this a lot already, we just may not have realised. Think back to the first lesson and the way in which we capitalised a String. 

```js
// node

"Hello World!".toUpperCase();

// "HELLO WORLD!"
```

When we run this program we **call**, or **invoke**, the function `toUpperCase`. We do this by including the parentheses `()` after the name of the function; if we omit the brackets the interpreter will simply tell us that `toUpperCase` is a function. We didn't have to write the code to capitalise our String, we just needed to call it and let the interpreter do the rest. Writing our own functions will enable us to do the same with blocks of code we write.

## Types of Function

Unlike many other programming languges, in JavaScript there are multiple ways in which we can define a function. There is no sinlge "best" way of doing it, but each one has it's own characteristics to be aware of and some will be better-suited than others to certain situations. Create a file to work in and we will see an example of each.

```sh
touch functions.js
```

### Named Functions

The first way to declare a function is to use a **named function**. We use the keyword `function` to indicate that we are declaring a function, then assign a name following the same conventions as a variable. We place parentheses after the function name, then a code block in which we palce the code we want the function to execute. Let's start with a simple example where we print a String to the console.

```js
// functions.js

function greet(){
	console.log("Good morning!");
}

greet();
```

We have called our function `greet` and when we call it we print the String "Good morning!" to the terminal. This will be useful if we want to say good morning a lot, but it only represents a small part of what we can do with functions.

Let's say we want to be a bit more specific with our greeting. We could define a different function to say "good afternoon" or "good evening" but we'd be repeating a lot of code, which wouldn't be very DRY. Instead we can modify our function so that it's behaviour depends on information we give it when we call it.

```js
// functions.js

function greet(timeOfDay){
	console.log(`Good ${timeOfDay}!`);
}

greet("morning");
greet("afternoon");
```
We have added `timeOfDay` to the parentheses in our function definition. This is known as a **parameter** and works in a similar way to the temporary variables we declare in a loop. When we call the function we can provide a value in the parentheses which is then assigned to `timeOfDay` when the code is executed. It only exists inside the function and has block scope. A function can have multiple parameters, if we need it to.

```js
// functions.js

function greet(timeOfDay, name){
	console.log(`Good ${timeOfDay}, ${name}!`);
}

greet("morning", "Alice");
greet("afternoon", "Bob");
```

The values we pass in to the function are known as **arguments**. Unlike other programming languages, a JavaScript function will still run if we provide the incorrect number of arguments. Any extras will be ignored, while any missing will be `undefined` inside the function.

```js
greet("morning", "Alice", "extra argument");
// "Good morning, Alice!"

greet("afternoon");
// "Good afternoon, undefined!"
```




# TODO

- return values
- hoisting
- anon. functions
- arrow functions