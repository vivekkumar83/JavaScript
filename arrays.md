# Arrays:
* Ordered collection of item
* Store multiple type of values
* index based
* reference type (i.e Object)
* the size of an array is dynamic and auto-growing
```javascript
let temp = [1,1.2,"vivek",null,undefined];
console.log(temp);// [1, 1.2, 'vivek', null, undefined]
```
### Creating an Arrays:
* two ways to create an array
#### Array constructor
```javascript
let arrayName = new Array(); // create an empty array
let arrayName = new Array(10); // create an array of size 10
let arrayName = new Array(1,2,3,"vivek",null); // create an array with values
```
#### Array literal notation
```javascript
let temp = [] // empty array // 
let temp = [1,1.2,"vivek",null,undefined]; // [1, 1.2, 'vivek', null, undefined]
```
### Accessing array elements:
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];

console.log(mountains[0]); // 'Everest'
console.log(mountains[1]); // 'Fuji'
console.log(mountains[2]); // 'Nanga Parbat'
```
* To change the value of an element
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains); // ['Everest', 'Fuji', 'Nanga Parbat']
mountains[1] = 'k2';
console.log(mountains); // ['Everest', 'k2', 'Nanga Parbat']
```
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
mountains[6] = "himalaya";
console.log(mountains); // ['Everest', 'k2', 'Nanga Parbat', undefined, undefined, undefined, 'himalaya']
console.log(mountains.length); // 7
console.log(mountains[2]); // Nanga Parbat
console.log(mountains[3]); // undefined
console.log(mountains[4]); // undefined
```
* now size becomes index + 1 i.e 7 & remaing index filled with undefined values
* access the element outside of it's range show error

### Functions
#### length
* to know the size or number of element in array
```javascript
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
```
#### push() method
* add one or more element to the end of an array and return the new length of the array
```javascript
let userName = ["vivek", "Ajay"];
console.log(userName);  // ['vivek', 'Ajay']
console.log(userName.push("vijay")); // 3
console.log(userName); // ['vivek', 'Ajay', 'vijay']
```
#### pop() method
* used to remove the last element from the array & return that element
* decrese the length
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.pop()); // vijay
console.log(userName); // (2) ['vivek', 'Ajay']
```
#### shift() method
* used to remove the first element from the array & return that element
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.shift()); // vivek
console.log(userName); // (2) ['Ajay', 'vijay']
```
#### unshift() method
* add one element or more element to the begining of the array and return the new length
```javascript
let userName = ["vivek", "Ajay", "vijay"];
console.log(userName); // (3) ['vivek', 'Ajay', 'vijay']
console.log(userName.unshift("kumar")); // 4
console.log(userName); // (4) ['kumar', 'vivek', 'Ajay', 'vijay']
```
#### indexOf()
* used to return the first index at which the given element is found in the array
```javascript
let userName = ["vivek", "Ajay", "vijay", "Ajay"];
let id = userName.indexOf("Ajay");
console.log(id); // 1
```
#### Array.isArray()
*  To check if a value is an array
```javascript
let userName = ["vivek", "Ajay", "vijay", "Ajay"];
console.log(Array.isArray(userName)); // true
```
   
### Primitive vs. Reference
* Primitive values are atomic pieces of data while reference values are objects that might consist of multiple values.
* You can add, change, or delete properties to a reference value, whereas you cannot do it with a primitive value.
* Copying a primitive value from one variable to another creates a separate value copy. It means that changing the value in one variable does not affect the other.
* Copying a reference from one variable to another creates a reference so that two variables refer to the same object.This means that changing the object via one variable reflects in another variable.
```javascript
let num1 = 6;
let num2 = num1;
console.log("value is num1 is", num1);  // value is num1 is 6
console.log("value is num2 is", num2); // value is num2 is 6
num1++;
console.log("after incrementing num1")
console.log("value is num1 is", num1);  // value is num1 is 7
console.log("value is num2 is", num2); // value is num2 is 6
```

```javascript
let array1 = ["item1", "item2"];
let array2 = array1; // both reference to same array
console.log("array1", array1); // array1 (2) ['item1', 'item2']
console.log("array2", array2); // array2 (2) ['item1', 'item2']
array1.push("item3");
console.log("after pushing element to array 1");
console.log("array1", array1); // array1 (3) ['item1', 'item2', 'item3']
console.log("array2", array2); // array2 (3) ['item1', 'item2', 'item3']
```
### clone & concatenate two arrays
* cloning or copying one array into another array without reflecting the another array
* used slice method for cloning 
```javascript
let array1 = ["item1", "item2"];
let array2 = array1.slice(0);
array2.push("item3");
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3']
console.log(array1===array2); // false
```
* used slice method for cloning & adding extra element
```javascript
let array1 = ["item1", "item2"];
let array2 = array1.slice(0).concat(["item3", "item4"]);
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
```javascript
let array1 = ["item1", "item2"];
let array2 = [].concat(array1,["item3", "item4"]);
console.log(array1)  // (2) ['item1', 'item2']
console.log(array2) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
* new method for cloning is Spread operator
```javascript
let array1 = ["item1", "item2"];
let oneMoreArray = ["item3", "item4"];
let array2 = [...array1, ...oneMoreArray];
console.log(array1)  // (2) ['item1', 'item2']
console.log(oneMoreArray) // (3) ['item1', 'item2', 'item3', 'item4']
console.log(array1===array2); // false
```
### for loop in array:
```javascript
let fruits = ["apple", "mango", "grapes", "banana"];
let fruits2 = [];
for(let i=0; i < fruits.length; i++){
    fruits2.push(fruits[i].toUpperCase());
}

