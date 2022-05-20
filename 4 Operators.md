## alert
* It shows a message and waits for the user to press “OK”.
``` javascript
alert("Hello");
```
* The mini-window with the message is called a modal window. 


## prompt
* The function prompt accepts two arguments
``` javascript
result = prompt(title, [default]);
```

``` javascript
let age = prompt('How old are you?', 100);

alert(`You are ${age} years old!`); // You are 100 years old!
```


## Type Conversions
* alert automatically converts any value to a string to show it. Mathematical operations convert values to numbers.


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



