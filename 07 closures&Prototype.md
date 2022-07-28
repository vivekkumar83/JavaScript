


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

