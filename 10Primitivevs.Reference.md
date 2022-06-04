## Primitive vs. Reference
* Primitive values are atomic pieces of data while reference values are objects that might consist of multiple values.
* Primitive values (null, undefined, boolean, number, string, symbol, and BigInt)
* Reference values that refer to objects.
``` javascript
let name = 'John';
let age = 25;

let person = {
  name: 'John',
  age: 25,
};
```
* Primitive values & Reference values stored in stack 
* Properties of the refrence value stored in heap memory
* JavaScript allocates memory on the stack for the three variables name, age, and person.
* The JavaScript engine creates a new object on the heap memory. Also, it links the person variable on the stack memory to the object on the heap memory.
* person variable is a reference that refers to an object.
* A reference value allows you to add, change, or delete properties at any time.
``` javascript
let person = {
  name: 'John',
  age: 25,
};

// add the ssn property
person.ssn = '123-45-6789';

// change the name
person.name = 'John Doe';

// delete the age property
delete person.age;


console.log(person);
```

``` javascript
Output:

{ name: 'John Doe', ssn: '123-45-6789' }
```

## Copying values
* When you assign a primitive value from one variable to another, the JavaScript engine creates a copy of that value and assigns it to the variable. 

``` javascript
let age = 25;
let newAge = age;
```
* Behind the scene, the JavaScript engine creates a copy of the primitive value 25 and assign it to the newAge variable.
* the newAge and age are separate variables. If you change the value of one variable, it won’t affect the other.
``` javascript
let age = 25;
let newAge = age;

newAge = newAge + 1;
console.log(age, newAge); // 25, 26
```
* When you assign a reference value from one variable to another, the JavaScript engine creates a reference so that both variables refer to the same object on the heap memory.
*  if you change one variable, it’ll affect the other.
let person = {
  name: 'John',
  age: 25,
};

let member = person;

member.age = 26;

console.log(person);
console.log(member);
```
* First, declare a person variable and initialize its value with an object with two properties name and age.
* Second, assign the person variable to the member variable. In the memory, both variables reference the same object
* change the age property of the object via the member variable
* Since both person and member variables reference the same object, changing the object via the member variable is also reflected in the person variable.
