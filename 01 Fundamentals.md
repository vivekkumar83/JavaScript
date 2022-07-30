## Variables:
* In the javascript we are using three keyword for declare variable var, let, const.
* var & let used
* for constant const used
* loosely typed or dynamic language
```javascript
var myNum; // declare
myNum = 7; // assign
console.log(myNum);
myNum = 8; // update
console.log(myNum);

var newNum = myNum; // copy in another variable
console.log(newNum);

newNum = 9;
console.log(newNum);
console.log(myNum);

let firstName = "vivek";
firstName = "kumar";
console.log(firstName);

const pi  = 3.14; // cant update
```

## Data types
### 7 primitive datatypes
* primitive type that has only one value
* immutable
* The variable assigned to a primitive type may be reassigned to a new value, but the original value can not be changed
* Primitives are passed by value
#### types
* null
* undefined
* boolean
* number
* string
* symbol 
* bigint 
### complex data type
* Objects are able to be mutated and their properties are passed by reference
* Booleans can be objects (if defined with the new keyword)
* Numbers can be objects (if defined with the new keyword)
* Strings can be objects (if defined with the new keyword)
* Dates are always objects
* Maths are always objects
* Regular expressions are always objects
* Arrays are always objects
* Functions are always objects
* Objects are always objects

### Null
* there is an absence of value

### Undefined
* when a variable is declared but not initialized, it is assigned the value of undefined.
```javascript
let counter;
console.log(counter);        // undefined
console.log(typeof counter); // undefined
```
### NaN
* Not a Number
* special numeric value that indicates an invalid number
```javascript
console.log('a'/2); // NaN;
```
### Bigint
* The bigint type represents the whole numbers that are larger than 253 – 1. 
```javascript
let pageView = 9007199254740991n;
console.log(typeof(pageView)); // 'bigint'
```


### The typeof operator
* The typeof operator returns the type of the argument.
* A call to typeof x returns a string with the type name:
```javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```
  
* The last three lines may need additional explanation:
* Math is a built-in object that provides mathematical operations
* The result of typeof null is "object". That’s an officially recognized error in typeof,null is not an object. It is a special value with a separate type of its own
* The result of typeof alert is "function", because alert is a function.

## alert, prompt, confirm:
### alert
* It shows a message and waits for the user to press “OK”.
``` javascript
alert("Hello");
```
* The mini-window with the message is called a modal window. 

### prompt
* The function prompt accepts two arguments
``` javascript
result = prompt(title, [default]);
```

``` javascript
let age = prompt('How old are you?', 100);

alert(`You are ${age} years old!`); // You are 100 years old!
```

### confirm
* The function confirm shows a modal window with a question and two buttons: OK and Cancel.
* The result is true if OK is pressed and false otherwise.
``` javascript
let isBoss = confirm("Are you the boss?");

alert( isBoss ); // true if OK is pressed
```
## Control Flow:
```javascript
let weight = 70; // kg
let height = 1.72; // meter

// calculate the body mass index (BMI)
let bmi = weight / (height * height);

let weightStatus;

if (bmi < 18.5) {
  weightStatus = 'Underweight';
} else if (bmi >= 18.5 && bmi <= 24.9) {
  weightStatus = 'Healthy Weight';
} else if (bmi >= 25 && bmi <= 29.9) {
  weightStatus = 'Overweight';
} else {
  weightStatus = 'Obesity';
}

console.log(weightStatus); // Healthy Weight
```
## Ternary Operator
```javascript
let age = 18;
let message;

message = age >= 16 ? 'You can drive.' : 'You cannot drive.';

console.log(message); // You can drive
```
## while loop
```javascript
let count = 1;
while (count < 10) {
    console.log(count);
    count +=2;
}
```
## do while loop
```javascript
let count = 0;
do {
  console.log(count);
  count++;
} while (count < 5)
```
# Function:
* Functions are the main “building blocks” of the program. They allow the code to be called many times without repetition
## Function Declaration
* To create a function we can use a function declaration.
```javascript
function functionName(parameters) {
    // function body
    // ...
}
```
```javascript
function showMessage(message) {
    console.log("hi",message);
}
```
## Calling a function
* To use a function, you need to call it. Calling a function is also known as invoking a function
```javascript
// function declaration

function showMessage(message) {
    console.log("hi",message);
}

// function calling

showMessage("vivek"); // hi vivek
```
* When the function is called, the arguments values are copied to local variables of parametre of function 
* whatever be the changes occured in the function is not seen outside, because a function always gets a copy of the value
* when we called the function without an argument, then corresponding value becomes undefined.
```javascript
function showMessage(message) {
    console.log("hi",message);
}

showMessage("vivek"); // hi vivek
showMessage(); // hi undefined
```
* We can specify the so-called “default” (to use if omitted) value for a parameter in the function declaration
```javascript
function showMessage(message = "Buddy") {
    console.log("hi",message,"What's up!..");
}

showMessage("vivek"); // hi vivek What's up!..
showMessage(); // hi Buddy What's up!..
```
## Returning a value
* Every function in JavaScript implicitly returns undefined unless you explicitly specify a return value
```javascript
function showMessage(message) {
    console.log("hi",message,"What's up!..");
}

let greet = showMessage("Darling"); // hi Darling What's up!..
console.log(greet); // undefined
```
* after using return 
```javascript
function showMessage(message) {
    return message;
}

let greet = showMessage("Darling"); 
console.log(greet); // Darling 
```
* It is possible to use return without a value
```javascript
function checkAge(age) {
  if (age >= 18) {
    return true;
  } else {
    return confirm('Do you have permission from your parents?');
  }
}

let age = prompt('How old are you?', 18);

if ( checkAge(age) ) {
  alert( 'Access granted' );
} else {
  alert( 'Access denied' );
}
```
## Naming a function
* Functions name are declare as it show what it does
* Function starting with…
* "get…" – return a value,
* "calc…" – calculate something,
* "create…" – create something,
* "check…" – check something and return a boolean, etc.

