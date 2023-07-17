### 1. Write a program that declares a variable using var, let, and const and prints the value to the console.
#### Answer:
```
var x = "Declared using var";
console.log(x);

let y = "Declared using let";
console.log(y);

const z = "Declared using const";
console.log(z);
```
### 2. Write a program that reassigns a value to a variable declared with let and prints the new value to the console.
#### Answer:
```
let x = "Swapnil";
console.log("Old value:", x);

x = "Swapnil Das";
console.log("New value:", x);
```
### 3. Write a program that tries to reassign a value to a variable declared with const and prints the message to the console.
#### Answer:
```
const x = "Swapnil";
console.log("Old value:", x);

x = "Swapnil Das";
console.log("New value:", x);
```
* It throws an error when trying to reassign a new value to the const variable, because reassigning a value in const variable is not allowed.
### 4. Write a program to declare a const, let, var variable within an if statement and try to access the variable outside the if block, what is the result?
#### Answer:
```
if (true) {
  const x = "Declared with const";
  let y = "Declared with let";
  var z = "Declared with var";
}

console.log("Accessing const variable outside if block:", x);
console.log("Accessing let variable outside if block:", y);
console.log("Accessing var variable outside if block:", z);
```
* The var variable z is accessible outside the if block and can be printed to the console without any issue.
* However, trying to access the let variable y or the const variable x outside the if block will result in a ReferenceError
* As they are block-scoped and not accessible outside their respective blocks it is throwing an error.
### 5. Write a program that concatenates two or more strings and prints the result to the console.
#### Answer:
```
let name1 = "Swapnil "
let name2 = "Das";
let name3 = name1 + name2;

console.log(name3);
```
### 6. Write a program that takes a string as input and prints the length of the string to the console.
#### Answer:
```
let x = prompt("Enter a string:");
let y = x.length;

console.log("Length of the string is:", y);
```
### 7. Write a program that converts a string to uppercase and prints the result to the console.
#### Answer:
```
let x = prompt("Enter a string:");
let y = x.toUpperCase();

console.log("Uppercase string is:", y);
```





