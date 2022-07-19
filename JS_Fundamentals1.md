# JavaScript Fundamentals 1:
* In this module we will cover some basic topics of javascript.


# Variables:
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

# Data types
### 7 primitive datatypes
* null
* undefined
* boolean
* number
* string
* symbol 
* bigint 
### and a complex data type
* Object

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
# Strings:
### create:
```javascript
let str ="srita";
console.log(str);

let str1 = 'sarita';
console.log(str1);

let str2 = `sarita`;
console.log(str2); 
```
### Accessing characters:
* indexing
* function use charAt()
```javascript
let str ="srita";
console.log(str[0]); //s
console.log(str.charAt(0)); //s
```
### Function in string:
```javascript
str = str.toUpperCase(); 
console.log(str);    // SARITA
str = str.toLowerCase();
console.log(str);   // sarita
str = str.slice(1,3);
console.log(str);   // ar
```
### String length:
```javascript
let newName = "vivek";
console.log(newName.length);
//  last character of the string,use the length - 1 index
console.log(newName.length);
console.log(newName[newName.length - 1]);
console.log(newName[newName.length - 2]);
```
### Strings are immutable:
* cannot be modified once created
* create a new string from an existing string
```javascript
let str = 'Hi';

str = 'h' + str[1]; // replace the string

alert( str ); // hi
```
### Concatenating strings:
```javascript
let firstName = "vivek";
let lastName = "kumar";
let fullName = firstName + " " + lastName;
console.log(fullName);
```
### Conversion:
* convert number to string
```javascript
let age = 22;
age = age + "";
console.log(typeof(age)); // string
age = String(age);
console.log(typeof(age)); // string
```
* convert string to number
```javascript
let age1 = "22";
age1 = +age1;
console.log(typeof(age1)); // number
age1 = Number(age1);
console.log(typeof(age1)); // number

let num = 24;
num = num.toString(num);
console.log(typeof(num)); // string
```
* evalutes data from left to right

``` javascript
let temp = 5+4+"mohit";
console.log(temp); // 9mohit
let temp = "mohit"+5+4
console.log(temp); // mohit54
```
``` javascript
let age = 22;
let firstName = "harshit"

//"my name is harshit and my age is 22 "
let aboutMe = "my name is " + firstName + " and my age is " + age; 
console.log(aboutMe);
let aboutMe = `my name is ${firstName} and my age is ${age}`
console.log(aboutMe);
```

* Numeric conversion rules
* undefined  -------------> 	NaN
* null  -------------->  	0
* true and false -----------> 	1 and 0


## Comparisons
### String comparison
* string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.
* strings are compared letter-by-letter.
``` javascript
alert( 'Z' > 'A' ); // true
alert( 'Glow' > 'Glee' ); // true
alert( 'Bee' > 'Be' ); // true
```

### Comparison of different types
* When comparing values of different types, JavaScript converts the values to numbers.
``` javascript
alert( '2' > 1 ); // true, string '2' becomes a number 2
alert( '01' == 1 ); // true, string '01' becomes a number 1
```

``` javascript
alert( true == 1 ); // true
alert( false == 0 ); // true
```

``` javascript
let a = 0;
alert( Boolean(a) ); // false

let b = "0";
alert( Boolean(b) ); // true
```

### Strict equality
* A strict equality operator === checks the equality without type conversion.
* it checks data types also
* These values are different, because each of them is a different type.
``` javascript
alert( null === undefined ); // false
```

``` javascript
alert( null == undefined ); // true
```

## Nullish coalescing operator '??':
* The nullish coalescing operator (??) is a logical operator that accepts two values and returns the second value if the first one is null or undefined.
``` javascript
const name = null ?? 'John';
console.log(name); // 'John'
```
* The nullish coalescing operator is short-circuited and cannot directly combine with the logical AND or OR operator.
``` javascript
let result = undefined ?? console.log('Hi');// Hi
```

``` javascript
const result = null || undefined ?? 'OK'; // SyntaxError
```

``` javascript
const result = (null || undefined) ?? 'OK'; 
console.log(result); // 'OK'
```

## Exponentiation Operator:
* To raise a number to the power of an exponent
``` javascript
let result = Math.pow(2,2);
console.log(result); // 4

result = Math.pow(2,3);
console.log(result); // 8
```
* The operator ** raises the x to the power of an exponent n
``` javascript
let result = 2 ** 2;
console.log(result); // 4

result = 2 ** 3;
console.log(result); // 8
```

## Conditional branching:
``` javascript
let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

if (year < 2015) {
  alert( 'Too early...' );
} else if (year > 2015) {
  alert( 'Too late' );
} else {
  alert( 'Exactly!' );
}
```
* all values are truthy except false, 0, -0, 0n, "", null, undefined, and NaN.

