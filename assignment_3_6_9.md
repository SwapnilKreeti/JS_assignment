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
* Function Expression: On the other hand, a function created using function expression syntax is not hoisted. Instead, it behaves like a regular variable declaration and assignment.
* The output is function expression.
```
var efunc = function() {
  console.log("function expression.");
};

efunc();
```
### 2. Write the usage of following functions / operators and give an example.
### a. Date.now()
#### Answer:
* The Date.now() function is a static method of the Date object in JavaScript.
*  It returns the number of milliseconds that have elapsed since January 1, 1970, 00:00:00 UTC (Coordinated Universal Time).
*  It provides a simple way to get the current timestamp as a numeric value.
```
const currentTimeStamp = Date.now();
console.log(currentTimeStamp);  
```
*  The output is 1628612951356 (The current timestamp in milliseconds).
### b. ?? (nullish coalescing operator)
#### Answer:
* The ?? operator is called the nullish coalescing operator.
* It provides a way to provide a default value when dealing with null or undefined values.
* It returns the right-hand operand if the left-hand operand is null or undefined; otherwise, it returns the left-hand operand.
```
const name = null;
const default = "Swapnil Das";
const resultName = name ?? default;

console.log(resultName); 
```
* The output is Swapnil Das.
### c. ?. (optional chaining operator)
#### Answer:
* The ?. operator, called the optional chaining operator, allows you to safely access properties or call methods of an object without causing an error if an intermediate property or method is null or undefined.
* It short-circuits the evaluation and returns undefined if any intermediate value is null or undefined.
```
const user = {
  name: "Swapnil Das",
  age: 22,
  location: {
    city: "Silchar",
    street: "ABC Street",
  },
};

const street_Name = user?.location?.street;
console.log(street_Name);  // Output: "ABC Street"

const phone_Number = user?.phone?.number;
console.log(phone_Number);  // Output: undefined
```
### 3. Write 2 JS statements, where:
### a. 1st one will split the words of the sentence I love going walkies into an array.
#### Answer:
```
const sentence = "I love going walkies";
const arr = sentence.split(" ");

console.log(arr);
```
* The Output is ["I", "love", "going", "walkies"]
### b. 2nd one will assign the elements of the resultant array into 4 variables (in a single statement).
#### Answer:
```const [w1, w2, w3, w4] = "I love going walkies".split(" ");

console.log(w1);  // Output: "I"
console.log(w2);  // Output: "love"
console.log(w3);  // Output: "going"
console.log(w4);  // Output: "walkies"
```





