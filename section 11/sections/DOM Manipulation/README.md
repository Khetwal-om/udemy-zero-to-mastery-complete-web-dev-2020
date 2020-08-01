## DOM Manipulation

1. Selectors in JS

```js
document.getElementsByTagName("h1")
HTMLCollection { 0: h1
, length: 1 }

document.getElementsByClassName("second")
HTMLCollection { 0: p.second
, length: 1 }

document.getElementById("first")
<p id="first">

document.getElementsByClassName("second")[0]
<p class="second">

document.querySelector("h1")
<h1>

document.querySelector("li")
<li random="23">

document.querySelectorAll("li")
NodeList(5)
​
0: <li random="23">​
1: <li>​
2: <li>​
3: <li>​
4: <li>
​
length: 5
​
<prototype>: NodeListPrototype { item: item(), keys: keys(), values: values(), … }

document.querySelector("li").getAttribute("random")
"23"
document.querySelector("li").setAttribute("random",10000)
undefined
document.querySelector("li").getAttribute("random")
"10000"
``` 


2. 

```js 
document.querySelector("h1").style
CSS2Properties(0)

document.querySelector("h1").style.background="yellow"
"yellow"
var h1=document.querySelector("h1")
undefined
h1
<h1 style="background: yellow none repeat scroll 0% 0%;">

h1.className="newClassName"
"newClassName"
document
HTMLDocument http://localhost:63342/section%2011/index.html?_ijt=kjk0g5ubpsbu0s8u72rqqov6k8

document.querySelector("li").classList;
DOMTokenList []

document.querySelector("li").classList.add("anotherTitle")
undefined
document.querySelector("li").classList.toggle("done")
true
document.querySelector("h1").innerHTML="something"
"something"
document.querySelectorAll("li")[1]
<li>

document.querySelectorAll("li")[1].parentElement
<ul>

document.querySelectorAll("li")[1].parentElement.children

HTMLCollection { 0: li.anotherTitle.done, 1: li, 2: li, 3: li, 4: li, length: 5 }```
```


## DOM Events


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
  JS workspace
  <h1> Shopping List</h1>
  <p id="first">Get it done today</p>
  <input id="todo" type="text" />
  <button id="enter">Click me </button>
  <ul>
      <li class="bold red" random="23">Notebook</li>
      <li>Ocean</li>
      <li>Spinach</li>
      <li>Rice</li>
      <li>Birthday Cake</li>
  </ul>
  <script  type="text/javascript" src="script.js"></script>
</body>
</html>
```


2. JS 

```js
let button = document.getElementById("enter")
let input = document.getElementById(("todo"))
let ul=document.querySelector("ul")


function inputLength(){
    return input.value.length
}
function createListElement(){
    let li=document.createElement("li")
    li.appendChild(document.createTextNode(input.value))
    ul.appendChild(li);
    input.value="";
}

button.addEventListener("click",function () {
     createListElement()
})


input.addEventListener("keypress",function (event) {
    if( inputLength() >0 &&  event.keyCode===13){
        createListElement()
    }
})

```



---



## Project :)


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="style.css">
    <title>Title</title>
</head>
  <body id="gradient">
    <h1>Background</h1>
    <input type="color" class="color1" name="color1" value="#00ff00">
    <input type="color" class="color2" name="color2" value="#ff0000">

    <h2>Current CSS  Background ..  </h2>

    <h3></h3>
  <script  type="text/javascript" src="script.js"></script>
</body>
</html>
```



2. CSS

```css
body {
    font: 'Raleway', sans-serif;
    color: rgba(0,0,0,.5);
    text-align: center;
    text-transform: uppercase;
    letter-spacing: .5em;
    top: 15%;
    background: linear-gradient(to right, red , yellow); /* Standard syntax */
}

h1 {
    font: 600 3.5em 'Raleway', sans-serif;
    color: rgba(0,0,0,.5);
    text-align: center;
    text-transform: uppercase;
    letter-spacing: .5em;
    width: 100%;
}

h3 {
    font: 900 1em 'Raleway', sans-serif;
    color: rgba(0,0,0,.5);
    text-align: center;
    text-transform: none;
    letter-spacing: 0.01em;

}
```

3. js

```js
var css = document.querySelector("h3");
var color1 = document.querySelector(".color1");
var color2 = document.querySelector(".color2");
var body = document.getElementById("gradient");

function setGradient() {
    body.style.background =
        "linear-gradient(to right, "
        + color1.value
        + ", "
        + color2.value
        + ")";

    css.textContent = body.style.background + ";";
}

color1.addEventListener("input", setGradient);

color2.addEventListener("input", setGradient);
```