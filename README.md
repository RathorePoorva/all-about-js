# all-about-js
This repository will cover most of the topics of javascript, interview question based on js, problem based questions and output based code snippets in js. Basically, the end goals is to cover all possible topics related to javascript

| S.No. | Topics |
|-------|-----------
| 1 | [JS Introduction](#js-introduction)|
| 2 | [Data Types](#data-types)|
| 3 | [ES6 Features](#es6-features)|
| 4 | [Default Function Parameters](#default-function-parameters)|
| 5 | [String Interpolation](#string-interpolation)|
| 6 | [JS Introduction](#intro)|
| 7 | [JS Introduction](#intro)|

1. ### JS Introduction
- JS is single threaded and have a single call stack. Hence, synchronous

- In order Javascript to run, we need more than JS Engine which includes Memory Heap and Call Stack, we need Javascript Run-Time Environment. It is part of browser, which includes, Web APIs(AJAX, setTimeout, DOM), Event Loop, Callback Queue

- For Javascript to be non blocking, we create Callback Functions.

2. ### Data Types
Total 9 data types in Javascript.

- 6 primitives data type:
    - String
    - Number
    - Big Int
    - Boolean
    - Symbol
    - Undefined
- Null → special primitive (typeof instance === "object")
- Object → includes arrays, sets, date, map
- Function → every function constructor is derived from Object Constructor. typeof instance === "function"

3. ### ES6 Features
ES6 is more popularly known as  ECMAScript 2015 which is a scripting language based on specification and standardization by ECMA international company in ECMA-262 and ISO/IEC 16232.

To increase the development of Javascript as independent implementation, ES6 was created to standardize Javascript. So now if you say ES6 it mean Javascript with ES6 features.

The wide array features of ES6 make this a very beneficial and efficient scripting language which is useful for everything related to JavaScript technology.

i. Block scoping - introduction to let and const keywords
ii. arrow functions
iii. Helper functions like forEach, map, filter, reduce, find
iv. classes 
v. default function Parameter
vi. rest and spread operator
vii. Destructuring of arrays and objects
viii. Promises
ix. String interpolation
x. for...of Loop

4. ### Default Function Parameters
- Default function parameters allow named parameters to be initialized with default values if no value or undefined is passed.
- argument -vs- parameter: though we use it interchangeably but arguments are what we pass to the function and parameter are what values are being received by the function.
- In Javascript, if no values are passed to the parameter, it is set to undefined by default.
```js
    function printMessage(message) {
        console.log(message);
    }
    printMessage(); // undefined
```
- Typical way to assign a default value is to depend on logical OR operators to handle default values of function parameters:
```js
    function printMessage(message) {
       message = typeof message !== 'undefined' ? message : 'Hello Instagram';
       console.log(message);
    }
    printMessage(); // 'Hello Instagram'
```   
- ES6 provides an easy way to set default parameters:
- using default values
```js
    function printMessage(message='Hi Insta') {
      console.log(message);
    }
    printMessage(); // 'Hi Insta'
    printMessage(undefined); // 'Hi Insta'
    printMessage('Hello Instagram'); // 'Hello Instagram'
```
- using object
```js
    function printMessage({message="Hi",name="Poorva"}={}) {
    console.log(`${message} ${name}`);}
    printMessage(); // Hi Poorva
    printMessage({message:'Hello',name:"Insta"});// Hello Insta
```
- using functions
```js
    function getName (){
    return "Poorva Rathore";
    }
    function printMessage(message="Hi", name=getName()){
    console.log(message + " " +name);
    }
    printMessage(); [//Hello](//hello) Poorva Rathore
    printMessage("Hello","Insta"); //Hello Insta
```
- The default argument is evaluated at call time.
- Parameters are still set left-to-right, overwriting default parameters even if there are later parameters without defaults
- functions and variables declared in the function body cannot be referred to from default value parameter initializers; attempting to do so throws a run-time ReferenceError.

    EG:
```js
    function printMessage(message="hello", name=getName()){
    function getName(){
    return "Poorva";
    }
    console.log(message+" "+name);
    }
    printMessage(); 
```
- QUIZ TIME:
```js
    function add(x=1,y=x+1,z=x+y){
    console.log(x+y+z);
    }
    add(); //6
    add(1,2,3); //6
```
```js
    function subtract(x=y+1,y=1){
    console.log(x-y);
    }
    subtract(); //reference Error
    subtract(10,5); //5
```
5. ### String Interpolation
- ES6 introduced String Interpolation in javascript which means now we can add variables, function calls, arithmetic expressions directly into a string using template literals (string starting and ending with backticks \` \`) and ${expresssion} as placeholders.
- It make your code more readable and less clumpsy

    eg: 
    ```js 
        function printMessage(message, name){
           console.log(`${message}, my name is ${name}.`);
        }
        printMessage("Hello","Poorva"); 
    ```
