# FUNCTION
* Functions are the main “building blocks” of the program. They allow the code to be called many times without repetition
## Function Declaration
* To create a function we can use a function declaration.
``` javascript
function showMessage() {
  alert( 'Hello everyone!' );
}
```
* The function keyword goes first, then goes the name of the function, then a list of parameters between the parentheses and finally the code of the function
*  We can pass arbitrary data to functions using parameters.
``` javascript
function showMessage(from, text) { // parameters: from, text
  alert(from + ': ' + text);
}

showMessage('Ann', 'Hello!'); // Ann: Hello! (*)
showMessage('Ann', "What's up?"); // Ann: What's up? (**)
```
* When the function is called in lines (*) and (**), the given values are copied to local variables from and text. Then the function uses them.
* the function changes from, but the change is not seen outside, because a function always gets a copy of the value:
``` javascript 
function showMessage(from, text) {

  from = '*' + from + '*'; // make "from" look nicer

  alert( from + ': ' + text );
}

let from = "Ann";

showMessage(from, "Hello"); // *Ann*: Hello

// the value of "from" is the same, the function modified a local copy
alert( from ); // Ann
```
## Default values
* when we called the function without an argument, then corresponding value becomes undefined.
``` javascript 
showMessage("Ann");
```
* Such a call would output "*Ann*: undefined". As the value for text isn’t passed, it becomes undefined.
* We can specify the so-called “default” (to use if omitted) value for a parameter in the function declaration, using =:
``` javascript 
function showMessage(from, text = "no text given") {
  alert( from + ": " + text );
}

showMessage("Ann"); // Ann: no text given
```
## Returning a value
* A function can return a value back into the calling code as the result.
``` javascript
function sum(a, b) {
  return a + b;
}

let result = sum(1, 2);
alert( result ); // 3
```

``` javascript
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
* It is possible to use return without a value.

## Naming a function
* Functions name are declare as it show what it does
* Function starting with…
* "get…" – return a value,
* "calc…" – calculate something,
* "create…" – create something,
* "check…" – check something and return a boolean, etc.

## Function expressions
* There is another syntax for creating a function that is called a Function Expression.
``` javascript
let sayHi = function() {
  alert( "Hello" );
};
```
* Here we can see a variable sayHi getting a value, the new function, created as function() { alert("Hello"); }.
* the meaning of these code samples is the same: "create a function and put it into the variable sayHi".
### Function is a value
* no matter how the function is created, a function is a value.
* Both examples above store a function in the sayHi variable.
``` javascript
function sayHi() {
  alert( "Hello" );
}

alert( sayHi ); // shows the function code
};
```
* the last line does not run the function, because there are no parentheses after sayHi
* a function is a special value, in the sense that we can call it like sayHi().
* The code above shows its string representation, which is the source code.
``` javascript
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```
* there are no parentheses after sayHi. If there were, then func = sayHi() would write the result of the call sayHi() into func, not the function sayHi itself.
* Everything would work the same with function expression
``` javascript
let sayHi = function() { // (1) create
  alert( "Hello" );
};

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```
*  why do Function Expressions have a semicolon ; at the end, but Function Declarations do not
*  The semicolon ; is recommended at the end of the statement, it’s not a part of the function syntax.
*  such as let sayHi = 5;, and it’s also there for a function assignment.

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
