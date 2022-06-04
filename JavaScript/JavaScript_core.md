# JavaScript Core concept

## What is JavaScript Engine?
Js engine allows computer to understand the js code.
#### ECMAScript Engine
V8,SpiderMonkey <br/>
ECMAScript is the governing body of JavaScript that essentially decides how the language should be standardized<br/>
### Inside the JavaScript engine
Js file -> Parser -> AST -> Interpreter -> Bytecode -> <br/>
> > > > > > >-> Profiler -> Compiler -> Optimized code -><br/>
1. lexical analysis which breaks the code into something called tokens to identify their meaning so that we know what the code is trying to do.
2. These tokens are formed into what we call AST that is an abstract syntax tree
3. So we parse the code, we try and figure out how the text is divided up based on keyboards from JavaScript.
4. Then it gets formed into this tree like structure called abstract syntax tree.
5. Once in this form, it goes through something called an interpreter.
6. Profiler, compiler, and we get some code (CPU can understand)

### Writing Optimized Code
slow down the Javascript
- eval()
- arguments
- for in
- with 
- delete

- Hidden classes : instantiate object properties in the same order so that hidden classes, which is what the compiler uses underneath the hood.
* V8 uses hidden classes to optimize property access time. It works similarly to the fixed object layouts used in languages like Java, except they are created at runtime.
- inline caching : code that exectues the same method repeatedly multiple times. instead of looking up object every time, it will cache or inline cache so that it becomes piece of text.

Optimization takeaways
1. Always instantiate your object properties in the same order so that hidden classes, and subsequently optimized code, can be shared.
2. Adding properties to an object after instantiation will force a hidden class change and slow down any methods that were optimized for the previous hidden class. Instead, assign all of an object’s properties in its constructor.
3. Code that executes the same method repeatedly will run faster than code that executes many different methods only once (due to inline caching).

we should write predictable code not only for human but also for machines. The more predictable code is, the better it will be.

### WebAssembly
Why not just use machine code from the begining?
If javascript is a comiled language then the compiling has to happen on the browser, back in the day it will slow down the speed. Also all the browsers have to agree on an executable format to run Javascript.

Web Assembly(abbreviated Wasm) is standard binary executable format for a stack-based virtual machine. Wasm is designed as a portable compilation target for programming languages, enabling deployment on the web for client and server applications.

### Call Stack and Memory Heap
Memory Heap is where the memory allocation happens.
Call stack is where the engine keeps track of where your code is in its execution.

How does garbage collection work in JavaScript?
it uses something called Mark and Sweep Algorithm
Memory leaks are pieces of memory that the application have used in the past, but is not needed
any longer, but has not yet been returned back to us to the pool of free memory.

Memory leak
case1 global variable
case2 event listeners : add event listeners and never remove them when we don't need them. keep adding and adding event listeners create memory leak.
case3 setInterval 

global execution context
