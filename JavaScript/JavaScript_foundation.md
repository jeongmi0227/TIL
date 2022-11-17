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

Hoisting happens on every execution context. Any time run function, a new execution context gets created and we have to go throught the creation phase and execution phase again. It makes unpredictable code so try to avoid hositing. 
```
var food = 'grapes';
var foodThoughts = function (){
    consoel.log('original food:'+food);
    var food = 'kimchi';
    consoel.log('original food:'+food);
}
foodThought();
```
Function Expression
```
var canada = () =>{
    console.log('cold');
}
```
Function Declaration
```
function korea(){
    console.log('warm');
}
```
Function Invocation/Call/Execution
canada function is defined at runtime when we actually run the function or called the function
korea function is defined when the compiler initally looks at the code and starts hositing and allocating memory.
```
canada()
india()
```

When a function is invoked, create a new execution context on top of global execution context and then we get this keyword.
In function invocation, we get arguments keyword and arguments is only available to us when we create a new execution context with a function. 
arguments keyword gives an object
* arguments looks like an array but it's not really an array.  The arguments keyword might make compiler or javascript engine less able to optimize code, because we cannot really use array methods on this.
* Each execution context we create a new arguments objects
```
function marry(person1,person2){
    console.log('arguments',arguments);
    console.log(Array.from(arguments)); // convert it into an array
    return `${person1} is now married to ${person2}`;
}
```
* Modern JavaScript avoid arguments
```
// Rest Parameters
function marry2(...args){
    console.log('arguments',args);
    console.log(Array.from(arguments)); // create an array
    return `${args[0]} is now married to ${args[1]}`;
}
```

Variable enviroment is a place that variables can live in individual execution contexts(variables inside function). 
They all technically live in JavaScript engine memory. Some function have access to their certain variables and some don't

```
// 1. function declarations, so these functions get hoisted and put at the top allocating memory space for them.
// 2. isValid is a global variable is assigned an undefined when it gets hoisted.
// 3. Then we start running or executing our code during the execution phase.
// 4. The first step is 'var isValid = false;', in the memory space we change undefined to now false.
// 5. The second step is 'one();', we invoke the function and a new execution context is created on top of the stack.
// 6. some of the information can be on the actual call stack or the execution context.
// Each execution context has its own variable environment
function two(){
    var isValid; // undefined
}

function one(){
    var isValid = true; // local env (variable env) 
    two(); // new exectuion context is created
}

var isValid = false;
one();

// two() -- undefined 
// one() -- true
// global execution context () -- false, 'one' and 'two' functions in the global variable environment.
```
 
All of these functions have a global lexical environment that is they are written in the global space. 
(not inside of another function, just on the main page. They get attached to the window object or the global object.)
All these functions have their own variable environment and they have access to each their own variables, but they also have little link
What we call is 'scope chain'. Links give us access to variables that are in our parent environment(global environment)

In JavaScript our lexical scope(available data + variables where the function was defined) determines our avaiable variables.(variables in our local environment or variable environment) Not where the function is called (dynamic scope)

It does not matter where the function is called, no matter where the function is on the execution stack.
What matters is where the function is written.

Lexical scope (static scope by JS language) only by looking at the source code, we can determine which environment the variables and data are available in, that is what the compiler does.

The JavaScript compiler looks at the code and attaches all these scope chains before it even runs the code.
The scope chain starts where the variable is defined and goes all the way down to the global context to see if the variable exists.

```
// static scope
var x = 'x';
function findName(){
    console.log(x);
    var b = 'b';
    return printName();
}

function printName(){
    var c = 'c';
    return 'Andrei Neagoie';
}

function sayMyName(){
    var a = 'a';
    return findName();
}
```
Function lexical environment that is findName is written insdie of sayMyName function
Global scope is the outermost scope. Variables declared outside a function are in global scope.
They can be accessed in any other scope that is inside of the functions.
```
function sayMyName(){
    var a = 'a';
    return function findName(){
        var b = 'b';
        console.log(c); // cannot access - undefined (Have this variable but it's not assigned anything right now)
        return function printName(){
            var c = 'c';
            console.log(b); // can  access parent environment
            return 'Jeongmi'
        }
    }
}

sayMyName()()()
```
