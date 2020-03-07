# Online tools
### [can I use](https://caniuse.com/) 
check if js or css new feature could work on the old broswer

# html
## emmet shortcut
you need to install emmet in sublime test 3
```
// html basic framework
! + tab
// add css link
<link + tab + href="format.css"
// add js line + src="script.js"
<script + tab
```

### where to put your js script
at the end of html body tag. because the browser will read the html from the beginning, we want the loading of js file won't delay the loading of page content. 

# Javascript
## Terminology
### Parameter vs Argument
* paramenter is in the definition of function
* argument is the input of the function
### Function Declaration VS Expression
* function declaration is formal define function
* function expression is to assign a function a variable
### variable type
* boolean
* int
* float
* null
* string
* dict

```javascript
var a; // a is undifined variable
```

### Data Structure
#### Array
```javascript
// list could be mixed variable type, but it will have performance issue
var list = ["tiger", "cat",  1];
// pop up the first element and remove it, the rest element will move to the left
list.shift()
// pop the end element
list.pop()
// add the element to the end of list
list.push("elephant")
// concatinate another list with the existing list by creating a new array 
list.concat(["bee", "deer"])
// sort the list in place
list.sort();
```
#### Object
we can create a object without class and define method inside of an object.
```javascript
var user = {
    name: "John", 
    age: 18, 
    hobby: "Soccer", 
    isMarried: false,
    thisMethod: function() {
        alert("hello world!")
    },
};
// to call the attribue
user.age
// to expand the user object
user.married = true

```
### operators
```javascript
// equal 
3 === 3
// not equal
4 !== 5
// or
false || true
// and
true && true
// not 
!true

```

### interact with user
```javascript
// this is comment
var first = prompt();  // get user input
alert(first);  // show alter in navigator
console.log(first) // log in the browser console
```
### control flow
#### if-else
```javascript
var name = "Billy";

if (name == "Billy") {
    alert("hi Billy");
} else if (name == "Suse") {
    alert("hi Suse");
} else {
    alert("I don't know you!");
}
```
#### ternary operator
```javascript
(3>2) ? true:false
```

#### switch
```javascript
function moveCommand(direction) {
    var WhatHappens;
    switch (direction) {
        case "forward":
            WhatHappens = "you encounter a monster";
            break;
        case "back":
            WhatHappens = "you arrived home";
            break;
        case "right":
            WhatHappens = "you found a river";
            break;
        case "left":
            WhatHappens = "you run into a troll";
            break;
        default:
            WhatHappens = "please enter a valid direction"
        
    }
    return WhatHappens;
}
```
### Loops
#### for Loop
```javascript
var my_list = [
    1, 
    2, 
    3, 
    4,
];
for (var i=0; i<my_list.length; i++) {
    console.log(my_list[i])
}
```
#### while Loop
```javascript
var count = 0;
while (count<my_list.length) {
    console.log(my_list[count]);
    count++;
}
```

#### do while Loop
```javascript
var count = 4;
do {
    console.log(my_list[count]);
    count--;
} while (count>=0);
```

#### for each method
only for ECMAScript 5
```javascript
my_list = [1,2,3,4,5];
my_list.forEach(function(i){
    console.log(i)
})
```
### functions
there are two ways of creating function 
#### function declaration
```javascript
function sayHello() {
    console.log("hello");
    return;
}
```
#### Function expression
Anonymous function
technically in javascript function is a variable
```javascript
var sayBye = function() {
    console.log("Bye");
    return; 
}

sayBye();
```

### Scope
1. root scope/windows scope
2. function scope


inside function scope, we can access to the variable in the root scope

# ES6
BABEL is a javascript compiler. It can translate new javascript feature to old javascript code that all the current browser can read it. 
## let + const
* don't use var anymore.
* let variable is local in any brackets not only in function but also in if
* a const variable is not allowed to be updated
* if a object is a const, we cannot assign other object but to update the value in the object
```javascript
// const variable is not allowed to change 
const player = "bobby";
// no one can this function 
const a = function(){
    alert('hello world');
    }

let experience = 100;
let wizardlevel = false;

if (experience>90) {
    // let variable has local soope inside of brackets
    let wizardlevel = true;
    // inside is true
    console.log('inside', wizardlevel);
}
// outside is false
console.log('outside', wizardlevel);

```
## Structuring
```javascript
const obj = {
    player: 'bobby',
    experience: 100,
    wizardLevel: false,
}

// assign attributes to const variable
const {player, experience} = obj

```
## Dynamic Object
```javascript
const name = 'john snow';
// john snow: blby, 3:hihi
const obj = {
    [name]: 'bobby',
    [1 + 2]: 'hihi'
}
```

## Template strings
```javascript
const name = "Sally";
const age = 34;
const pet = "horse";

const greetingBest = `hello ${name} you seem to be ${age + 10}. what a pretty!`

```

## Object properties
```javascript
const a = "Simon";
const b = true;
const c = {};
// input the key value easily
const obj = {a, b, c}

```

## Default argument
```javascript
function greet(name='fanxiao', age=10) {
    console.log(`hello ${name}, with ${age} ages`)
}

```

## Symbol
symbol object is always unique
```javascript
let sym1 = Symbol();
let sym2 = Symbol('foo');
let sym3 = Symbol('foo')

// get false
sym2 === sym3

```
## arrow function
 
```javascript
function addd(a, b) {
    return a + b; 
}
// the following arrow function is the same as the above function
const add = (a, b) => a + b;
```

### Closure
child scope can access the parent scope, but parent scope cannot access the child scope

### Curring
```javascript
// this is normal function
const multiply = (a, b) => a*b
// 
```
### Compose
```javascript
// compose two functions
const compose = (f, g) => (arg) =>f(g(arg));
const sum=(num) => num + 1;
compose(sum, sum)(5) ; 

// compose two functions which get different input
const add_two = (f, g) => (arg1, arg2) =>f(arg1) + g(arg2);
const square=(num) => num ** 2;
add_two(square, square)(3,4);
```