## Ternary Operator:
* the syntax of the ternary operator
* condition ? expressionIfTrue : expressionIfFalse;
```javascript
let age = 18;
let message;

message = age >= 16 ? 'You can drive.' : 'You cannot drive.';

console.log(message);
```

# Arrays:
* Ordered collection of item
* Store multiple type of values
* index based
* reference type (i.e Object)
* the size of an array is dynamic and auto-growing
```javascript
let temp = [1,1.2,"vivek",null,undefined];
console.log(temp);// [1, 1.2, 'vivek', null, undefined]
```
### Creating an Arrays:
* two ways to create an array
#### Array constructor
```javascript
let arrayName = new Array(); // create an empty array
let arrayName = new Array(10); // create an array of size 10
let arrayName = new Array(1,2,3,"vivek",null); // create an array with values
```
#### Array literal notation
```javascript
let temp = [] // empty array // 
let temp = [1,1.2,"vivek",null,undefined]; // [1, 1.2, 'vivek', null, undefined]
```
### Accessing array elements:
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];

console.log(mountains[0]); // 'Everest'
console.log(mountains[1]); // 'Fuji'
console.log(mountains[2]); // 'Nanga Parbat'
```
* To change the value of an element
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains); // ['Everest', 'Fuji', 'Nanga Parbat']
mountains[1] = 'k2';
console.log(mountains); // ['Everest', 'k2', 'Nanga Parbat']
```
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
mountains[6] = "himalaya";
console.log(mountains); // ['Everest', 'k2', 'Nanga Parbat', undefined, undefined, undefined, 'himalaya']
console.log(mountains.length); // 7
console.log(mountains[2]); // Nanga Parbat
console.log(mountains[3]); // undefined
console.log(mountains[4]); // undefined
```
* now size becomes index + 1 i.e 7 & remaing index filled with undefined values
* access the element outside of it's range show error

### Functions
#### length
* to know the size or number of element in array
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
```
#### push() method
* add one or more element to the end of an array and return the new length of the array
```javascript
let userName = ["vivek", "Ajay"];
console.log(userName);  // ['vivek', 'Ajay']
console.log(userName.push("vijay")); // 3
console.log(userName); // ['vivek', 'Ajay', 'vijay']
```
#### pop() method
* used to remove the last element from the array & return that element
* decrese the length
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.pop()); // vijay
console.log(userName); // (2) ['vivek', 'Ajay']
```
#### shift() method
* used to remove the first element from the array & return that element
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.shift()); // vivek
console.log(userName); // (2) ['Ajay', 'vijay']
```
#### unshift() method
* add one element or more element to the begining of the array and return the new length
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.unshift("kumar")); // 4
console.log(userName); // (4) ['kumar', 'vivek', 'Ajay', 'vijay']
```
#### indexOf()
* used to return the first index at which the given element is found in the array
```javascript
let userName = ["vivek", "Ajay", "vijay", "Ajay"];
let id = userName.indexOf("Ajay");
console.log(id); // 1
```
#### Array.isArray()
*  To check if a value is an array
```javascript
let userName = ["vivek", "Ajay", "vijay", "Ajay"];
console.log(Array.isArray(userName)); // true
```
   
### Primitive vs. Reference
* You can add, change, or delete properties to a reference value, whereas you cannot do it with a primitive value.
* Copying a primitive value from one variable to another creates a separate value copy. It means that changing the value in one variable does not affect the other.
* Copying a reference from one variable to another creates a reference so that two variables refer to the same object.This means that changing the object via one variable reflects in another variable.
```javascript
let num1 = 6;
let num2 = num1;
console.log("value is num1 is", num1);  // value is num1 is 6
console.log("value is num2 is", num2); // value is num2 is 6
num1++;
console.log("after incrementing num1")
console.log("value is num1 is", num1);  // value is num1 is 7
console.log("value is num2 is", num2); // value is num2 is 6
```

```javascript
let array1 = ["item1", "item2"];
let array2 = array1; // both reference to same array
console.log("array1", array1); // array1 (2) ['item1', 'item2']
console.log("array2", array2); // array2 (2) ['item1', 'item2']
array1.push("item3");
console.log("after pushing element to array 1");
console.log("array1", array1); // array1 (3) ['item1', 'item2', 'item3']
console.log("array2", array2); // array2 (3) ['item1', 'item2', 'item3']
```
### clone & concatenate two arrays
* cloning or copying one array into another array without reflecting the another array
* used slice method for cloning 
```javascript
let array1 = ["item1", "item2"];
let array2 = array1.slice(0);
array2.push("item3");
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3']
console.log(array1===array2); // false
```
* used slice method for cloning & adding extra element
```javascript
let array1 = ["item1", "item2"];
let array2 = array1.slice(0).concat(["item3", "item4"]);
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
```javascript
let array1 = ["item1", "item2"];
let array2 = [].concat(array1,["item3", "item4"]);
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
* new method for cloning is Spread operator
```javascript
let array1 = ["item1", "item2"];
let oneMoreArray = ["item3", "item4"];
let array2 = [...array1, ...oneMoreArray];
console.log(array1)  // (2) ['item1', 'item2']
console.log(oneMoreArray) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
### for loop in array:
```javascript
let fruits = ["apple", "mango", "grapes", "banana"];
let fruits2 = [];
for(let i=0; i < fruits.length; i++){
    fruits2.push(fruits[i].toUpperCase());
}

console.log(fruits2); // (4) ['APPLE', 'MANGO', 'GRAPES', 'BANANA']
```
* use const for creating array
* we are not changing the address of const variable here
```javascript
// heap memory ["apple", "mango"] 0x11

const fruits = ["apple", "mango"]; // 0x11
fruits.push("banana");
console.log(fruits); // (3) ['apple', 'mango', 'banana']
```
#### for of loop in array
```javascript
const fruits = ["apple", "mango", "grapes", "fruit4", "fruit5"];
const fruits2 = [];
for(let fruit of fruits){
    fruits2.push(fruit.toUpperCase());
}
console.log(fruits2); // (5) ['APPLE', 'MANGO', 'GRAPES', 'FRUIT4', 'FRUIT5']
```
#### for in loop in array
```javascript
const fruits = ["apple", "mango", "grapes", "fruit4", "fruit5"];
const fruits2 = [];

for(let index in fruits){
    fruits2.push(fruits[index].toUpperCase());
}
console.log(fruits2); // (5) ['APPLE', 'MANGO', 'GRAPES', 'FRUIT4', 'FRUIT5']
```
### Array destructuring
* for storing the different value of array in different variable
```javascript
const myArray = ["value1", "value2", "value3","value4"];
let myvar1 = myArray[0];
let myvar2 = myArray[1];
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
```
* using destructuring
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, myvar2] = myArray;
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
```
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, , myvar3] = myArray; // commas skip the value
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar3", myvar3); // value of myvar3 value3
```
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, myvar2, ...myNewArray] = myArray;
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
console.log(myNewArray);  // (2) ['value3', 'value4']
```

# Object:
* an object is an unordered collection of key-value pairs. Each key-value pair is called a property.
* creating object using curly brackets
* let obj = {}; empty object
* let obj = {name = "mohit", age = 24};
* using new operator 
* let obj = new object();
* let obj = new object ({key1: value1, key2: value2})

``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};
```
### Accessing properties
* To access a property of an object, you use one of two notations: the dot notation and array-like notation.
### 1) The dot notation (.)
``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

