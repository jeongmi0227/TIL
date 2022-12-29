### Node.js foundation

How do you run JavaScript?
Need a runtime, sort of JavaScript engine and a runtimeto be able to run the code that's what node does.
A browser runs a JavaScript engine. V8 is JS engine for chrome.

What if we don't have browser and want to run JavaScript on our computers?
=> Node.js

Node is JavaScript runtime. What is JavaScript runtime? 
=> JavaScript environment that allows us to run JavaScript as well as do some extra stuff(libuv).

Node.js in a simplified form is simply a way for us to give a JavaScript file to the Node.js runtime
It's going to go through the V8 engine and it's going to read the JavaScript.
Any time it sees something that maybe isn't part of JavaScript, it's going to communicate with libuv library.

Is a web browser a JavaScript Runtime?
=> Yes

#### Node.js 
Node.js runtime has JavaScript engine to execute JavaScript code.
Also has the Node.js APIs (fs, http, path, crypto) will call into C++ Node.js bindings.
Actual implementation of some of these core functionalities such as working with file or the http protocol,lives in libuv.

V8 and libuv are two most important internal components of Node.js.


#### Non-blocking
blocking code executes synchronously. Non-blocking code execute in the background or even in parallel with the rest of the code.
Non blocking asynchronous code that allows CPU over to continue executing the other instructions in our JavaScript program while we are making use of our other devices, such as hard drive. 

#### Is JavaScript synchronous or asynchronous?
Common job interview question.
=> JavaScript is a synchronous language. One statement executes after the other.
However, when JavaScript is run in certain environments like browser or Node.js, it allows us to write asynchronous functionality.
But this functionality like setTimeout is not strictly part of JavaScript. It comes from Node APIs from global object in the browser from window object.
JavaScript can behave in an asynchronous way, but it doesn't come this way out of the box. We have to manipulate it to be this way.


#### Is Node.js multi-threaded?
Traditionally, JavaScript is a single threaded programming language.
In Node, we have one main thread. This one thread runs the V8 engine, our JavaScript code, including the node APIs(libuv) which is the event loop.

libuv manages Asynchronous I/O 
1. file system
2. network
Event loop is code in libuv that runs are asynchronous functions and executes the corresponding callback when the result of the function is ready.
In Node, any time we call an asynchronous function from JavaScript, it gets put on that event loop.
All of our JavaScript code is running on the main thread and any asynchronous functions are put on the event loop.

