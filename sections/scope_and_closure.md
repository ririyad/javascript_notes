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