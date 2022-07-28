


### Closures:
* A function binds together with it's lexical enviroment
* function along with it's lexical scope forms a closures
```javascript
function x(){
    var b =7;
    function y(){
        console.log(b);
    }
    return y;
}
var z = x();
console.log(z);
z();
/*
ƒ y(){
        console.log(b);
    }


7
*/
```
```javascript
function x(){
    var b =7;
    return function y(){
        console.log(b);
    }
    y;
}
var z = x();
console.log(z);
z();
/*
ƒ y(){
        console.log(b);
    }


7
*/
```

```javascript
function z() {
    var b =900;
    function x() {
        var a =7;
        function y() {
            console.log(a,b); // 7, 900
        }
        y();
    }
    x();
}
z();

/*
closure (x)
a:7

closure (z)
b:900
*/

```
* it remember the reference of variable a & b
```javascript
function x() {
    var i =1;
    setTimeout(function (){
        console.log(i);
    },3000);
    console.log("vivek");
}
x();
/* output:
vivek
1
*/
```
* in the above code, there is call back function forms closure with reference of variable i
* when the timer has finished call back function executed & print the value of reference of i

### for-each
```javascript
const users = [
    {firstName: "harshit", age: 23},
    {firstName: "mohit", age: 21},
    {firstName: "nitish", age: 22},
    {firstName: "garima", age: 20},
]

users.forEach(function(user){
    console.log(user.firstName);
});
```
### Sort Method 
* this sort the array assuming string
* it compare the ASCII value of first letter or number
```javascript
const userNames = ['harshit', 'abcd', 'mohit', 'nitish', 'aabc', 'ABC', 'Harshit'];
userNames.sort();
console.log(userNames); // (7) ['ABC', 'Harshit', 'aabc', 'abcd', 'harshit', 'mohit', 'nitish']
```
* output is not as expected because of ascii comparison
```javascript
const numbers = [5,9,1200, 410, 3000];
numbers.sort();
console.log(numbers);

/*
[1200, 3000, 410, 5, 9]
ascii value of 1 in 1200 = 49[49,51,52,53,57]
ascii value of 3 in 3000 = 51
ascii value of 4 in 410 = 52
ascii value of 5        = 53
ascii value of 9        = 57
*/
```
* sollution of the above problem
```javascript
const numbers = [5,9,1200, 410, 3000];
numbers.sort((a,b)=>a-b); // for ascending a-b & descending b-a
console.log(numbers); //  [5, 9, 410, 1200, 3000]
```
### Find method
```javascript
const users = [
    {userId : 1, userName: "harshit"},
    {userId : 2, userName: "harsh"},
    {userId : 3, userName: "nitish"},
    {userId : 4, userName: "mohit"},
    {userId : 5, userName: "aaditya"},
];

const myUser = users.find((user)=>user.userId===3);
console.log(myUser); // {userId: 3, userName: 'nitish'}
```
### Every method
```javascript
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
]


const ans = userCart.every((cartItem)=>cartItem.price < 30000);
console.log(ans); // false
```
### Some method
* any one item exist true
```javascript
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
    {productId: 3, productName: "macbook", price: 25000},
]

const ans = userCart.some((cartItem)=>cartItem.price > 20000);
console.log(ans); // true
```
### fill method 
* value , start , end 
```javascript
const myArray = [1,2,3,4,5,6,7,8];
myArray.fill(0,2,5);
console.log(myArray); // [1, 2, 0, 0, 0, 6, 7, 8]
```
### splice method 
* start , delete , insert 
* delete
```javascript
const myArray = ['item1', 'item2', 'item3'];
const deletedItem = myArray.splice(1, 2);
console.log("delted item", deletedItem); // delted item (2) ['item2', 'item3']
```
* insert 
```javascript
const myArray = ['item1', 'item2', 'item3'];
myArray.splice(1, 0,'inserted item');
console.log(myArray); // ['item1', 'inserted item', 'item2', 'item3']
```
* insert and delete 
```javascript
const myArray = ['item1', 'item2', 'item3'];

const deletedItem = myArray.splice(1, 2, "inserted item1", "inserted item2")
console.log("delted item", deletedItem); // delted item (2) ['item2', 'item3']
console.log(myArray);  // (3) ['item1', 'inserted item1', 'inserted item2']
```
