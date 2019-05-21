---
title: My top ES6 Features
category: "JavaScript"
cover: gabriel-sollmann-1594110-unsplash.jpg
author: P D K Pavan Kumar
---

Here are some of ES6 features that i use very often.

1. Default Paramters

I honestly use this syntax whenever i create methods containing parms with default values.

```javascript
//Before
function link(color, text) {
  color = color || 'blue';
  text = text || 'www.pdkpavan.com';
  //logic goes here
}

//Now
link = (color = 'blue', text = 'www.pdkpavan.com') {
  //logic goes here
}

```

2. Destructuring Assignment

This is quite handy when we get the desired data from a bunch of json data.

```javascript
//Before
function fetchData() {
  var response = somesynchronousservercall();
  var key = response.key;
  var username = response.username;
  //logic goes here 
} 

//Now
fetchData = () => {
  const { key, username } = somesynchronousservercall();
  //logic goes here
}
```

3. Arrow functions
  
  I am a big fan of this ES6 feature. This made javascript code fun. This features saves the this keyword context in React many times.

```javascript
//Before
function addNumbers(a, b) {
  return a+b;
}

//Now
addNumbers => a + b;
```

4. Spread/Rest Operator
  ... the three dots can do some really cool stuff and save lot time

case 1: trying to get the arguments
```javascript
//Before
function shoNumbers() {
  console.log(arguments);
}

//Now
showNumbers = (...args) => console.log(args);
```

case 2: Cloning of a object
```javascript
//Before
var mylist = {a: 1, b:2, c:3};
var clone = Object.assign({}, mylist);

//Now
const mylist = {a:1, b:2, c:3};
const clone = {...mylist};
```

case 3: Concatenation
```javascript
//Before 
var a = [1,2,3];
var b = [4,5,6];
var c = a.concat(b);

//Now
const a = [1,2,3];
const b =[4,5,6];
const c = [...a, ...b];
```

5. Propery short-hand
  This is handy when the property has same name in key value pair

```javascript
//Before
function math() {
  function add() {...}
  function multiply() {...}

  return {
    add: add,
    multiply: multiply
  }
}

//Now
math = () => {
  add = () => {...};
  muliply = () => {...};

  return {
    add,
    multiply
  }
}
```

--
Peace.