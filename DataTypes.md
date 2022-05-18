# Data types
* There are eight basic data types in JavaScript.
* JavaScript, are called “dynamically typed”.

## Number
* The number type represents both integer and floating point numbers.
* Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: Infinity, -Infinity and NaN.
* NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance
```javascript
console.log( "not a number" / 2 ); // NaN, such division is erroneous
```
## BigInt
* In JavaScript, the “number” type cannot represent integer values larger than (253-1) (that’s 9007199254740991), or less than -(253-1) for negatives
* BigInt type was recently added to the language to represent integers of arbitrary length.
* A BigInt value is created by appending n to the end of an integer
```javascript
console.log( "not a number" / 2 ); // NaN, such division is erroneous
```
## String
* A string in JavaScript must be surrounded by quotes.
```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

## Boolean (logical type)
* The boolean type has only two values: true and false.
```javascript
let isGreater = 4 > 1;
console.log( isGreater ); // true (the comparison result is "yes")
```

## The “null” value
* It’s just a special value which represents “nothing”, “empty” or “value unknown”.
```javascript
let age = null;
```
* The code above states that age is unknown.


## The “undefined” value
* The meaning of undefined is “value is not assigned”.
* If a variable is declared, but not assigned, then its value is undefined
```javascript
let age;
console.log(age); // shows "undefined"
```

## Objects and Symbols
* All other types are called “primitive” because their values can contain only a single thing (be it a string or a number or whatever). 
  In contrast, objects are used to store collections of data and more complex entities so non - primitive
* The symbol type is used to create unique identifiers for objects. 


## The typeof operator
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
