 
 #### Functions are objects

 ```
 // last parameter of the Function will be the actual code body
 const four = new Function('num', 'return num');

 four(4);   // 4
 ```
 Functions are objects, they are a special type of object that is a callable object with the bracket
 notation for invoking the function contains the code it has name and it also has some porperties like call,apply and bind.
 Functions can perform the actions in our code and store them as data and can be passed around like data.
 ```
 function woohoo(){
    console.log('woohoo');
 }

 woohoo.name;
 ```

 Functions are first class citizens in JS
 // Three properties that make functions a first class citizen
 // Anything we can do with other types, we can do with a function. 
 // this idea of a first class citizen property in JavaScript introduces JavaScript to a whole world called functional programming.
 ```
 //1. functions can be assigned into variables and properties of objects.
 var stuff = function(){};

 //2. Pass function as arguments into a function.
 function a(fn){
    fn()
 }
 a(function(){console.log('hiii')})

 //3. Return functions as a values from other functions.
 function b(){
    return function c(){console.log('Bye')}
 }

 var d = b();
 d(); // bye
 ```
#### Higer Order Functions
higher order functions are simply a function that can take a function as an argument or a function that returns another function.
higher order functions has the ability to tell the function what to do during invocation. We are able to have a little bit more flexibility than we had before.
Pros :  keep the code dry and a lot more flexible.

```
const giveAccessTo = (name) =>
    'Access Granted to ' + name;

function authentication(person){
    let array = [];
    let repeat = 0;
    if(person.level === 'admin'){
        repeat = 5000;
    }else if(person.level === 'user'){
        repeat = 1000;
    }
    for(let i=0; i< repeat;i++){
        array.push(i);
    }
    return giveAccessTo(person.name);
}
function letPerson(person,fn){
    // tell it what data use (user) + what to do (fn)
    if(person.level === 'admin'){
        return fn(person);
    }else if(person.level === 'user'){
        return fn(person);
    }
}

letPerson({level:'admin', name:'Tim'}, authentication)
```
Exercise : Higher Order Functions
```
// make generic function 
const multiplyBy = function (num1){
    return function(num2){
        return num1* num2;
    }
}
const multiplyBy = (num1) => (num2) => num1*num2;

const multiplyByTwo =  multiplyBy(2);
const multiplyByTen =  multiplyBy(10);
multiplyByTwo(4); // 8
multiplyByTen(4); // 40
```

#### Closures

```
function a(){
    let granpa = 'granpa'
    return function b(){
        let father = 'father'
        return function c(){
            let son = 'son'
            return `${granpa} > ${father} > ${son}`
        }
    }
}

const one = a();
console.log(a()()());   // granpa > father > son
```

```
// Don't care about hosting, instead setTimeout will goes all the way into web API and gets put on the callback queue.
// The event loop pushes it back onto the stack, 
// but by that time we already ran the callMeMaybe function const callMe has been created already and assigned 
// there is an enclosing function is using it, it's going to create a closure.
function callMeMaybe(){
    setTimeout(function(){
        console.log(callMe);
    },4000);
    const callMe = 'Hiii';
}

callMeMaybe(); //Hiii
```