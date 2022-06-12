## Object:
* An empty object (“empty cabinet”) can be created using one of two syntaxes.
``` javascript
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```

## Object Methods:
``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

person.greet = function () {
    console.log('Hello!');
}

person.greet(); // Hello!
```

``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet: function () {
        console.log('Hello, World!');
    }
};

person.greet(); // Hello, World!  
```

``` javascript
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet() {
        console.log('Hello, World!');
    }
};

person.greet(); // Hello, World!
```

* Inside a method, the this value references the object that invokes the method. 

``` javascript
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


console.log(person.getFullName()); // John Doe

```

##  this keyword:
* The this references the object of which the function is a property. In other words, the this references the object that is currently calling the function.
``` javascript
let counter = {
  count: 0,
  next: function () {
    return ++this.count;
  },
};

console.log(counter.next()); // 1
```
* The next() is a function that is the property of the counter object. Therefore, inside the next() function, the this references the counter object.
