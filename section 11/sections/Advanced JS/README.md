## Advanced  concepts of JS

1. let , var and const 

```js
const player ='bobby'
undefined
let experience= 100
undefined
let wizardLevel=false
undefined
if(experience>90){
  let wizardLevel=true
  console.log('inside', wizardLevel)
}
inside true debugger eval code:3:11
undefined
console.log(wizardLevel)
false
```

--- 

```js
const player ='bobby'

let experience= 100

var wizardLevel=false

if(experience>90){
  var wizardLevel=true
  console.log('inside', wizardLevel)
}
console.log('outside',wizardLevel)
inside true debugger eval code:9:11
outside true debugger eval code:11:9
```

2. Object assignment

```js
const obj= {
  player: 'bobby',
  experience: 19
}
undefined
obj={player: 'andy', age : 20}
Uncaught TypeError: invalid assignment to const 'obj'
    <anonymous> debugger eval code:1

```

---


```js
const obj= {
  player: 'bobby',
  experience: 19
}
undefined
obj.player='noob'
"noob"

obj

Object { player: "noob", experience: 19 }


```

---

```js
const obj= {
  player: 'bobby',
  experience: 19
}
undefined
const {player,experience} = obj
undefined
player
"bobby"
experience
19
```

---

> Simple assignmet , a:a,b:b can be written as a,b if names are identical .

```js
const a = "Sam"
undefined
const b= "fun"
undefined
const obj = { a, b }
undefined

obj

Object { a: "Sam", b: "fun" }
```

--- 

> Template strings or ( backticks )


```js
const name="Lucy"
undefined
const age=22
undefined
const greet = `Hello ${name} , glad you're  ${age} `
undefined
greet
"Hello Lucy , glad you're  22 "
```


> default arguments 

```js
function greet( name= '', age=30,pet='cat'){
  return `Hello ${name}  ,  do you have a ... ${pet}`
}
undefined
greet()
"Hello   ,  do you have a ... cat"

```

--- 
 
```js 
function greet( name= '', age=30,pet='cat'){
  return `Hello ${name}  ,  do you have a ... ${pet}`
}
undefined
greet("John",20,"otter")
"Hello John  ,  do you have a ... otter"
```


> Symbol
 
  


---  

> Arrow function

```js 
function add(a,b){ 
   return a+b
}
undefined
add(10,1)
11
const answer=(a,b)=> a+b
undefined
answer(10,10)
20
```


> Advanced functions Closures , a function ran, the function executed . It's never going to execute again , it's going to remember there are references to those variables so the child scope always has access to the parent scope.

```js
const first =()=> {
  const greet='Hi'
  const second=()=> {
    alert(greet)
 }
  return second
}
const newFunc=first()
newFunc()
```

--- 

1. Curring

> Curring , converting a function that takes multiple arguments to fun that takes  single argument.


```js 
const multiply = (a,b) => a*b
undefined
const curriedMultiply=(a)=>(b)=> a*b
undefined
curriedMultiply(12)
curriedMultiply(b)
​
length: 1
​
name: ""


```

> The correct way to call.

```js
const curriedMultiply=(a)=>(b)=> a*b
undefined
curriedMultiply(12)
function curriedMultiply(b)

curriedMultiply(3)(4)
12
```

> Another approach

```js 
const curriedMultiply=(a)=>(b)=> a*b
undefined
const multiplyByFive = curriedMultiply(5)
undefined
multiplyByFive(10)
50
```
---

4. Compose

> The act of putting two functions together to form a third function , where output of one function is the input of other one.

```js
onst compose = (f,g) => (a) =>  f(g(a))
undefined
const sum =(num) => num+1
compose(sum,sum)(5)
7
```

5. Sideeffect

> Avoid sideeffects using functional purity
```js
var a=5
function b(){
  a=2
}
```


---


6. Advanced Arrays

1. forEach 

```js
const array = [1,2]
const updatedOne = array.forEach((num)=> num*2)
array
Array [ 1, 2 ]
``` 

#### Significant stuffs to learn :)

---

1. map

> forEach just loops over , in map we can loop over each element and return new array , always have return element, map  transforms the array , with map all sideeffects  are gona

```js
const array=[1,2]
const mapArray = array.map(num=> num*2)
console.log(mapArray)
Array [ 2, 4 ]

```

2. filter 

```js
const array=[1,2,3,4]
const filterArray=array.filter(num=> num>2)
filterArray
Array [ 3, 4 ]
```

3. reduce

> 

```js
array = [19,29,100,400]
Array(4) [ 19, 29, 100, 400 ]

const reduceArray =array.reduce((accumulator,num)=> accumulator+=  num)
undefined
reduceArray
548


[ 10, 40, 50, 60 ]

const reduceAccumulator =array.reduce (accumulator,num)=> {
  return accumulator+ num 
}, 0 )
undefined
reduceAccumulator
160
const reduceMethod =array.reduce((accumulator,num)=> {
  return accumulator+ num 
}, 0 )
undefined
reduceMethod
160
const reduceConcept=array.reduce((accumulator,num)=> {
  return accumulator+ num 
}, 100 )
undefined
reduceConcept
260
```



---



##### Advanced Objects

1. References

```js
var object1= { value: 10 }
var object2= object1
var object3 = {value: 10}
object1===object2
object1===object3
object1.value =19
console.log(object2.value)
console.log(object3.value)
19 
10
```


2. Class

> constructor

```js
class Player {
  constructor(name,type) {
    this.name=name;
    this.type=type;
 }   
   introduce() {
      console.log(`${this.name}   :    ->   ${this.type}`)
} 
}
undefined
class Wizard extends Player {
  constructor(name,type) {
    super(name,type) 
}
  play(){
     console.log(` ${this.type} from wizard class.`) 
 }
}
undefined
const wiz1=new Wizard('Shally','Healer')
const wiz2= new Wizard('Shawn','Magin')

console.log(wiz1)
Object { name: "Shally", type: "Healer" }


console.log(wiz2)
Object { name: "Shawn", type: "Magin" }

wiz1.introduce()
Shally   :    ->   Healer debugger eval code:7:12
wiz2.introduce()
Shawn   :    ->   Magin debugger eval code:7:12
wiz1.play()
 Healer from wizard class. debugger eval code:6:14
wiz2.play()
 Magin from wizard class. debugger eval code:6:14
```

9. Pass by reference / value

> Objects are references in Javascript

```js
let obj={ a: 'a',b: 'b'}
undefined
let obj2=obj
undefined
obj
Object { a: "a", b: "b" }

obj2
Object { a: "a", b: "b" }

obj2.b='e'
"e"
obj
Object { a: "a", b: "e" }

obj2
Object { a: "a", b: "e" }

​
```




> Make a new object using Object.clone()

```js
let obj={ a: 'b',b: 'c'}
let clone= Object.assign({},obj)
clone
Object { a: "b", b: "c" }

obj
Object { a: "b", b: "c" }

clone
Object { a: "b", b: "c" }

clone.a='d'
"d"
obj
Object { a: "b", b: "c" }

clone
Object { a: "d", b: "c" }
```

> The another approach is using spread operator

```js
let obj={a: 'a',b: 'b'}
let clone={...obj}
undefined
clone
Object { a: "a", b: "b" }

obj.a='i'
"i"
obj
Object { a: "i", b: "b" }

clone
Object { a: "a", b: "b" }

clone.b='o'
"o"
obj
Object { a: "i", b: "b" }

clone
Object { a: "a", b: "o" }
```


> Shallow clone is cloning first level

```js
let obj = { a: 'a',c: { deep : 'copy here'}}
obj
{…}
​
a: "a"
​
c: Object { deep: "copy here" }
​
<prototype>: Object { … }

let clone={...obj}
undefined
clone
Object { a: "a", c: {…} }

obj
Object { a: "a", c: {…} }

obj.c.deep="yep"
"yep"
obj
{…}
​
a: "a"
​
c: Object { deep: "yep" }
​
<prototype>: Object { … }

clone
{…}
​
a: "a"
​
c: Object { deep: "yep" }
​
<prototype>: Object { … }
```

> deep cloning , using JSON

```js
let obj={ a: 'a',c: 'deep copy using JSON ...'}
let clone={...obj}
let superClone=JSON.parse(JSON.stringify(obj))
undefined
obj.c='Try '
"Try "
obj
Object { a: "a", c: "Try " }

