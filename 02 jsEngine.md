## JAVASCRIPT ENGINE:
* A JavaScript engine is a computer program that you give JavaScript code to and it tells the computer how to execute it. 
* Basically a translator for the computer between JavaScript and a language that the computer understands.
![jsengine](https://github.com/vivekkumar83/JavaScript/blob/main/jsengine.png)
* Parsing is the process of analyzing the source code, checking it for errors, and breaking it up into parts.
* The parser produces a data structure called the Abstract Syntax Tree or AST
* AST is a tree graph of the source code that does not show every detail of the original syntax, but contains structural or content-related details
### JIT Compiler:
* In modern engines, the interpreter starts reading the code line by line while the profiler watches for frequently used code and flags then passes is to the compiler to be optimized. In the end, the JavaScript engine takes the bytecode the interpreter outputs and mixes in the optimized code the compiler outputs and then gives that to the computer. This is called "Just in Time" or JIT Compiler.
## Call Stack:
* The call stack keeps track of where we are in the code, so we can run the program in order.
* All the execution context is managed by the call stack
* Everything in js happens inside an execution context.
* Execution context is simply the environment within which your code is ran.
*  There are 2 types of execution context in JavaScript, global or function.
*  There are 2 stages as well to each context, the creation and executing phase. 
*  As the JavaScript engine starts to read your code, it creates something called the Global Execution Context.
*  1 stage is the memory creation phase,inside this variable & function in key-value pair exist,also called variable enviroment
*  2 stage is the execution pahse,also called  code component,thread of execution start from here,one line at a time
``` javascript
var n = 2;
function square(num) {
	var ans = num * num;
	return ans;
}
var square2 = square(n);
console.log(square2)     // 4
var square4 = square(4);
console.log(square4);    // 16
```
* how this js code work behind the scene
* first there is global execution context is created
* after the variable n, we come to variable square2 & square4 
* in these variable,there is a function invocation so, another new functional execution context is created for square2 & square4
* similarly in these execution context there is memory creation & execution phase
* all the EC is pushed into call stack one by one & after the operation,it will be deleted automatically one by one,after the whole code will be completed the GEC will be deleted, work as lifo
* in case of recursion function calling function again & again,stack over flow comes into picture.
## Memory Heap:
* The memory heap is a place to store and write information so that we can use our memory appropriately. It is a place to allocate, use, and remove memory as needed.
* JavaScript is a garbage collected language.
* If you allocate memory inside of a function, JavaScript will automatically remove it from the memory heap when the function is done being called. 
* JavaScript completes garbage collection with a mark and sweep method.

## Hoisting:
* Hoisting is a phenomenona in javascript, by which we can access the variable & function even before we initialized it
``` javascript
getName();  // vivek kumar
console.log(x); // undefined

var x = 7;
function getName() {
	console.log("vivek kumar")
}
```
* so in the memory creation phase function getName() stores the whole function & var x stores the undefined.
* functions are fully hoisted
* var variable is hoisted & initliazed to undefined but let & const are hoisted but not initliazed to value
* arow function & function expression behaves just like variable so it stores undefined first
``` javascript
var x = 1;
a();  // 10
b();  // 100
console.log(x);  // 1

function a() {
	var x = 10;
	console.log(x); // find x in the local enviroment
}


function b() {
	var x = 100;
	console.log(x)
}
```
## window & this:
* window is a global object which is created along with global execution context
* when any js code is run a global object is created & a global execution context is created & a this keyword is created.
``` javascript
var a = 10;
function b() {
	var x = 10;
}

// window.a = 10
// this.a = 10
// a = 10 by default window.a

```

* whatever the variable & function you created in the global scope, are attached to window object(global object) & can be access through 
* window.var
* this.var
* var (by default window.var)

* var x is not in the global scope so, this.x is not defined.


## lexical enviroment:
* Scope means where you can access a specific variable or a function in code
* Scope is directly dependent on the lexical enviroment
* wherever a execution context is created, a lexical enviroment is also created
* lexical enviroment is the local memory along with the lexical enviroment of it's parent
* lexical means inhirachical or sequence
* whenever a execution context is created, you also get refrence to the lexical enviroment of it's parent
``` javascript
var b = 10;
function a() {
	c();
	function c() {
		console.log(b);
	}
}
a();
```
* finding b in it's local enviroment of function c if not present then move it's parent local enviroment of function a() then move to it's parent enviroment global level 
* scope chain is process of finding value in lexical enviroment
## let & const:
* let & const declaration are hoisted
``` javascript
console.log(a) // reference error 
let a = 10;

console.log(b); // undefinedf
var b = 100;
```
``` javascript
let a = 10;
console.log(a); // 10

console.log(b); // undefinedf
var b = 100;
```
* global: b = undefined 
* script: a = undefined

* var b is attached to global level but a is attached in a  separate space(script)
* let & const are also get memory but they are stored in a different memory then global
* you can't access these let & const without initiliazation
* temporal dead zone is the time since when this let variable is hoisted and till it is initiliazed some value, the time between that is known as temporal dead zone
``` javascript
console.log(c);  // c = undefined

                  time between this is temporal dead zone
                  
let c = 30;      // c = 10
```
* whenever you try to access a variable in temporal dead zone,it gives you a refrence error
* var b = 100; this is global object so attached to window object 
* this.b = 100
* but let a = 100; this is not global so don't attached to window object
* this.a = undefined
* const is more strict then let 
* const is always initiliazed  with value, & can't be updated again
* but let can be updated without using let keyword
* let & const both are in scope level
* we can update let in same scope level. outside of the scope, it shows error

## Block scope & Shadowing:
``` javascript
{
	 this is block
}
```
* whatever all the variable & function can access inside the block, block scope called

``` javascript
{
  var a = 10;
  let b = 50;
  const c = 30;
}
```
*           Block --> b : undefined (hoisted in block)
*                     c : undefined (hoisted in block)

* Global --> a : undefined (hoisted in global)

* let & const can not access outside of the block

``` javascript
var a = 100;  // global
let b = 50;   // script
const c = 40; // script
{
	var a = 10; // global but updated 
	let b = 20; // block 
	const c = 30; // block
	console.log(a);  // 10
	console.log(b);  // 20
	console.log(c);  // 30
}
console.log(a);  // 10
console.log(b);  // 50
console.log(c);  // 40
```

``` javascript
let a = 20;
{
	var a = 20;
}
```
* we can not shadowing a let variable using var, we can shadowing only let inside block
``` javascript
let a = 20;
function x() {
	var a = 20;
}
```
* this can be done, because var is functionl block so it's boundry is function 
* but in the above case, it is on the block level scope, so can't shadowing  
``` javascript 
var a = 20;
{
	let a = 20;
}
```
* this is also true because var is in global scope.

* block scope follows lexical scope
``` javascript 
const a = 20;
{
	const b = 100;
	{
		const c = 200;
		console.log(a);
	}
}
```
