* JavaScript strings are primitive values.
* strings are immutable. It means that if you modify a string, you will always get a new string. The original string doesn’t change.
* There is no separate type for a single character.
``` javascript
let str = 'Hi';
let greeting = "Hello";
```

### Accessing characters
* To get a character at position pos, use square brackets [pos] or call the method str.charAt(pos). 
``` javascript
let str = "Hello";

// the first character
alert( str[0] ); // H
alert( str.charAt(0) ); // H
```

### String length
``` javascript
let str = "Good Morning!";
console.log(str.length);  // 13
```
* To access the last character of the string, you use the length - 1 index
``` javascript 
let str = "Hello";
console.log(str[str.length -1]); // "o"
```

### Strings are immutable
* string immutable,so alwys create a new variable for storing a modified string
``` javascript
let str = 'Hi';

str = 'h' + str[1]; // replace the string

alert( str ); // hi
```

### function in javascript
``` javascript
let firstName = "harshit";

firstName = firstName.toUpperCase();
console.log(firstName);             // HARSHIT
firstName = firstName.toLowerCase();
console.log(firstName);            // harshit
firstName.slice(1);
console.log(firstName);            // arshit
```

### Conversion
* convert number to string
``` javascript
let age = 22
age = age + "";
console.log(typeof(age)); "22"
```

* convert string to number
``` javascript
let myStr = +"34";
console.log(typeof myStr);// number
```

``` javascript
let age = "18";
age = Number(age);
console.log(typeof age); // number
```

### string concatenation
``` javascript
let string1 = "17";
let string2 = "10";

let newString = +string1 + +string2;
console.log(typeof newString);//number
```

``` javascript
let string1 = "17";
let string2 = "10";

let newString = +string1 + +string2;
console.log(typeof newString);//number
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

``` javascript
let age = 22;
let firstName = "harshit"

//"my name is harshit and my age is 22 "
let aboutMe = "my name is " + firstName + " and my age is " + age; 
console.log(aboutMe);
let aboutMe = `my name is ${firstName} and my age is ${age}`
console.log(aboutMe);
```
* evalutes data from left to right

``` javascript
let temp = 5+4+"mohit";
console.log(temp); // 9mohit
let temp = "mohit"+5+4
console.log(temp); // mohit54
```
