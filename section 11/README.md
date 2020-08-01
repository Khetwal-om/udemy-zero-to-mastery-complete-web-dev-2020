# JAVASCRIPT TYPES
---

1. Number

---

**Modulo operation in  JS**

> Need to figure out why the negative sign varies

5%12=5

12%5=2

-5%12=-5

5%-12=5

---

2. String 

```js 
"Hello"+"there"
"Hellothere"
"Hello "+"there"
"Hello there"
'This is pretty decent'
"This is pretty decent"
'This is pretty decent'
"This is pretty decent"
'This  isn\'t very nice'
"This  isn't very nice"
10+"34"
"1034"
"34"+10
"3410"
10+"34"+10
"103410"
10-"3"
7
```
3. Boolean

```js
true
false
false
3>1
true
5>101
false
4=4
Uncaught SyntaxError: invalid assignment left-hand side
debugger eval code:1
4==4
true
4===4
true

undefined
3!==3
false
```


## Exercise

1. 

```js
5+"34"
"534"
5-"4"
1
10%5
0
5%10
5
"Java"+"Script"
"JavaScript"
" "+ " "
"  "
"  "+ 0
"  0"
true + true
2
false + true
1
true + false
1
false - true
-1

false - true
-1
"Bob"-"bill"
NaN
"A"<"B"
true
"A">"B"
false
"a">"A"
true
"b"<"B"
false
"b"<"A"
false
true===false
false
true!true
Uncaught SyntaxError: unexpected token: '!'
debugger eval code:1:4
true!=true
false
```

---


5. Variables

```js
var george= "There pretzels are making me thirsty"+"!";
undefined
george
"There pretzels are making me thirsty!"
prompt("What is your username")
"Om"
var first=prompt("Enter the  first one")
undefined
var second=prompt("Enter the second one")
undefined
first
"10"
second
"20"
Number(first)+Number(second)
30 

var george= "There pretzels are making me thirsty"+"!";
undefined
george
"There pretzels are making me thirsty!"
prompt("What is your username")
"Om"
var first=prompt("Enter the  first one")
undefined
var second=prompt("Enter the second one")
undefined
first
"10"
second
"20"
Number(first)+Number(second)
30
var a= true
undefined
a
true
a=2323
2323
var name="Billy"
undefined
if(name==="Billy"){ }
undefined
if(name==="Billy"){ }
undefined
if(name==="Billy"){ 
}
undefined
if(name==="Billy"){ 
  alert("Billy")
}
undefined
if(name==="Billy"||name=== "Ann"){
   alert("Hi! Billy or Ann")
}
undefined
if(name==="Billy"&&name=== "Ann"){
   alert("Hi! Billy or Ann")
}
undefined
firstName="Bob"
"Bob"
lastName="Smith"
"Smith"
if( firstName==="Bob" && lastName==="Smith"){
   alert("Hi Bob Smith")
}
undefined
if(!firstName==="Bob" && lastName==="Smith"){
   alert("Hi Bob Smith")
}
undefined
!true
false
!false
true
if(!(firstName==="Bob" && lastName==="Smith")) {
   alert("Hi Bob Smith")
}

```

## functions and data structures

---

```js
function sayHello(){
   console.log("hello!")
}
sayHello();

let sayHi=function () {
    console.log("gm , np")
};
sayHi();

function  sing() {
    console.log("El hambre");
    console.log("Tienes")
}
sing();
function multiply(a,b){
    console.log(a,b);
    return a*b
}
console.log(multiply(5,10));

let functionsList = [function apple(){
    console.log("Apple")
}]
console.log(functionsList)

list=["bear","bird"]
console.log(list)
console.log(list.shift())
console.log(list)
list.push("elephant");
console.log(list);
console.log(list.pop());
console.log(list);

list.concat(["bee","dear"]);
console.log(list)
list.sort()
console.log(list)


let myList=["cat","bear","elephant","bee"]
let myEdited=myList.concat(["monkey"])
console.log(myEdited)
```



---

## Objects concepts

--- 

```js
var user = {
    name: "john",
    age: 34,
    hobby: "Soccer",
    isMarried: false,
    spells: ["shazam","boo"],
    shout : function () {
        console.log("short w:Ooooo")
    }
}
var list = ["apple","banana","orange","blanca"]

console.log(user.name)
console.log(user.age)
console.log(user.hobby)
console.log(user.isMarried)

//to add a new property
user.favouriteFood="spinach"
console.log(user.favouriteFood)

var list = [
    {
        username: "andy",
        password: "secr"
    },
    {
        username: "jess",
        password: "loads"
    }
]
// shout is method of user
user.shout()
```
---

## facebook 1

```js
var database = [
    {
        username: "andrei",
        password: "supersecret"
    }
]

var newFeed= [
    {
        username: "Bobby",
        timeline: "myriad slew loads of love legion"
    },
    {
        username: "Sally",
        timeline: "Oh,  I see   Fair enough"
    }
]

let userName= prompt("what's your  username")
let userPassword=prompt("what's your password")

function signIn(user,pass) {
    if(user===database[0].username &&
       pass===database[0].password){
        console.log(newFeed)
    }else{
        alert("invalid!")
    }
}
console.log(signIn(userName,userPassword))
```

## Loops

---
```js
var todos = [
    "clean something.",
    "exercise"
]
todos.forEach(function (i) {
    console.log(i)
})

clean something. 
exercise





var todos = [
    "clean something.",
    "exercise"
]
todos.forEach(function (todo,i) {
    console.log(todo,i)
})


var todos = [
    "clean something.",
    "exercise"
]
function logTodos(todo,i) {
    console.log(todo,i)
}
todos.forEach(logTodos)
```

---

