## Scope and Closure

### Scope

 - JavaScript is not block scoped, it's a function scoped language. We can create a blog by creating a function. Although this is not the only way to create scope but for the most part function is used to create scope
- Method argument is actually means creating a new variable. For example:
```javascript
    var name = "Riyad";
    function printGreet("Hello" + name) {
    console.log(name);
    }

    printGreet("Arthur");
```
    Here, the output will be:
```code
    Hello Arthur
```
In this code block, when the function is called the method argument acts as a new variable. So, the name variable initialized first and the name in method argument are not the same.

- IIFE: Immediately Invoked Function Expression
- In JavaScript, if you declare variables then you can do both read and write operation. But if you don't declare variable, you can do write operation, but you can't do read operation. For example:
```javascript
    //with declaring
    var foo = 10; //write
    console.log(foo) //read

    //without declaring
    foo = 10 // this is okay

    //without declaring variable
    console.log(foo) // ReferenceError, 'foo' is not defined
```
- When you run a JavaScript on a browser the global object is usually the window object. for example if we type 'window' on the console of a browser we see some properties. Here 'window' is the global object and that contains these global properties. So now, when we create a global variable, you are actually creating global properties of 'window' object. The same thing also works for functions. According to the spec, there is one global object that is available across the broad and whenever you create global variables you are essentially creating properties of that global object.
- Consider the following code:
```javascript
    function setValue() {
    a = 10;
    }
    
    setValue();
```
In this code block, when the code executes, variable a creates in global scope.

### Compilation and Interpretation
- JavaScript is both compiled and interpreted langauage.
- In JavaScript, execution is two phase thing:
    - Compilation step, where scope chains are created, the variable being declared each variable goes and sits one of this scopes in scope chain.
    - Interpretaion step, where it gets those variables by referring to the scope chain
> Have a clear concept about Scope Chain 