### 1. What is the difference in hoisting behaviour between a function created using function declaration syntax and that created using a function expression syntax? Give an example.
#### Answer:
* Function Declaration:A function created using function declaration syntax is hoisted, which means it is moved to the top of its scope during the compilation phase, allowing the function to be called before it is defined in the code.
* In the code below, the function hfunc is called before its actual declaration.
* This works because during hoisting, the function is moved to the top, allowing it to be invoked even before its actual position in the code.
* The output is Hoisted function
```
hfunc(); 

function hfunc() {
  console.log("Hoisted function.");
}
```
