# JavaScript Fundamentals 1:
* In this module we will cover some basic topics of javascript.


## Variables:
* In the javascript we are using three keyword for declare variable var, let, const.

```javascript
var firstName = "vivek";
console.log(firstName); // vivek
```

* upadte var variable without using var keyword
```javascript
firstName =  "kumar";
console.log(firstName); // kumar
```

* let firstName = "ajay"; we can't use firstName here   
```javascript
let name = "harshit";
name = "Mohit";
console.log(name); // Mohit
``` 

```javascript
const pi = 3.14;
console.log(pi); // 3.14
```  


## Data types
* There are eight basic data types in JavaScript.
* JavaScript, are called “dynamically typed”.

### Number
* The number type represents both integer and floating point numbers.
* Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: Infinity, -Infinity and NaN.
* NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance
```javascript
console.log( "not a number" / 2 ); // NaN, such division is erroneous
```
### BigInt
* In JavaScript, the “number” type cannot represent integer values larger than (253-1) (that’s 9007199254740991), or less than -(253-1) for negatives
* BigInt type was recently added to the language to represent integers of arbitrary length.
* A BigInt value is created by appending n to the end of an integer
```javascript
console.log( "not a number" / 2 ); // NaN, such division is erroneous
```
### String
* A string in JavaScript must be surrounded by quotes.
```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

### Boolean (logical type)
* The boolean type has only two values: true and false.
```javascript
let isGreater = 4 > 1;
console.log( isGreater ); // true (the comparison result is "yes")
```

### The “null” value
* It’s just a special value which represents “nothing”, “empty” or “value unknown”.
```javascript
let age = null;
```
* The code above states that age is unknown.


### The “undefined” value
* The meaning of undefined is “value is not assigned”.
* If a variable is declared, but not assigned, then its value is undefined
```javascript
let age;
console.log(age); // shows "undefined"
```

### Objects and Symbols
* All other types are called “primitive” because their values can contain only a single thing (be it a string or a number or whatever). 
  In contrast, objects are used to store collections of data and more complex entities so non - primitive
* The symbol type is used to create unique identifiers for objects. 


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


## Type Conversions:
* for converting the type of value from one type to another type.
* alert automatically converts any value to a string to show it. 
* Mathematical operations convert values to numbers.

### String conversion 
* String conversion happens when we need the string form of a value.
* String(value) function to convert a value to a string
``` javascript
let value = true;
alert(typeof value); // boolean

value = String(value); // now value is a string "true"
alert(typeof value); // string
```

### Numeric Conversion
* Numeric conversion happens in mathematical functions and expressions automatically.
``` javascript
alert( "6" / "2" ); // 3, strings are converted to numbers
```
* Number(value) function to explicitly convert a value to a number
``` javascript
alert( "6" / "2" ); // 3, strings are converted to numbers
```

* If the string is not a valid number, the result of such a conversion is NaN
``` javascript
let age = Number("an arbitrary string instead of a number");

alert(age); // NaN, conversion failed
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
``` javascript
let age = 18;
let message;

message = age >= 16 ? 'You can drive.' : 'You cannot drive.';

console.log(message);
```

