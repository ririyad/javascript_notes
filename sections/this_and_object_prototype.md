## this and Object Prototype

- If you want to define a function as a constructor function, consider the convention of naming the function staring with capital letter, like:
``` javascript
function FunctionName()
```
- You need to define a constrcutor function with the ``` new ``` keyword.
- Calling a constructor function without the ``` new ``` keyword doesn't work. No new objects get created, and the return value is undefined.
- There are two default arguments to every function call: arguments and ``` this ```.
- There are **four** different ways to call a function in javascript.
- Consider the following code:
``` javascript
function foo() {
    console.log("Hello");
}

foo();
```
when a standalone function is executed calling directly like mentioned above, the value of the ``` this ``` keyword is **global object**.
- The **global object** depends on the runtime environment of javascript: if the javascript runs on a browser, the global object is called the **window object**, if the environment is node.js the global object is called **global**
- Consider the following code, where function is a property of an object:
```javascript
var obj = {};
obj.foo = function() {
    console.log("Hello");
};

obj.foo();
```
If a function is called in the context of an objet, then when the function is called the ``` this``` reference is referring to the **object** itself. So, if we rewrite the snippet:
```javascript
var obj = {"prop": "This is the object itself!"};
obj.foo = function() {
    console.log("Hello");
    console.log(this);
};

obj.foo();
```
The output will be: (in Chrome Console)
```code
Hello
{prop: "This is the object itself!", foo: f} 
```
- Consuder the snippet
```javascript 
funtion foo() {
    console.log("Hello");
}
new foo();
```
When a function is called with the ``` new ``` keyoword, the ``` this ``` always refers to newly created object. So, if we rewrite the snippet:
```javascript 
funtion foo() {
    console.log("Hello");
    console.log(this);
}
new foo();
```
The output will be: (Chrome)
``` code
Hello
foo{}
foo{}
``` 
- Each function could have a different ``` this ``` references even though there is a function inside another function. Consider the following code:
``` javascript 
function Bicycle(candence, speed, gear, tirePressure) {
    this.candence = candence;
    this.speed = speed;
    this.gear = gear;
    this.tirePressure = tirePressure;
    this.inflateTires = function() {
        this.tirePressure += 3;
    }
}

var biCycle1 = new Bicycle(50, 20, 4, 25);
bicycle1.inflateTires();
``` 
In the follwowing code, there is a top level function called ``` Bicycle ``` it's called constructor which is called in the constructor mode, and there is a inner function:
```javascript
     this.inflateTires = function() {
        this.tirePressure += 3;
    }
```
which is not being called in the costructor mode. So, we can say that, this two functions are differnt even though one of them is inside another. that's why their ``` this ``` reference will be different. The ``` this ``` reference of the constructor function is newely created object whereas the ``` this ```reference of the ``` ìnflateTires ``` function is that object whose property is ``` inflateTires```.