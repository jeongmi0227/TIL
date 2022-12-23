### Types in JavaScript
```
// Primitive types (It's a data that only represents a signle value and a variable of a primitive type directly contains the value of that type.)
typeof 5 // number in memeory the value is 5
typeof true //boolean
typeof 'text' //string
typeof undefined //undefined
typeof null // object
typeof Symbol('Hiii') //symbol

// Non primitive types (Does not contain the actual value directly)
typeof {} // object
typeof [] // object
typeof function(){} //function
```
undefined is the absence of definition. 
null is an absence of value.

functions and arrays are objects.

#### Array.isArray() check if it is array or not
```
// arrays are object typeof cannot determine if it is array or not
Array.isArray([1,2,3]); // true
Array.isArray({})   // false
```
### Pass by reference vs Pass by value
primitive type are immutable. If we need to change it, remove the existing value completely.(Cannot change the value)
```
// Pass by value
// copy the value and create that value somewhere else in memory.
var a = 5;
var b = a;

b++
console.log(a); // 5
console.log(b); // 6

// Pass by reference

let obj1 = {name:'Park', password: '123'};
let obj2 = obj1;

obj2.password = 'easy';
console.log(obj1);  //password has been changed
console.log(obj2); //password has been changed

// Array
var c = [1,2,3,4,5];
//var d = c;
var d = [].concat(c);
d.push(18274734);
console.log(c) // 1,2,3,4,5
console.log(d); // 1,2,3,4,5,18274734

// Object1
let obj = {a:'a',  b:'b',  c:'c'};

let clone = Object.assign({},obj); // copy and creat new clone 
let clone2 = {...obj}; // spread operator same as Object.assign

obj.c = 5;
console.log(obj);
console.log(clone); // no changes in this clone object
console.log(clone2); // no changes in this clone object


// Object2
let obj = {
    a:'a', 
    b:'b', 
    c:{
        deep: 'try and copy me'
    }
};

// shallow cloning where we can only clone the first layer
let clone = Object.assign({},obj); // copy and creat new clone 
let clone2 = {...obj}; // spread operator same as Object.assign

// deep clone
// ** Deep clone can have some performance implications.
// if the object is extremely deep, a massive object then it's going to take a long time to clone everything.
let superClone = JSON.parse(JSON.stringify(obj)); // This won't be used too much, recommend to use other ways to deep clone.

obj.c.deep = 'hello';
console.log(obj);
console.log(clone); // c has been updated 
console.log(clone2); // c has been updated 
console.log(superClone); // no changes in this  clone object

```

#### Exercise: Compare Objects
How would you compare two objects if they are pointing to a different location in memory but still have the same properties?
```
var user1 = {name : "nerd", org: "dev"};
var user2 = {name : "nerd", org: "dev"};
var eq = user1 == user2;
alert(eq); // gives false
```

#### Type coericion
Type coericion means when the appearance that is the things to the left and to the right of the operator are different types.
One of them will be converted into an equivalent value by the JavaScript engine.

type coericion means the language  converting a certain type to another type.
```
1 == '1' // JS engine will convert this to 1 == 1
```

#### Do all languages have type coericion?
=> Yes they do, we always need to convert types between programs to do things.

Object.is()
```
-0 == +0 // true

// How can we compare those value correctly?
// Object.is() is pretty much same as '===' except for a few cases.
Object.is(-0,+0); // false

NaN === NaN // false but we can use Object.is it will return true
```