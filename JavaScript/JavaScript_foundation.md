### Execution Context
JavaScript sees the brackets, it's going to create something called execution context onto the stack.
The base execution context is called the global execution context.

Stack
execution context
execution context
Global execution context

Whenever code is run in JavaScript, it is run inside of an execution context.

The first thing the JavaScript engine does is to create this global execution context.
In inside the global execution context
1. Global object (window)
2. this

### Lexical environment
lexical enviroment simply means where we write something.
lexical means at compile time where is the code written and based on when the compiler or the interpreter sees our code, it will know different things about the code.

In JavaScript our lexical scope (available data + variables where the function was defined)
Determines our available variables. Not where the function is called(dynamic scope)

### Hoisting
Hoisting is the behavior of moving the variables or function declarations to the top of their respective environments during compilation phase. Variables are partially hoisted and function declarations are hoisted.

When JavaScript engine sees var or function, it's going to hoist it and make space for it in memeory.

1. function expression
(Only going to be run after it was defined)
```
var add = function (){
    console.log('Hi');
}
```
2. function declaration
```
function add(){
    console.log('Hi);
}
```

With global execution context, we have the global object, this object during the creation phase that get assigned. During the execution phase, we run our code, During the creation phase, we also have hoisting. Anytime we see the function or var keywords as the first items on the line, we allocate the space for them in heap memory to make sure that the JavaScript engine is ready for the execution.

Hoissting happens on every execution context. Any time run function, a new execution context gets created and we have to go throught the creation phase and execution phase again. It makes unpredictable code so try to avoid hositing. 
```
var food = 'grapes';
var foodThoughts = function (){
    consoel.log('original food:'+food);
    var food = 'kimchi';
    consoel.log('original food:'+food);
}
foodThought();
```