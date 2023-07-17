### 1. If we execute this Javascript, what will the browser's console show?
```
var text = 'outside';
function logIt(){
console.log(text);
var text = 'inside';
};
logIt();
```
#### Answer:
* The browser's shows undefined.
* In JavaScript, variables declared with var are hoisted, which means their declarations are moved to the top of their scope.
*  However, the assignments are not hoisted, so the local text variable is assigned the value 'inside' after the console.log() statement executes.
### 2. Write a regular expression to reverse the first and last name
#### Answer:
```
var full_Name = "Swapnil Das";
var reversed_full_Name = full_Name.replace(/(\w+)\s(\w+)/, "$2 $1");

console.log(reversed_full_Name); 
```
### 3. Write a Regular expression to validate email address
#### Answer:
```
var email = "swapnildasnits@gmail.com";

var emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;

var isValidEmail = emailRegex.test(email);

console.log(isValidEmail);
```
* In this case, the output is true.
### 4. Find the output
```
var x = 100;
console.log(x);
function test(){
var x = 250;
console.log(x);
if (x > 100) {
let x = 350;
console.log(x);
}
console.log(x);
}
test();
console.log(x);
```
#### Answer:
* The output is as follows:
```
100
250
350
250
100
```
### 5. What is the difference of output between these two expressions? Give your reasons for it:
### a. 12 == “12”
#### Answer:
* The output is true.
* The == operator attempts to convert the operands to a common type before making the comparison.
* In this case, JavaScript will convert the string "12" to a number before comparing it to the number 12.
* As both operands have the same numeric value, the comparison evaluates to true
### b. 12 === “12”
#### Answer:
* The output is false.
* The === operator in JavaScript performs a strict equality comparison.
* It checks both the value and the type of the operands.
* In this case, the left operand is a number 12 and the right operand is a string "12".
* Since the types are different, the strict equality comparison will evaluate to false. 
### c. Number(12) === 12
#### Answer:
* The output is true.
*  In this expression, Number(12) explicitly converts the value 12 to a number using the Number constructor.
* The resulting value is a number.
* The strict equality comparison (===) then compares this number to the number 12.
* Since both the value and the type are identical (12 as a number), the comparison evaluates to true.
### 6. What is NaN?
#### Answer:
* NaN (Not a Number) is a unique value in JavaScript that represents an invalid or unrepresentable numeric result.
* It occurs when a mathematical operation encounters non-numeric or undefined values.
*  NaN is not equal to any other value, including itself.
*  To check if a value is NaN, you can use the isNaN() function.
*  NaN is commonly used to indicate numeric computation errors or undefined values.

