## Function expressions
* There is another syntax for creating a function that is called a Function Expression.
```javascript
let showMessage = function(message) {
    return message;
}

let greet = showMessage("Darling"); 
console.log(greet); // Darling 
```
* the meaning of these code samples is the same: "create a function and put it into the variable showMessage".
* no matter how the function is created, a function is a value.
```javascript
let showMessage = function(message) {
    return message;
}

let greet = showMessage("Darling"); 
console.log(greet); // Darling 
console.log(showMessage);
// ƒ (message) {
//    return message;
// }
```
* We can copy a function to another variable
```javascript
let sayHi = function() { // (1) create
  alert( "Hello" );
};

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```
## Callback functions
``` javascript
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

function showOk() {
  alert( "You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// usage: functions showOk, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
```
* The arguments showOk and showCancel of ask are called callback functions or just callbacks.

## Arrow functions
``` javascript
let func = (arg1, arg2, ..., argN) => expression;
```
* This creates a function func that accepts arguments arg1..argN, then evaluates the expression on the right side with their use and returns its result.
``` javascript
let sum = (a, b) => a + b;

/* This arrow function is a shorter form of:

let sum = function(a, b) {
  return a + b;
};
*/

alert( sum(1, 2) ); // 3
```
* As you can see, (a, b) => a + b means a function that accepts two arguments named a and b. Upon the execution, it evaluates the expression a + b and returns the result.
* one argument, then parentheses around parameters can be omitted, making that even shorter.
``` javascript
let double = n => n * 2;
// roughly the same as: let double = function(n) { return n * 2 }

alert( double(3) ); // 6
```
* If there are no arguments, parentheses are empty, but they must be present
``` javascript
let sayHi = () => alert("Hello!");

sayHi();
```
``` javascript
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  () => alert('Hello!') :
  () => alert("Greetings!");

welcome();
```
## Multiline arrow functions
* The arrow functions that we’ve seen so far were very simple. They took arguments from the left of =>, evaluated and returned the right-side expression with them.
* Sometimes we need a more complex function, with multiple expressions and statements. 
* we can enclose them in curly braces. The major difference is that curly braces require a return within them to return a value
``` javascript
let sum = (a, b) => {  // the curly brace opens a multiline function
  let result = a + b;
  return result; // if we use curly braces, then we need an explicit "return"
};

alert( sum(1, 2) ); // 3
```
## function inside function:
```javascript
function app(){
    const myFunc = () =>{
        console.log("hello from myFunc")
    }
    
    const addTwo = (num1, num2) =>{
        return num1 + num2;
    }

    const mul = (num1, num2) => num1* num2;

    console.log("inside app");
    myFunc();
    console.log(addTwo(2,3));
    console.log(mul(2,3));
}
app();
// inside app
// hello from myFunc
// 5
// 6
```
