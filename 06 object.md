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
### Object Methods
* When the value is a function, the property becomes a method
```javascript
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet: function () {
        console.log('Hello, World!');
    }
};
```
```javascript
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet() {
        console.log('Hello, World!');
    }
};

person.greet(); // Hello, World!
```
* the this value references the object that invokes the method.
```javascript
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet: function () {
        console.log('Hello, World!');
    },
    getFullName: function () {
        return this.firstName + ' ' + this.lastName;
    }
};


console.log(person.getFullName()); // // Hello, World!
```
