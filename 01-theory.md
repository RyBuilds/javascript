# JavaScript

## What is JavaScript?

**Simple:** JavaScript is a high-level, object-orientated, multi-paradigm programming language.

**Less Simple:** JavaScript is a `high-level` `prototype based object-oriented` `multi-paradigm` `interpreted or just-in-time compiled` `dynamic` `single-threaded` `garbage-collected` programming language with `first-class functions` and a non-blocking `event loop concurrency model`.

### High-Level

Every program needs hardware resources such as a memory and a CPU to do its work. Low-level languages (C) require you to manually manage these resources, for example asking the computer for memory to create a new variable. High-level languages (JS, Python) have abstractions which take all of that work away from us. This makes a language easier to learn and use, although these programs will never be as fast or optimised as those written in C. One powerful tool which takes memory management away from us is `Garbage Collection`.

### Garbage-Collected

Garbage collection is an algorithm within the JavaScript engine which automatically removes old and used objects from the computer memory, ensuring it doesnt get clogged up with unnecessary stuff.

### Interpreted or Just-In-Time Compiled

A computers processor only understands 0's and 1's, machine code. Since this isn't practical, we write human readable code which is an abstraction over machine code. This code eventually needs to be translated into machine code and that step can be either compiling or interpreting. This step is necessary in every single programming language - in the case of JavaScript; this happens inside the JavaScript engine.

### Multi-Paradigm

JavaScript is a multi-paradigm language, which adds to its popularity. A paradigm is an approach and overall mindset of structuring our code, which influences the coding style and technique in a project. Paradigms can also be classified as Imperative (what the program does without explicitly specifying its control flow) or Declerative (how the program should do something by explicitly specifying each instruction step-by-step).

Three popular paradigms are:
.._ Procedural programming - logical step-by-step instructions
.._ Object-oriented programming (OOP)
..- Functional programming (FP)

Most languages are one or the other, but JavaScript does all of it - its really flexible and versatile, we can do whatever we want with it.

### Prototype-Based Object-Oriented

Almost everything in JavaScript is an object, except primitive values; numbers, strings, booleans, undefined, null, symbols and bigints. Arrays are just objects, and `prototypal inheritance` is the reason we can use .push on an array. We create arrays from an array blueprint/template called the `prototype`, which contains all the array methods. The arrays we create in our code then inherit these methods from the template, which enables us to use them on the arrays.

### First-Class Functions

Functions are treated like regular variables and so we can pass functions into other functions, and return functions from functions. This enables a lot of powerful techniques to be used, and allows for functional programming - one of the aforementioned paradigms.

### Dynamic

JavaScript is dynamically typed, we dont assign data types to variables - they only become known when the JavaScript engine executes our code. The type of variable can easily be changed as we reassign variables. In most other programming languages, you have to manually assign types to variables, which prevents a lot of bugs from happening - TypeScript enables the use of types with JavaScript.

### Single-Thread and the Non-Blocking Event Loop Concurrency Model

A `concurrency model` is how the JavaScript engine handles multiple tasks happening at the same time, and a `thread` is a set of instructions that is executed in the computers CPU - its where our code is executed in the machines processor.

JavaScript runs in a `single-thread` which can only handle one thing at a time. If there's a long-running task like fetching data from a remote server, it'd block the single-thread where the code is running - and so we need a `non-blocking` way of handling multiple things at the same time. By using an `event loop`, JavaScript takes long running tasks, executes them in the background, and then puts them back in the main thread once they're finished. This is JavaScripts non-blocking event loop concurrency model with a single thread - simplified.