console.log(person.firstName);// john
console.log(person.lastName);// Doe
```
### 2) Array-like notation ( [])
``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

console.log(person['firstName']); // john
console.log(person['lastName']); // Doe
```
* When a property name contains spaces, you need to place it inside quotes.
``` javascript
let address = {
    'building no': 3960,
    street: 'North 1st street',
    state: 'CA',
    country: 'USA'
};
```
* To access the 'building no' property, you need to use the array-like notation

``` javascript
address['building no'];
};
```
### Modifying the value of a property:
* To change the value of a property, you use the assignment operator (=)

``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

person.firstName = 'Jane';

console.log(person); 
```

``` javascript
Output:

{ firstName: 'Jane', lastName: 'Doe' }
```

### Adding a new property to an object
``` javascript
let person = {
  firstName: 'John',
  lastName: 'Doe'
};

person.age = 24;

console.log(person); 
```
``` javascript
Output:

{ firstName: 'John', lastName: 'Doe', age: 24 }
```

### Deleting a property of an object
``` javascript
let person = {
  firstName: 'John',
  lastName: 'Doe'
};

person.age = 24;

console.log(person); 

delete person.age;
console.log(person); 
```
``` javascript
Output:

{ firstName: 'John', lastName: 'Doe', age: 24 }
{ firstName: 'John', lastName: 'Doe' }
```

### Checking if a property exists
* The in operator returns true if the propertyName exists in the objectName.
``` javascript
let employee = {
    firstName: 'Peter',
    lastName: 'Doe',
    employeeId: 1
};

console.log('ssn' in employee);
console.log('employeeId' in employee);
```
``` javascript
Output:

false
true
```

### how to iterate object
* two ways (1)for in loop  (2)object.keys
* (1)for in loop
``` javascript
const person = {
    name: "harshit",
    age: 22,
    "person hobbies": ["guitar", "sleeping", "listening music"]
}

