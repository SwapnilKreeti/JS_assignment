### 1. What is an IIFE (Immediately Invoked Function Expression) and why would you use it in JavaScript? Give an example of IIFE.
#### Answer:
* An IIFE (Immediately Invoked Function Expression) is a JavaScript function that is executed immediately after it is defined.
*  It is typically used to create a local scope and avoid polluting the global scope.
*  It's useful for encapsulating code and keeping variables private.
*  Example:
```
(function() {
  var x = "Swapnil";
  console.log(x);
})();
```
### 2. What is the purpose of using the bind() method in JavaScript and how is it different from call() and apply()?
#### Answer:
* bind(): The bind() method creates a new function with a bound context (the this value) and returns it. It allows you to set the this value for a function permanently. The bound function can be invoked later, and it will always have the specified this value.
* call(): The call() method allows you to invoke a function immediately and explicitly specify the this value. It accepts the this value as the first argument, followed by any additional arguments that the function expects.
* apply(): The apply() method is similar to call(), but it accepts the this value as the first argument and an array or array-like object as the second argument containing the function arguments.
### 3. What is a Higher-Order Function (HOF) in JavaScript and how is it different from regular functions? Explain with an example.
#### Answer:
* A Higher-Order Function (HOF) in JavaScript is a function that can take one or more functions as arguments and/or return a function as its result.
* It treats functions as first-class citizens, allowing them to be manipulated and composed.
* Higher-Order Functions can receive other functions as arguments, allowing for dynamic behavior and enhancing code reusability.
```
function calculate(operation, x, y) {
  return operation(x, y);
}

function addition(x, y) {
  return x + y;
}

function multiplication(x, y) {
  return x * y;
}

const sum = calculate(addition, 4, 8);      
const product = calculate(multiplication, 3, 4); 

console.log(sum);    
console.log(product);
```
### 4. Write a function called multiplyBy that takes a number as input and returns a new function that multiplies any number passed into it by the original number.
#### Answer:

