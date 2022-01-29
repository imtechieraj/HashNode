## Top ES6 Features - Every Javascript Developer Must know...! 🤔

# 1. Understanding Let and Const 

Let and const are different ways of creating variables. we know var, var creates a variable in javascript. Javascript only knows var. With **ES6, a version of javascript**, two different keywords were introduced, **let and const**. 

 If we use let to create a variable that really is variable. let can be updated but not
 re-declared.


```    
         let greeting = "say Hi";
         greeting = "say Hello instead";

``` 


But the most important takeaway here, If you plan on creating a constant value, so something which you only assign once and **never change**. 


```
        const greeting = "say Hi";
        greeting = "say Hello instead";  // error: Assignment to constant variable. 

``` 

# 2. Arrow Functions

This is different syntax for creating Javascript functions. A normal javascript function looks like this.


```
     const myFunction = function() {
                console.log("Hello hask-node")
     }

``` 

 Now an arrow function looks like this. 


```
     const myFunction = () => {
                console.log("Hello hask-node")
     }
     
``` 

I have assigned constant and then on the right side of the equals sign. That's the arrow function syntax instead of function keyword. So an equal sign and a greater than sign and then the function body. 
 
 The arrow function syntax is a bit shorter than the normal syntax since it omits the function keyword and it also and that is the great benefit. 

This keyword in javascript. If you've worked with javascript a bit, you probably know that the this keyword doesn't always refer to what you might have expected it to refer to during you writing your code. When you use this inside an arrow function it will always keep its context and not change it surprisingly on runtime. 

  # 3. Exports and Imports

Another feature which next generation javascript offers is about writing modular code so javascript code you split up over multiple files. 

And the idea behind export and import statements and so-called modules is that inside of a javascript file. we can import content from another file so that the javascript files themselves know their dependencies. 



```
//say.js

function sayHi() {
  alert(`Hello`);
}

function sayBye() {
  alert(`Bye`);
}

export {sayHi, sayBye}; // a list of exported variables
``` 


```
import {sayHi, sayBye} from './say.js';
sayHi(); // Hello
sayBye(); // Bye
``` 
 We export the default keyword. this is a special keyword marking this as the default export of this file.


```
// 📁 user.js
export default class User { // just add "default"
  constructor(name) {
    this.name = name;
  }
}
``` 

```
// 📁 main.js
import User from './user.js';   // not {User}, just User
new User('John');
```


  # 4. Understanding Classes

Another core feature of next generation javascript are classes. Classes are essentially blueprints for objects. A class is created with the class keyword and a class can have both properties and methods. Methods are simply functions attached to classes where properties are variables attached to classes. 

```
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
  get area() {
    return this.calcArea();
   }
  // Method
  calcArea() {
    return this.height * this.width;
  }
}

```

classes are kind of a more convenient way of creating constructor functions so we can create javascript objects with classes as blueprints.
 
That's the idea and classes also support inheritance. Which means we have another class which you inherit from taking all its properties and methods and potentially adding new properties and methods. 

```
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name); // call the super class constructor and pass in the name parameter
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

let d = new Dog('Mitzie');
d.speak(); // Mitzie barks.
```

# 5. The Spread and the Rest operators

Actually it's only one operator three dots. Yes this may look strange but the operator is just three dots. 
The spread operator is used to split up array elements or object properties. So we spread up an array or object.

For example, if we have an old array and we want to add all the elements from that old array to a new array and additionally add a 1 and a 2 element this first syntax would be what we use, 

```
  let numberStore = [0, 1, 2]; 
  let newNumber = 12;
  let newNumber2 = 22;
  numberStore = [...numberStore, newNumber, newNumber2];
  console.log(numberStore); // [0, 1, 2, 12, 22];
``` 
And of course then we can add more elements to it. So if we just use the normal syntax with the square brackets to create an array, the same for the object. We create a new object with curly braces with the new prop but then we also have dot dot dot. Old object to pull out all the properties of the old object and their values and add them as key value pairs to the new object as a side note if the old object.

```
let obj1 = { foo: 'bar', x: 42 };
let obj2 = { foo: 'baz', y: 13 };

let clonedObj = { ...obj1 };
// Object { foo: "bar", x: 42 }

let mergedObj = { ...obj1, ...obj2 };
// Object { foo: "baz", x: 42, y: 13 }
```

Now the rest operator which is used less often though function and you could also use ES6 arrow function. we can get a couple of args in single array variable. we can also name this variable whatever you want but you have to use the three dots in front of it. 
   
```
function myFun(...manyMoreArgs) {
  console.log(manyMoreArgs[0]); //one
  console.log(manyMoreArgs[1]); //two
  console.log(manyMoreArgs[2]); //three
}

myFun("one", "two", "three", "four", "five", "six")

``` 
# 6. Destructuring

Destructuring allows to easily extract array elements or object properties and store them in variables. we can pull out single elements or properties and store them in variables for arrays and objects.


```
let a, b, rest;
[a, b] = [10, 20];
console.log(a); // 10
console.log(b); // 20

[a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(a); // 10
console.log(b); // 20
console.log(rest); // [30, 40, 50]

({ a, b } = { a: 10, b: 20 });
console.log(a); // 10
console.log(b); // 20

({a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40});
console.log(a); // 10
console.log(b); // 20
console.log(rest); // {c: 30, d: 40}

``` 
# 7. Template literals

Template literals introduce more syntax, namely the back-tick, or ` as a mechanism to declare strings, and additionally, placeholder syntax, namely ${}, to support interpolation of variables and expressions. Template literals make it easier to compose strings consisting of both literal strings and expressions in-line that are to be evaluated as part of the string creation. Consider the following:

```
let a = 5;
let b = 10;
console.log(`Fifteen is ${a + b} and
not ${2 * a + b}.`);
// "Fifteen is 15 and
// not 20."
``` 
Template literals can also be used to lay out multiline strings.

```
let str=`string text line 1
string text line 2`
console.log(str);     

//output :
`string text line 1
 string text line 2`
``` 

# 8. JavaScript Default Parameters

In JavaScript, a parameter has a default value of undefined. It means that if you don’t pass the arguments into the function, its parameters will have the default values of undefined.

See the following example:

```
function say(message) {
    console.log(message);
}

say(); // undefined

``` 

In the syntax above, you use the assignment operator (=) and the default value after the parameter name to set a default value for that parameter. For example:

```
function say(message='Hi') {
    console.log(message);
}

say(); // 'Hi'
say(undefined); // 'Hi'
say('Hello'); // 'Hello'
```

# 9. Enhanced Object Literals

ES6 provides enhanced object literals which make it easy to quickly create objects with properties inside the curly braces.

```
function getMobile(manufacturer, model, year) {
   return {
      manufacturer,
      model,
      year
   }
}
getMobile("Samsung", "Galaxy", "2020");
```
# 10. The For/Of Loop

The JavaScript for/of statement loops through the values of an iterable objects.
for/of lets you loop over data structures that are iterable such as Arrays, Strings, Maps, NodeLists, and more.

The for/of loop has the following syntax:

```
const cars = ["BMW", "Volvo", "Mini"];

for (let x of cars) {
  console.log(_item);  // BMW , Volvo , Mini
}
```

Start using ES6 today!!!  ❤️ 

## My resent blog: 

#### Array Helper Methods: Every Javascript Developer Must know ! 😯

https://thisisraj.hashnode.dev/array-helper-methods-every-javascript-developer-must-know