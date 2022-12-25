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






