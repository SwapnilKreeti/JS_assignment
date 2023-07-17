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

