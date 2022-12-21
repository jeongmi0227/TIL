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

It is going to go up the scope chain to the global environment.
Global environment sees that this doesn't exist and will creat it for us. Just as it's looking up the scope chain.

'use strict' keyword prevents JavaScript doing unexpected pitfalls
```
'use strict'
function weird(){
 height = 50; // leakage of global variables. 
 return height;
}

weird();
var heyhey = function doodle(){
    // do something
    return 'heyhey'
}
heyhey();

doodle(); // Get reference error, this is because the doodle function is actually enclosed in its own scope.
// doodle is added to its own execution contexts variable environment
```

Function scope vs Block scope
scope means what variables we have access to

most other programming languages has block scope
JavaScript is functionally scoped, only create a new scope, a new environment when there is a function.
ES6 introduced the 'let' and 'const' keyword allow us to use block scope 
```
if (5>4){
    var secret = '12345'
    let something ='test' // only access it inside the block scope
}

secret;
```
Block scoping means declaring a variable not just inside a function, but around any curly brackets
like if statements or loops. 
The variable itself let i is still in memory, but the engine just won't allow us to access it before like it was when we used var
This way we get to keep our mental framework of execution context and variable environment, 
but also let and const keyword that give us some of the powers of block scoping.
```
function loop(){
    for(var i = 0; i < 5; i++){
        console.log(i);
    }
    console.log('final',i); // print i number

    // block scope
    for(let j = 0; j < 5; j++){
        console.log(j);
    }
    console.log('final',j); // print reference error
}

loop();
```
If we declare everything as global variable then it will cause polluting the global namespace 
that having too much data on our global execution environment.
global variable can have variable collisions.
All the script tags get combined into one execution context.
Everything is on the global execution context and they overwrite each other if there's any duplicates.

IIFE (Immediately invoked function expression)

```
// IIFE
// We can place all library code inside of local scope to avoid any namespace collisions.

// function expression
// It will not be in global variable and 
// all of the properties created inside over this function are going to be scoped inside IIFE not outside.
// IIFE allows us to call immediately as JavaScript is executing. It's going to define what it is and right afterwards, 
// with the brackets, it's going to call it. It's going to create new variable environment, a new execution context
// This allows to us to attach private data in a new execution context that can be accessed by the global execution context(the chain runs downward)
 
(function(){
     var a = 1;
})();

// function(){}();  syntax error
```

'this' is the object that the function is a property of.(who called me, this keyword acts as a placeholder and we'll refer to whichever object called that method.)
When the global execution context starts during the creation phase, we create the global object and 'this'.
Global  object and 'this', they are equal each other

```
// 1. Gives methods access to their object

const obj = {
    name : 'billy',
    sing(){
        return 'lalala '+this.name
    },
    singAgain(){
        return this.sing()+'!'
    }
}
obj.singAgain()

// 2. Execute same code for multiple objects
function importantPerson(){
    console.log(this.name+'!');
}

const name = 'Sunny';
const obj1 = {
    name: 'Cassy',
    importantPerson: importantPerson
}

const obj2 = {
    name: 'Jacob',
    importantPerson: importantPerson
}

importantPerson() // Sunny
obj1.importantPerson() // Cassy
obj2.importantPerson() // Jacob
```

manipulate this keyword
call(), apply(), bind() 
all the functions use call when invoking a function. 
```
function a(){
    console.log('hi');
}

a.call() // underneath the hood in JS when we do a() invoke the function
// All functions when created, have this porperty called 'call' that allows us to call the function.

a.apply() // call and apply do the same thing.
```
call() and apply() are useful for borrowing methods from an object.
 'this' can be dynamic.
bind() returns a new function with a certain context and parameters.
It is usually used when we want a function to be called later on with a certain type of context or a certain type of this keyword.
bind() allows us to store the this keyword or this function borrowing for later use.
```
const wizard = {
    name: 'Merlin',
    health: 100,
    heal(num1, num2){
        return this.health += num1 + num2;
    }
}

const archer = {
    name: 'Robin Hood',
    health: 30
}

console.log('1', archer);
// wizard.heal.call(archer,50, 30);
wizard.heal.apply(archer, [50, 30]); // take a array as parameters
const healArcher = wizard.heal.bind(archer,100, 30);
healArcher(); 
console.log('2', archer);

```
Exercise: call(), apply()
```
const array = [1,2,3];

// in this case, the 'this' keyword doesn't matter!
function getMaxNumber(arr){
  return Math.max.apply(null, arr);  
}

getMaxNumber(array)
```

function currying
Currying means give partial parameter
it allows us to reuse a piece of code, give it a partial parameter, and create these functions are extensible.
```
function multiply(a,b){
    return a*b
}

let multiplyByTwo =  multiply.bind(this,2);
console.log(multiplyByTwo(4)) // 8

let multiplyByTen =  multiply.bind(this,10);
console.log(multiplyByTwo(4)) // 40
```

Exercise this keyword
```
var b = {
    name: 'jay',
    say(){ console.log(this)}
}

var c = {
    name: 'jay',
    say(){return function (){console.log(this)}}
}

var d = {
    name: 'jay',
    say() {return () => console.log(this)}
}
b.say()   // b object
c.say()() // window object
d.say()() // It fixed problem the this keyword was lexical scoped inside of the arrow function. It does not care about where it was called.
```


