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



* 
