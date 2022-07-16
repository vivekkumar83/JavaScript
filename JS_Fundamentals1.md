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
