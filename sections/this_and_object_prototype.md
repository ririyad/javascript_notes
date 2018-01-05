## this and Object Prototype

- If you want to define a function as a constructor function, consider the convention of naming the function staring with capital letter, like:
``` javascript
function FunctionName()
```
- You need to define a constrcutor function with the ``` new ``` keyword.
- Calling a constructor function without the ``` new ``` keyword doesn't work. No new objects get created, and the return value is undefined.
- There are two default arguments to every function call: arguments and ``` this ```.