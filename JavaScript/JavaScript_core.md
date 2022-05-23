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
