# What is JavaScript?

**Simple:** JavaScript is a high-level, object-orientated, multi-paradigm programming language.

**Less Simple:** JavaScript is a `high-level` `prototype based object-oriented` `multi-paradigm` `interpreted or just-in-time compiled` `dynamic` `single-threaded` `garbage-collected` programming language with `first-class functions` and a `non-blocking event loop concurrency model`.

## What does all of this mean...

<details>
<summary>High-Level</summary>
Every program needs hardware resources such as memory and a CPU to do its work. Low-level languages (C) require you to manually manage these resources, for example asking the computer for memory to create a new variable. High-level languages (JS, Python) have abstractions which take all of that work away from us. This makes a language easier to learn and use, although these programs will never be as fast or optimised as those written in C. One powerful tool which takes memory management away from us is `Garbage Collection`.
</details>

<details>
<summary>Garbage-Collected</summary>
Garbage collection is an algorithm within the JavaScript engine which automatically removes old and used objects from the computer memory, ensuring it doesnt get clogged up with unnecessary stuff.
</details>

<details>
<summary>Interpreted or Just-in-Time Compiled</summary>
A computers processor only understands 0's and 1's, machine code. Since this isn't practical, we write human readable code which is an abstraction over machine code. This code eventually needs to be translated into machine code and that step can be either compiling or interpreting. This step is necessary in every single programming language - in the case of JavaScript; this happens inside the JavaScript engine.
</details>

<details>
<summary>Multi-Paradigm</summary>
JavaScript is a multi-paradigm language, which adds to its popularity. A paradigm is an approach and overall mindset of structuring our code, which influences the coding style and technique in a project. Paradigms can also be classified as Imperative (what the program does without explicitly specifying its control flow) or Declerative (how the program should do something by explicitly specifying each instruction step-by-step). Most languages are one or the other, but three popular paradigms are:

- Procedural programming - logical step-by-step instructions
- Object-oriented programming (OOP)
- Functional programming (FP)
</details>

<details>
<summary>Prototype-Based Object-Oriented</summary>
Almost everything in JavaScript is an object, except primitive values; numbers, strings, booleans, undefined, null, symbols and bigints. Arrays are just objects, and `prototypal inheritance` is the reason we can use `.push` on an array. We create arrays from an array blueprint/template called the `prototype`, which contains all the array methods. The arrays we create in our code then inherit these methods from the template, which enables us to use them on the arrays.
</details>

<details>
<summary>First-Class Functions</summary>
Functions are treated like regular variables and so we can pass functions into other functions, and return functions from functions. This enables a lot of powerful techniques to be used, and allows for functional programming - one of the aforementioned paradigms.
</details>

<details>
<summary>Dynamic</summary>
JavaScript is dynamically typed, we dont assign data types to variables - they only become known when the JavaScript engine executes our code. The type of variable can easily be changed as we reassign variables. In most other programming languages, you have to manually assign types to variables, which prevents a lot of bugs from happening - TypeScript enables the use of types with JavaScript.
</details>

<details>
<summary>Non-Blocking Event Loop Concurrency Model with a Single-Thread</summary>
A `concurrency model` is how the JavaScript engine handles multiple tasks happening at the same time, and a `thread` is a set of instructions that is executed in the computers CPU - its where our code is executed in the machines processor.

JavaScript runs in a `single-thread` which can only handle one thing at a time. If there's a long-running task like fetching data from a remote server, it'd block the single-thread where the code is running - and so we need a `non-blocking` way of handling multiple things at the same time. By using an `event loop`, JavaScript takes long running tasks, executes them in the background, and then puts them back in the main thread once they're finished. This is JavaScripts non-blocking event loop concurrency model with a single thread - simplified.

</details>

---

# The JavaScript Engine and Runtime

A `JavaScript engine` is a program which executes JavaScript code. Every browser has its own JavaScript engine, but Google's V8 engine which powers Google Chrome and Node.js is the most well known. Any JavaScript engine always contains a `callstack` and a `heap`. A callstack is where our code is actually executed using `execution contexts`, and a heap is an unstructured memory pool which stores all the objects our application needs. This explains where our code is executed.

## How is Code Compiled?

Every program needs to be converted into machine code since computer processors only understands 0's and 1's, and this can happen using compilation or interpretation.

### Compilation

Compilation is when entire source code is converted into machine code at once, and written to a binary file (portable file) that can be executed by any computer. It's a two step process; first the machine code is built, then it's executed in the CPU. Execution can happen way after the compilation; any application being used right now had been compiled before, and its being executed way after its compilation.

**Source code** &rarr; Step 1: Compilation &rarr; **Portable file:** Machine code &rarr; Step 2: Execution &rarr; Program running

### Interpretation

Interpretation is when an interpreter runs through the source code and executes it line by line. There's no two-step process like in compilation, the code is read and executed at the same time right before it's executed, not ahead of time. For this reason, it's much slower than compiled languages.

**Source code** &rarr; Step 1: Execution line by line &rarr; Program running

### Just-in-Time Compilation

Just-in-time compilation is when entire code is converted into machine code at once, and executed immediately. This is a combination of compilation and interpretation; there are still the two steps of regular ahead-of-time compilation, but there is no portable file to execute, and execution happens immediately after compilation.

**Source code** &rarr; Step 1: Compilation &rarr; Machine code &rarr; Step 2: Immediate execution &rarr; Program running

## How JavaScript Engines Compile Source Code

As a piece of code enters the JavaScript engine, the first step is to parse the code; read the code. During the parsing process, the code is passed into a data structure called the `Abstract Syntax Tree (AST)`. This works first by splitting up each line of code into pieces that are meaningful to the language like const or function keywords, and then saving all of these pieces into the tree in a structured way. This step also checks if there are any syntax errors, and the resulting tree will be used later to generate the machine code. The next step is compilation, which takes the generated AST and compiles it into machine code. This machine code then gets executed right away - and this happens in the callstack.

Modern JavaScript have clever optimisation strategies; they create a very unoptimised version of machine code in the beginning just so it can start executing as fast as possible. Then in the background, this code is being optimised and recompiled during the already running program execution, which can be done multiple times, and after each optimisation. The unoptimised code is simply swapped for the new and more optimised code without ever stopping execution. This process is what makes modern engines so fast. All this parsing, compilation and optimisation happens in some special threads inside the engine which we cannot access from our code, so completely seperate to the main thread running in the callstack and executing our own code.
