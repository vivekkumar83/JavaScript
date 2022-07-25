### Function Statement:
* Function Statements is also known as function declaration
``` javascript
a();  // a called
function a() {
	console.log("a called");
}
a();   // a called
``` 

### Function Expression
``` javascript
console.log(b); // undefined
b();            // error
var b = function () {         // function acts like a value
	console.log("b called");
}
b();            // b called
```

### Anonymous Function
``` javascript
(function () {
   //...
});
```
* A function without a name is Anonymous Function,& does not have their own identity
* it is used when the functions are used as values , it is not used as function statement
* in function expression, we use anonymous function as values assign to variables

### Named Function Expression
``` javascript
var b = function xyz() {  
	console.log("b called");  // b called
	console.log(xyz);         // Function:xyz
}
b();   //
xyz(); // we can not access xyz as global scope because it is created in local scope 
```

### Fnction returning function
```javascript
function myFunc(){
    function hello(){
        return "hello world"
    }
    return hello;
}

const ans = myFunc();
console.log(ans()); // hello world
```

### function can be passed in a function as an argument
``` javascript
var b = function (parm1) {
	console.log(parm1)
		
}
function xyz() {
	
}
b(xyz); // Function : xyz
```
* here in the above codde we pass function xyz as an argument in the function b 
``` javascript
var b = function (parm1) {
	return function () {
		
	}		
}

console.log(b()); // [Function (anonymous)]
```
### First class Function:
* the ability of function to be used as values and can be passed these as an arguments to another function and can be returned from the function is this ability is known as first class function
* first class function is also known as first class citizen

### Callback Function:
* callback function are very powerfull in javascript
* it can give access to the whole asynchronous world in a single synchronous thread language
* javascript is a synchronous single threaded language
* it can do only one thing at a time in specific order
``` javascript
setTimeout(function () {
	console.log("timer");
},5000);

function x(y) {
	console.log("x");
	y();
}

x(function y() {
	console.log("y")
});

// x
// y
// after 5 second
// timer
```

### IIFE - IMMEDIATELY INVOKED FUNCTION EXPRESSION:
* A JavaScript immediately invoked function expression is a function defined as an expression and executed immediately after creation. 
* When you define a function, the JavaScript engine adds the function to the global object. 
* if you declare a variable outside of a function using the var keyword, the JavaScript engine also adds the variable to the global object
* If you have many global variables and functions, the JavaScript engine will only release the memory allocated for them until the global object loses its scopes.
* One way to prevent the functions and variables from polluting the global object is to use immediately invoked function expressions.
``` javascript
(function(){
    //...
})();
```
* Can also be referred to as a Self-Executing Anonymous Function.
```javascript
(function() {
    var counter = 0;

    function add(a, b) {
        return a + b;
    }

    console.log(add(10,20)); // 30
}());
```
### Function pass-by-value or pass-by-reference
* In JavaScript, all function arguments are always passed by value. 
* Function arguments are local variables in JavaScript.

### Closures:
* A function binds together with it's lexical enviroment
* function along with it's lexical scope forms a closures
```javascript
function x(){
    var b =7;
    function y(){
        console.log(b);
    }
    return y;
}
var z = x();
console.log(z);
z();
/*
ƒ y(){
        console.log(b);
    }


7
*/
```
```javascript
function x(){
    var b =7;
    return function y(){
        console.log(b);
    }
    y;
}
var z = x();
console.log(z);
z();
/*
ƒ y(){
        console.log(b);
    }


7
*/
```

```javascript
function z() {
    var b =900;
    function x() {
        var a =7;
        function y() {
            console.log(a,b); // 7, 900
        }
        y();
    }
    x();
}
z();

/*
closure (x)
a:7

closure (z)
b:900
*/

```
* it remember the reference of variable a & b
```javascript
function x() {
    var i =1;
    setTimeout(function (){
        console.log(i);
    },3000);
    console.log("vivek");
}
x();
/* output:
vivek
1
*/
```
* in the above code, there is call back function forms closure with reference of variable i
* when the timer has finished call back function executed & print the value of reference of i
### High Order Function:
* Afunction which takes another function as an argument or return a function from it
```javascript
function x() {
    console.log("namaste")
}

function y(x) {
    x();
}
```
* map,filter & reduce are high order functionin js
### Map:
* it is used to transform the array
* it returns a new array
```javascript
const arr = [1,2,3,4,5];

function binary(x) {
    return x.toString(2)
}

const output = arr.map(binary);

console.log(output); // (5) ['1', '10', '11', '100', '101']
```