superClone
Object { a: "a", c: "deep copy using JSON ..." }
```

---

5. Type Coercion 
> When datatypes on left hand side and right hand side varies.



> Three equals means compare two values but don't do  coercion

```js
1=='1'
true
1==='1'
false
```

10. ES7  

> includes

```js
'Hellooo'.includes('o')
true
'Helloo'.includes('oo')
true
'Helloo'.includes('oooo')
false
const pets=['cats','dog','fox','otter']
undefined
pets.includes('cats')
```

> exponential

```js
const square=(x)=>x**2
undefined
square(10)
100
```

11. ES8

> padStart() , padEnd()

```js
'Turtle'.padStart(10)
"    Turtle"
'Turtle'.padEnd(10)
"Turtle    "
```

>  

```js
const fun=(a,b,c,d,)=> {
 console.log(a)
}
undefined
fun(1,2,3,4,)
1


const fun=(a
           ,b,
            c,
            d,)=> {
 console.log(a)
```



> Object.values(),.entries(),.keys()

```js
let obj= {  
  username0: 'Santa',
  username1: 'Joey',
  username2: 'Phoebe',
  username4: 'Stu'
}
Object.keys(obj).forEach((key,index)=> {
 console.log(key,obj[key])
})
username0 Santa 
username1 Joey   
username2 Phoebe  
username4 Stu
```
> values()

```js
Object.values(obj).forEach(value=> console.log(value))
Santa debugger eval code:1:44
Joey debugger eval code:1:44
Phoebe debugger eval code:1:44
Stu
```

> entries()

```js
Object.entries(obj).forEach(value=> console.log(value))
Array [ "username0", "Santa" ]

Array [ "username1", "Joey" ]

Array [ "username2", "Phoebe" ]

Array [ "username4", "Stu" ]

Object.entries(obj).map(value=> { return value[1] + value[0].replace('username','') })
Array(4) [ "Santa0", "Joey1", "Phoebe2", "Stu4" ]
```

11. es 10

> flat on Arrays

```js
const array = [1,2,3,44]
array.flat()
Array(4) [ 1, 2, 3, 44 ]

const array = [1,2,3,[4,4],5,[10]]
array.flat()
Array(7) [ 1, 2, 3, 4, 4, 5, 10 ] 
const array = [1,2,3,[4,4],5,[10,[1]]]
array.flat()
(8) […]
​
0: 1
​
1: 2
​
2: 3
​
3: 4
​
4: 4
​
5: 5
​
6: 10
​
7: Array [ 1 ]


```

> We can decide up to how many layers we want to flatten the array 



```js
```



> 
```js
const entries = ['bob',,,,,,,,'sally','zen','tim']
entries.flat()
Array(4) [ "bob", "sally", "zen", "tim" ]
```

> flatMap()

```js
const entries = ['bob',,,,,,,,'sally','zen','tim']
const chaos=entries.flatMap(creature=> creature+ ':)')
undefined
chaos
Array(4) [ "bob:)", "sally:)", "zen:)", "tim:)" ]
```

> trimStart()   trimEnd()

```js
let userMail='          eddy@gmail.com'
userMail.trimStart()
"eddy@gmail.com"
```


 
> formEntries()

```js
userProfiles=[['commanderTom',20],['DevEd',22],['Brad',19]]
Array(3) [ (2) […], (2) […], (2) […] ]

Object.fromEntries(userProfiles)
Object { commanderTom: 20, DevEd: 22, Brad: 19 }
```

> ES8

```js
userProfiles=[['commanderTom',20],['DevEd',22],['Brad',19]]
Array(3) [ (2) […], (2) […], (2) […] ]

const obj=Object.fromEntries(userProfiles) 
Object.entries(obj)
(3) […]
​
0: Array [ "commanderTom", 20 ]
​
1: Array [ "DevEd", 22 ]
​
2: Array [ "Brad", 19 ] 
```


---




12. Try Catch


--- 

13. loops


> for of  , iterates over strings,arrays.

```js
const basket=['apple','grapes']
for(item of basket){ 
 console.log(item) 
}
apple
grapes
```
> for in 


```js
const basket=['apples','oranges']
const detailedBasket = { 
    apples: 5,
    oranges: 12
}
for(item of basket){
    console.log(item)
}

for(item in detailedBasket){
  console.log(item)
}

iterating ...
apples   
oranges

ennumerating

apples 
oranges
```

> arrays are  objects in JS

```js
const basket=['one','2']
undefined
for(item in basket){
  console.log(item)
}
0 
1 
```

