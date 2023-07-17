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


