```javascript
const arr = [1,2,3,4,5];


const output = arr.map(function binary(x) {
    return x.toString(2)
});

console.log(output); // (5) ['1', '10', '11', '100', '101']
```


```javascript
const arr = [1,2,3,4,5];


const output = arr.map((x) =>x.toString(2));

console.log(output); // (5) ['1', '10', '11', '100', '101']
```
### Filter 
```javascript
const arr = [1,2,3,4,5];


const output = arr.filter((x) => x >2);

console.log(output); // (3) [3, 4, 5]
```
### Reduce
* used at a place where you have to take all the element of the array & comeup with the single value out of them
* takes two argument
```javascript
const arr = [1,2,3,4,5];


const output = arr.reduce(function (acc,curr) {
    acc =acc + curr;
    return acc;
}, 0);

console.log(output); // 15
```
### chaining map filter
```javascript
const users = [
    {firstName : "vivek", LastName : "kumar", age : 25},
    {firstName : "gudiya", LastName : "kumari", age : 20},
    {firstName : "rachna", LastName : "kumari", age : 20},
    {firstName : "rashmka", LastName : "mandana", age : 29},
]

const output = users.filter((x) => x.age <25).map((x) => x.firstName);

console.log(output); // (2) ['gudiya', 'rachna']
```
### for-each
```javascript
const users = [
    {firstName: "harshit", age: 23},
    {firstName: "mohit", age: 21},
    {firstName: "nitish", age: 22},
    {firstName: "garima", age: 20},
]

users.forEach(function(user){
    console.log(user.firstName);
});
```
### Sort Method 
* this sort the array assuming string
* it compare the ASCII value of first letter or number
```javascript
const userNames = ['harshit', 'abcd', 'mohit', 'nitish', 'aabc', 'ABC', 'Harshit'];
userNames.sort();
console.log(userNames); // (7) ['ABC', 'Harshit', 'aabc', 'abcd', 'harshit', 'mohit', 'nitish']
```
* output is not as expected because of ascii comparison
```javascript
const numbers = [5,9,1200, 410, 3000];
numbers.sort();
console.log(numbers);

/*
[1200, 3000, 410, 5, 9]
ascii value of 1 in 1200 = 49[49,51,52,53,57]
ascii value of 3 in 3000 = 51
ascii value of 4 in 410 = 52
ascii value of 5        = 53
ascii value of 9        = 57
*/
```
* sollution of the above problem
```javascript
const numbers = [5,9,1200, 410, 3000];
numbers.sort((a,b)=>a-b); // for ascending a-b & descending b-a
console.log(numbers); //  [5, 9, 410, 1200, 3000]
```
### Find method
```javascript
const users = [
    {userId : 1, userName: "harshit"},
    {userId : 2, userName: "harsh"},
    {userId : 3, userName: "nitish"},
    {userId : 4, userName: "mohit"},
    {userId : 5, userName: "aaditya"},
];

const myUser = users.find((user)=>user.userId===3);
console.log(myUser); // {userId: 3, userName: 'nitish'}
```
### Every method
```javascript
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
]


const ans = userCart.every((cartItem)=>cartItem.price < 30000);
console.log(ans); // false
```
### Some method
* any one item exist true
```javascript
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
    {productId: 3, productName: "macbook", price: 25000},
]

const ans = userCart.some((cartItem)=>cartItem.price > 20000);
console.log(ans); // true
```
### fill method 
* value , start , end 
```javascript
const myArray = [1,2,3,4,5,6,7,8];
myArray.fill(0,2,5);
console.log(myArray); // [1, 2, 0, 0, 0, 6, 7, 8]
```
### splice method 
* start , delete , insert 
* delete
```javascript
const myArray = ['item1', 'item2', 'item3'];
const deletedItem = myArray.splice(1, 2);
console.log("delted item", deletedItem); // delted item (2) ['item2', 'item3']
```
* insert 
```javascript
const myArray = ['item1', 'item2', 'item3'];
myArray.splice(1, 0,'inserted item');
console.log(myArray); // ['item1', 'inserted item', 'item2', 'item3']
```
* insert and delete 
```javascript
const myArray = ['item1', 'item2', 'item3'];

const deletedItem = myArray.splice(1, 2, "inserted item1", "inserted item2")
console.log("delted item", deletedItem); // delted item (2) ['item2', 'item3']
console.log(myArray);  // (3) ['item1', 'inserted item1', 'inserted item2']
```
