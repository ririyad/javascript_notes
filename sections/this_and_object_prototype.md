## this and Object Prototype

- If you want to define a function as a constructor function, consider the convention of naming the function staring with capital letter, like:
``` javascript
function FunctionName()
```
- You need to define a constrcutor function with the ``` new ``` keyword.
- Calling a constructor function without the ``` new ``` keyword doesn't work. No new objects get created, and the return value is undefined.
- There are two default arguments to every function call: arguments and ``` this ```.
- Consider the following code:
``` javascript
function foo() {
    console.log("Hello");
}

foo();
```
when a function is executed like this, the value of the ``` this ``` keyword is **global object**.
- The **global object** depends on the runtime environment of javascript: if the javascript runs on a browser, the global object is called the **window object**, if the environment is node.js the global object is called **global**