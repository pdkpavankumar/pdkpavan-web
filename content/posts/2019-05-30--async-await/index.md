---
title: Boost Your JavaScript Promises with async/await syntax
category: "JavaScript"
cover: preview.png
author: P D K Pavan Kumar
---

## Boost Your JavaScript Promises with async/await syntax

What are async and await.

**Async**
async keyword is used  before the function definition to make the function asynchronous. which returns an [
`AsyncFunction`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction) 
So the async keyword makes the function always to return promise even if it doesn't.

```javascript
async function fun() {
  return 'hai';
}
-------
> fun()
output: Promise {<resolved>: "hai"}
-------
fun().then((msg)=> console.log('message:' +msg))
output: message:hai
```
**Await**
Await key word makes the javascript wait until the promise is settled.
***NOTE:*** it can be only be used in async method
```javascript
fun = async () => {
 console.log('started');
 await fun2();
 console.log('finished');
}
fun2 = () => {
return new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });
}

> fun()
> output:
 started
 Promise {<pending>}
 finished
```
**Error Handling**
Now you can handle promises/asynchronous methods as well with in try/catch blocks.
```javascript
fun = async () => {
  try {
    let response = await fetch('/no-user-here');
    let user = await response.json();
  } catch(err) {
    // catches errors both in fetch and response.json
    alert(err);
  }
}

>fun();
```
Here are something i really think cool about async/await and boosts promises
1. Coding is clean
```javascript
//Before
fun().then((resp) => console.log(resp));

//After 
resp = await fun();
console.log(resp);
```
2. Debugging is simple
Previously  you can set breakpoints in arrow methods that returns expressions now with async/await you can easily keep breakpoints in the code where is no body.

  3. Error Handling
As explained above now error handling with try/catch is possible.
4. Nested promises and conditional promises
Imagine we have nested promises like a new server call has to be made based on intermittent server call. 
```javascript
//Before
fun = () => {
serverCall1().then((resp) => {
    serverCall2(resp.output).then((resp)=> {
      console.log(resp.output);
    });
});
}

//Now 
fun = async () => {
const resp = await serverCall1();
const response = await serverCall2(resp.output);
console.log(response.output);
}
```

---peace