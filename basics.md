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
### map
you always need to return while using map. 
use map over forEach if you want to do something on list
```javascript
const array = [1,2,3,4,5]
// inside map should be a function
const mapArray = array.map(num=>{
    return num*2;
})
// the above code should be shortened as following
const mapArray = array.map(num => num*2)
```
### filter
```javascript
const array = [1,2,3,4,5];
// filter the list with the element greater than 2
const filterArray = array.filter(num=> {
    return num > 2;
})
```
### reduce
you can do filter and map with reduce
```javascript
const my_list = [1,2,3,4,5];
// get the sum of all the elements in the list
const reduceArray = my_list.reduce((acc, num) => {
    return acc + num;
}, 10) // 10 is the initiate value, the result is 25
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
#### reference type
```javascript
// false
[] === []

obj00 = { value: 10};
// obj01 is a reference of obj00
obj01 = obj00;
// change made in obj00 will impact on obj01
// true
obj01 === obj00;
// obj02 is a new object
obj02 = { value: 10 };
// false 
obj02 === obj00
```
#### context
context tell you what object we are inside of
```javascript
// in console , this is window
console.log(this === window)
// alert is a method of window object
this.alert('hello world')

// if this is in an object, this is the object
const obj04 = {
    a: function(){
        console.log(this.b);
    }, 
    b: 11,
}
```
#### instatiation
when you reuse the code
```javascript

class Player {
    constructor(name, type) {
        this.name = name;
        this.type = type;
    }
    introduce() {
        console.log(`Hi I am ${this.name}, I'am a ${this.type}`)
    }
}

let obj05 = new Player('fanxiao', 'human');

// inheritance
class Wizard extends Player {
    constructor(name, type) {
        // access the construtor of parent class
        super(name, type);
    }
    play() {
        console.log(`i'am a ${this.type}`)
    }
}

let obj06 = new Wizard('xiao', 'wizard')
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
in side forEach there should be a function
only for ECMAScript 5
```javascript
my_list = [1,2,3,4,5];
// 
my_list.forEach(function(i){
    console.log(i)
})
// use arrow function in forEach
const newArray = [];
my_list.forEach((number)=> {
    newArray.push(number * 2);
});
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

// curring function 
const multiply_curried = (a) => (b) => a * b
// define a new function by curried function
const multiply_by5 = multiply_curried(5)

multiply_by5(10)

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

# ES7
### include
```javascript
// o is in the hello
'hello'.include('o')
```

### power operator
```javascript
const cube = (y) => y **3
```

# ES8
### .padStart() and .padEnd()
```javascript
// add pad at the beginning of string
'Turtle'.padStart(10)
// add pad at the end of string
'Turtle'.padEnd(10)
```
### line
easy to git change
```javascript
const fun = (
             a, 
             b, 
             c, 
            ) => {
    console.log(a);
}
```
### Object.values, Object.entries, Object.keys
```javascript
let obj = {
    username0: 'Santa',
    usernane1: 'Rudolf', 
    username2: 'Mr.Grinch'
}
// Object.keys()
Object.keys(obj).forEach((key, index) => {
    console.log(key, obj[key], index);
})

// Object.values()
Object.values(obj).forEach(value => {
    console.log(value);
})

// Object.entries() get [key, value]
Object.entries(obj).forEach(entry => {
    console.log(entry)
})

// replace 
Object.entries(obj).map(entry => {
    return entry[0].replace('username', '') + entry[1]
})
```
# ES10

### flat
we can choose how many layers to distribute of flat
```javascript
const my_list = [1, 2, [2, 4], [[5, 7], 9]]
// default argument is 1
my_list.flat(2)

// get rid of empty element
const entries = ['a', 'b',,,,,'c']
entries.flat()
```
### flatmap
```javascript
const my_list = [1, 2, [2, 4], [[5, 7], 9]]
// add 10 to each element in all layers
// if the element has more than one layer, 10 will add in the last element as a string
my_list.flatMap(num=>num + 10)
```
### trimStart(), trimEnd()
```javascript
let userEmail1 = '    tigerfanxiao@gmail.com'
let userEmail2 = 'tigerfanxiao@gmail.com   '
console.log(userEmail.trimStart())
console.log(userEmail.trimEnd())
```
### fromEntries
easily transfer a list of key-value to an object
```javascript
let my_list = [['name', 'fanxiao'], ['age', 19]]
Object.fromEntries(my_list)
```
### try-catch
```javascript
// from ES10 no need to create error object
try {
    true + 'hi'
} catch {
    
    console.log('Wrong input')
}

// before ES10 it is needed to create error object
try {
    bob + 'a';
} catch (error) {
    console.log('yuo messed up', error)
}
```

### for of and for in 
```javascript
// for of iterate a iterable array, string
basket = ['apple', 'orange', 'grapes']
for (item of basket) {
    console.log(item)
}

// for in iterate an object enumerable with keys
let obj00 = {
    'name': 'fanxiao',
    'age': 19,
}
for (key in obj00) {
    console.log(key)
}
```