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
## Modifying the value of a property:
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

## Adding a new property to an object
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

## Deleting a property of an object
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

## Checking if a property exists
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

