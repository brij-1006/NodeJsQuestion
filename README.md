
### Table of Contents

# NodeJsQuestion
 ### NodeJS
    # REPL 
        > Read − Reads user's input, parse the input into JavaScript data-structure and stores in memory.
        > Eval − Takes and evaluates the data structure
        > Print − Prints the result
        > Loop − Loops the above command until user press ctrl-c twice.
    # Streams 
        > Read data from a source or write it to a destination
            ## Type of streams 
              Readable − Stream which is used for read operation.
              Writable − Stream which is used for write operation.
              Duplex − Stream which can be used for both read and write operation.
              Transform − A type of duplex stream where the output is computed based on input.
                # ES6 vs Es5

                  ###A.    // ---------- ES5 ----------
               function getNum() {
                 return 10;
               }
               // ---------- ES6 ----------
               const getNum = () => 10;

               ##B. Return Array function

               // ---------- ES5 ----------
               function getArr() {
                 return [1, 2, 3];
               }
               // ---------- ES6 ----------
               const getArr = () => [1, 2, 3];

               C. Return Object function

               // ---------- ES5 ----------
               function getObj() {
                 return { a: 1, b: 2, c: 3 };
               }
               // ---------- ES6 ----------
               // Note the () to differentiate with actual code block
               const getObj = () => ({ a: 1, b: 2, c: 3 });

               D. Return Number function with param

               // ---------- ES5 ----------
               function calcCircleArea(radius) {
                 return Math.PI * radius * radius;
               }
               // ---------- ES6 ----------
               const calcCircleArea = (radius) => Math.PI * radius * radius;
               E. Return Number function with param and code block

               // ---------- ES5 ----------
               function calcCircleArea(radius) {
                 if (!radius) {
                   return null;
                 } else {
                   return Math.PI * radius * radius;
                 }
               }
               // ---------- ES6 ----------
               const calcCircleArea = (radius) => {
                 if (!radius) {
                   return null;
                 } else {
                   return Math.PI * radius * radius;
                 }
               };
               Object Manipulation
               A. Extract object values

               var obj1 = { a: 1, b: 2 };
               // ---------- ES5 ----------
               var a = obj1.a;
               var b = obj1.b;
               // ---------- ES6 ----------
               var { a, b } = obj1;
               B. Define object

               var a = 1;
               var b = 2;
               // ---------- ES5 ----------
               var obj1 = { a: a, b: b };
               // ---------- ES6 ----------
               var obj1 = { a, b };
               C. Merge objects with the spread operator (…)

               var obj1 = { a: 1, b: 2 };
               var obj2 = { c: 3, d: 4 };
               // ---------- ES5 ----------
               var obj3 = Object.assign(obj1, obj2);
               // ---------- ES6 ----------
               var obj3 = { ...obj1, ...obj2 };
               Async Function (Callback vs. Promise)
               // ---------- ES5 (callback) ----------
               function isEvenNumber(num, callback) {
                 if (num % 2 === 0) {
                   callback(true);
                 } else {
                   callback(false);
                 }
               }
               isEvenNumber(10, function(result) {
                 if (result) {
                   console.log('even number');
                 } else {
                   console.log('odd number');
                 }
               });
               // ---------- ES6 (promise) ----------
               const isEvenNumber = (num) => {
                 return new Promise((resolve, reject) => {
                   if (num % 2 === 0) {
                     resolve(true);
                   } else {
                     reject(false);
                   }
                 });
               };
               isEvenNumber(10).then((result) => {
                 console.log('even number');
               }).catch((error) => {
                 console.log('odd number');
               });
               Promise also has some super useful methods like:

               Promise.race → returns the first promise in the iterable to resolve
               Promise.all → returns a promise when all the promises in the iterable have completed
               Module Exports and Imports
               A. Export module

               var testModule = { a: 1, b: 2 };
               // ---------- ES5 ----------
               module.exports = testModule;
               // ---------- ES6 ----------
               export default testModule;
               // ---------- ES6 (child modules) ----------
               export const a = 1;
               export const b = 2;
               B. Import module

               // ---------- ES5 ----------
               var testModule = require(./testModule);
               // ---------- ES6 ----------
               import testModule from './testModule';
               // ---------- ES6 (child modules) ----------
               import { a, b } from './testModule';
               Block Scoping (let)
               // ---------- ES6 ----------
               var num = 0; // num is globally scoped
               for (let i = 0; i < 5; i++) { // i is block scoped
                 num += i;
               }
               console.log(num); // 0 + 1 + 2 + 3 + 4 = 10
               console.log(i); // undefined
               Template Literal (`)
               const a = 1;
               const b = 'b';
               // ---------- ES5 ----------
               const c = 'value of a is ' + a + ' and value of b is ' + b;
               // ---------- ES6 ----------
               const c = `value of a is ${a} and value of b is ${b}`;

