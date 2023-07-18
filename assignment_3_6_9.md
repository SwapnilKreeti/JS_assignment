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
```
const [w1, w2, w3, w4] = "I love going walkies".split(" ");

console.log(w1);  // Output: "I"
console.log(w2);  // Output: "love"
console.log(w3);  // Output: "going"
console.log(w4);  // Output: "walkies"
```
### Given object for Questions 4, 5 (and possibly 6)
```
const myObject = {
x1: "Samba",
x2: {
x3: {
x4: {},
x5: "Rails",
},
x6: {
x7: -1,
x8: [25, 8, 4, 10]
},
}
};
```
### 4. For the given object, write a single line destructuring assignment to get these values:
### a. x3 (store result in variable name y)
#### Answer:
```
const { x2: { x3: y } } = myObject;
console.log(y);  
```
* The output is { x4: {}, x5: "Rails" }
### b. 2nd element of x8 (use any variable name for result)
#### Answer:
```
const { x2: { x6: { x8: [, secondValue] } } } = myObject;
console.log(secondValue);
```
* The output is 8
### 5. Write JS code to create another object (named newObject), which contains all attributes from the given objects, and the following key value pairs:
### a. Key: x20 Value: “Shinko”
#### Answer:
```
const myObject = {
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails",
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10]
    },
  },
};

const newObject = {
  ...myObject, // the spread operator ... is used to create a new object newObject by spreading all the attributes from myObject into it
  x20: "Shinko"
};

console.log(newObject);
```
* OUTPUT
```
{
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails"
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10]
    }
  },
  x20: "Shinko"
}
```
### b. Key: x21 Value: [5, 40, 73, 19]
#### Answer:
```
const myObject = {
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails",
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10]
    },
  },
};

const newObject = {
  ...myObject,
  x20: "Shinko",
  x21: [5, 40, 73, 19]
};

console.log(newObject);
```
* OUTPUT
```
{
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails"
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10]
    }
  },
  x20: "Shinko",
  x21: [5, 40, 73, 19]
}
```
### 6. Create a new array newArray , which combines elements from arrays stored inside attributes x8 and x21 of the object created in Q5.
#### Answer:
```
const myobject = {
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails"
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10]
    }
  },
  x20: "Shinko",
  x21: [5, 40, 73, 19]
};

const arr = [...myobject.x2.x6.x8, ...myobject.x21];

console.log(arr);
```
* The output is [25, 8, 4, 10, 5, 40, 73, 19].
### 7. For the given JS program:
```
let aRandomNum = 37;
function f1(num) {
console.log(num * 3);
}
function f2() {
aRandomNum *= 3;
console.log(aRandomNum);
}
f1(aRandomNum);
f2();
f1(aRandomNum);
```
### a. Out of the 2 functions f1 and f2, which one is pure and which one is impure? Give reasons for the conclusion.
#### Answer:
* Pure function (f1):The f1 function takes a parameter num and performs a computation by multiplying num by 3. The output of f1 solely depends on its input, making it deterministic and predictable.
* Impure function (f2): The f2 function does not take any parameters.The output of f2 depends not only on its input (which is none), but also on the current state of aRandomNum.
### b. What will be the output of the program (the 3 output values)?
#### Answer:
```
111 
111
333
```
* The first function call f1(aRandomNum):
* Input: aRandomNum = 37
* Output: 111 (result of 37 * 3)
* The second function call f2():
* Modifies the global variable aRandomNum by multiplying it by 3.
* Previous value of aRandomNum (which is 37) is multiplied by 3 to become 111.
* Output: 111 (updated value of aRandomNum)
* The third function call f1(aRandomNum):
* Input: aRandomNum (updated value) = 111
* Output: 333 (result of 111 * 3)