console.log(fruits2); // (4) ['APPLE', 'MANGO', 'GRAPES', 'BANANA']
```
* use const for creating array
* we are not changing the address of const variable here
```javascript
// heap memory ["apple", "mango"] 0x11

const fruits = ["apple", "mango"]; // 0x11
fruits.push("banana");
console.log(fruits); // (3) ['apple', 'mango', 'banana']
```
#### for of loop in array
```javascript
const fruits = ["apple", "mango", "grapes", "fruit4", "fruit5"];
const fruits2 = [];
for(let fruit of fruits){
    fruits2.push(fruit.toUpperCase());
}
console.log(fruits2); // (5) ['APPLE', 'MANGO', 'GRAPES', 'FRUIT4', 'FRUIT5']
```
#### for in loop in array
```javascript
const fruits = ["apple", "mango", "grapes", "fruit4", "fruit5"];
const fruits2 = [];

for(let index in fruits){
    fruits2.push(fruits[index].toUpperCase());
}
console.log(fruits2); // (5) ['APPLE', 'MANGO', 'GRAPES', 'FRUIT4', 'FRUIT5']
```
### Array destructuring
* for storing the different value of array in different variable
```javascript
const myArray = ["value1", "value2", "value3","value4"];
let myvar1 = myArray[0];
let myvar2 = myArray[1];
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
```
* using destructuring
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, myvar2] = myArray;
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
```
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, , myvar3] = myArray; // commas skip the value
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar3", myvar3); // value of myvar3 value3
```
```javascript
const myArray = ["value1", "value2", "value3","value4"];

let [myvar1, myvar2, ...myNewArray] = myArray;
console.log("value of myvar1", myvar1); // value of myvar1 value1
console.log("value of myvar2", myvar2); // value of myvar2 value2
console.log(myNewArray);  // (2) ['value3', 'value4']
```
### passing array to function
```javascript
function findTarget(array, target){
    for(let i = 0; i<array.length; i++){
        if(array[i]===target){
            return i;
        }
    }
    return -1;
}
const myArray = [1,3,8,90]
const ans = findTarget(myArray, 8);
console.log(ans); // 2
```

### rest parameters 
```javascript
function findTarget(array, target){
    for(let i = 0; i<array.length; i++){
        if(array[i]===target){
            return i;
        }
    }
    return -1;
}
const myArray = [1,3,8,90]
const ans = findTarget(myArray, 8);
console.log(ans); // 2
```
