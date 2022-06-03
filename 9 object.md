# Object:
* an object is an unordered collection of key-value pairs. Each key-value pair is called a property.
``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};
```
## Accessing properties
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
*  