for(let key in person){
    // console.log(key); // only key
    // console.log(person[key]); // only value
    // console.log(`${key} : ${person[key]}`); // both key value
    // console.log(key," : " ,person[key]); // // both key value
}
```
* (2)object.keys
``` javascript
const person = {
    name: "harshit",
    age: 22,
    "person hobbies": ["guitar", "sleeping", "listening music"]
}
console.log(Object.keys(person)); // keys in array format ((3) ['name', 'age', 'person hobbies'])
console.log(typeof(Object.keys(person))); // object
const val = Array.isArray((Object.keys(person)));
console.log(val); // true

for(let key of Object.keys(person)){
    console.log(person[key]); 
}

// output:
// harshit
// 22
// (3) ['guitar', 'sleeping', 'listening music']
```

### computed properties
``` javascript
const key1 = "objkey1";
const key2 = "objkey2";

const value1 = "myvalue1";
const value2 = "myvalue2";
// 1st way
const obj = {
    [key1] : value1,
    [key2] : value2
}
// 2nd way
const obj = {};

obj[key1] = value1;
obj[key2] = value2;
console.log(obj);
```
### Spread Operator
* copy
``` javascript
const array1 = [1, 2, 3];
const array2 = [5, 6, 7];

const newArray = [...array1, ...array2, 89, 69]; // (8) [1, 2, 3, 5, 6, 7, 89, 69]
const neewArray = [..."123456789"]; // (9) ['1', '2', '3', '4', '5', '6', '7', '8', '9']
console.log(newArray);
console.log(neewArray);
```
* spread operator in object
``` javascript
const obj1 = {
    key1: "value1",
    key2: "value2",
};
const obj2 = {
    key1: "valueUnique",
    key3: "value3",
    key4: "value4",
};
// for repeating key, updated value assigned
const neewObject = { ...obj2, ...obj1, key69: "value69" }; // {key1: 'value1', key3: 'value3', key4: 'value4', key2: 'value2', key69: 'value69'}
const newObject = { ..."abcde" }; // {0: 'a', 1: 'b', 2: 'c', 3: 'd', 4: 'e'}
console.log(newObject);
console.log(neewObject);
```
### object destructuring

``` javascript
const audio = {
    singerName: "Jubin Nautiyal",
    famousSong: "sun sun barsat ki dhun",
    year: 2022,
    anotherFamousSong: "rimjhim",
};
  
let { singerName, famousSong, ...restProps } = audio;
console.log(singerName);  // Jubin Nautiyal
console.log(famousSong); // sun sun barsat ki dhun
console.log(restProps); //  {year: 2022, anotherFamousSong: 'rimjhim'}
```

### objects inside array

``` javascript
const users = [
    {userId: 1,firstName: 'harshit', gender: 'male'},
    {userId: 2,firstName: 'mohit', gender: 'male'},
    {userId: 3,firstName: 'nitish', gender: 'male'},
]

for(let user of users){
    console.log(user);
}

// output:
// {userId: 1, firstName: 'harshit', gender: 'male'}
// {userId: 2, firstName: 'mohit', gender: 'male'}
// {userId: 3, firstName: 'nitish', gender: 'male'}
```

``` javascript
const users = [
    {userId: 1,firstName: 'harshit', gender: 'male'},
    {userId: 2,firstName: 'mohit', gender: 'male'},
    {userId: 3,firstName: 'nitish', gender: 'male'},
]

for(let user of users){
    console.log(user.firstName);
}
// output:
// harshit
// mohit
// nitish
```
### nested destructuring 
``` javascript
const users = [
    {userId: 1,firstName: 'harshit', gender: 'male'},
    {userId: 2,firstName: 'mohit', gender: 'male'},
    {userId: 3,firstName: 'gudiya', gender: 'female'},
]

const [user1, user2, user3] = users;
console.log(user1); // {userId: 1, firstName: 'harshit', gender: 'male'}
const [{firstName}, ,{gender}] = users;
console.log(firstName); // harshit
console.log(gender); // female
```

``` javascript
const users = [
    {userId: 1,firstName: 'harshit', gender: 'male'},
    {userId: 2,firstName: 'mohit', gender: 'male'},
    {userId: 3,firstName: 'gudiya', gender: 'female'},
]

const [{firstName: user1firstName, userId}, , {gender: user3gender}] = users;
console.log(user1firstName); // harshit
console.log(userId);         // 1
console.log(user3gender);    // female
```
# Function:
* Functions are the main “building blocks” of the program. They allow the code to be called many times without repetition
### Function Declaration
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
### Calling a function
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
### Returning a value
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
### Naming a function
* Functions name are declare as it show what it does
* Function starting with…
* "get…" – return a value,
* "calc…" – calculate something,
* "create…" – create something,
* "check…" – check something and return a boolean, etc.

### Function expressions
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
### Callback functions
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

### Arrow functions
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
### Multiline arrow functions
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
