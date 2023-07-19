### 1. Define ‘Asynchronous programming’.
#### Answer:
* Asynchronous programming in JavaScript is a programming approach that allows tasks to run concurrently without blocking the main program's execution.
* Instead of waiting for each task to complete before moving to the next one, asynchronous programming enables tasks to start and run in the background while other operations continue.
* This is useful for handling time-consuming operations like network requests or file I/O without freezing the entire program.
* By utilizing asynchronous programming techniques, JavaScript applications can efficiently handle time-consuming tasks without blocking the program's execution.
* This enables the creation of more scalable and responsive applications, particularly when dealing with tasks that involve waiting for results, such as network communication or file operations.
### 2. What are callbacks? Give an example.
#### Answer:
* Callbacks are functions that are passed as arguments to other functions and are invoked once a certain task or operation is completed.
* They allow for the execution of code after an asynchronous operation finishes, ensuring that the program continues running without waiting for the result.
```
function fetchDataAsync(callback) {
  setTimeout(() => {
    const result = 'New fetched data';
    callback(result); 
  }, 2000); 
}

function handleData(result) {
  console.log('Received data:', result);
}

fetchDataAsync(handleData);
```
### 3. What is a promise? What are its different states? Also write the methods which change a promise to their corresponding states.
#### Answer:
* A promise in JavaScript is an object that represents the eventual completion or failure of an asynchronous operation and the resulting value. It offers a cleaner and more structured approach for handling asynchronous tasks compared to using callbacks.

A promise can exist in one of the following three states:

* Pending: This is the initial state of a promise. It signifies that the associated asynchronous operation is still in progress, and the promise has not yet been fulfilled or rejected.
* Fulfilled: When a promise successfully completes its operation, it transitions to the fulfilled state. This indicates that the promised task has been successfully accomplished, and the resulting value is available for further processing.
* Rejected: If an error occurs during the asynchronous operation, the promise transitions to the rejected state. This state signifies that the promised task has encountered a failure, and an error or reason for the failure is provided.
```
const customPromise = new Promise((resolve, reject) => {
  
  setTimeout(() => {
    const randomNumber = Math.random();
    if (randomNumber < 0.5) {
      resolve(randomNumber); 
    } else {
      reject(new Error('Promise rejected')); 
    }
  }, 2000); 
});

customPromise
  .then((value) => {
    console.log('Promise fulfilled with result:', value);
  })
  .catch((error) => {
    console.log('Promise rejected with error:', error.message);
  });
```
### 4. Write a JS promise which resolves after 5s, with a value of “Hello Javascript”. Also, write code to print the length of this string after resolving.
#### Answer:
```
const customPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Hello Javascript");
  }, 5000); 
});

customPromise
  .then((value) => {
    console.log("Resolved value:", value);
    console.log("Resolved string's length:", value.length);
  })
  .catch((error) => {
    console.error("Promise rejected with error:", error);
  });
```
### 5. What is ‘callback hell’ problem? How does the use of promises help in reducing this?
#### Answer:
* Callback hell, also known as the "pyramid of doom," refers to the problem of dealing with multiple nested callbacks in asynchronous JavaScript code. It occurs when callbacks are deeply nested, leading to complex and unreadable code. Promises help alleviate this problem by offering a more structured and manageable approach to asynchronous code.
* Promises improve code readability by allowing the chaining of asynchronous operations using the then() method, reducing excessive indentation and creating a more linear and understandable code structure. They enable sequential execution of tasks by ensuring that subsequent tasks wait for the previous ones to complete successfully, eliminating the need for deeply nested callbacks.
* Promises also provide dedicated error handling through the catch() method, simplifying error management by centralizing error handling code. Additionally, promise composition methods such as Promise.all() and Promise.race() offer powerful ways to work with multiple promises concurrently or select the first resolved promise.
* Furthermore, the async/await syntax can be used with promises to write asynchronous code in a synchronous-like manner, further enhancing code readability and maintainability.
### 6. What is the difference between Promise.all() and Promise.allSettled()? Give an example.
#### Answer:
* Promise.all(): This method takes an array of promises as input and returns a new promise. The returned promise fulfills when all the input promises fulfill, or rejects as soon as any of the input promises reject. The fulfillment value is an array of the resolved values from the input promises, in the same order as the input.
* The output is ['Promise 1', 'Promise 2', 'Promise 3']
```
const p1 = Promise.resolve('Promise 1');
const p2 = Promise.resolve('Promise 2');
const p3 = Promise.resolve('Promise 3');

Promise.all([p1, p2, p3])
  .then((values) => {
    console.log(values); 
  })
  .catch((error) => {
    console.error(error); // Not called in this example
  });
```
* OUTPUT
```
['Promise 1', 'Promise 2', 'Promise 3']
```
* Promise.allSettled(): This method also takes an array of promises as input and returns a new promise. The returned promise fulfills with an array of objects representing the outcomes of the input promises, whether fulfilled or rejected. Each object contains a status property indicating either "fulfilled" or "rejected", and a value property holding the resolved value or a reason property holding the rejection reason.
```
const p1 = Promise.resolve('Promise 1');
const p2 = Promise.reject(new Error('Error occurred'));
const p3 = Promise.resolve('Promise 3');

Promise.allSettled([p1, p2, p3])
  .then((results) => {
    console.log(results);
  });
```
* OUTPUT
```
 [
      { status: 'fulfilled', value: 'Promise 1' },
      { status: 'rejected', reason: Error: Error occurred },
      { status: 'fulfilled', value: 'Promise 3' }
 ]
```
### 7. Write a JS function that throws a SyntaxError if the value age (passed as parameter of the function) is greater than 80. The error message will be “You are too old.”
#### Answer:
```
function check_Age(age) {
  if (age > 80) {
    throw new SyntaxError('You are too old.');
  }
}

try {
  check_Age(90);
} catch (error) {
  console.error(error.message); 
}
```
* The output is You are too old.
### 8. For this code, answer the following:
```
const p1 = Promise.any([
new Promise((resolve, reject) => setTimeout(() => reject(“Part 1 is
rejected.”), 2000)),
new Promise((resolve, reject) => setTimeout(() => resolve(“Part 2 is
resolved.”), 5000)),
]);
p1.then((res) => console.log(res))
```
### a. Write the output of this code. Briefly explain the reasoning.
#### Answer:
* OUTPUT
```
Part 2 is resolved.
```
* The reason is that the "Part 2 is resolved." promise has a longer delay of 5000 milliseconds compared to the "Part 1 is rejected." promise's delay of 2000 milliseconds. Therefore, it will resolve first, and Promise.any() will fulfill with the resolved value.

### b. What will be the output of this code if Promise.any() is replaced by Promise.race()? Is the output for this case generated faster or slower? Give reasons.
#### Answer:
* OUTPUT
```
Part 1 is rejected.
```
* The output in this case is determined by the behavior of the Promise.race() method. Promise.race() compares the execution time of the promises provided as arguments and returns the result of the fastest one. In the given code, the first promise, with a timeout of 2 seconds, is the fastest. As a result, the output "Part 1 is rejected." is generated after approximately 2 seconds, corresponding to the rejection of the first promise.
### 9. Given is a code snippet.
```
const p = new Promise((resolve, reject) => {
resolve(“Part a”);
resolve(“Part b”);
})
p.then((res)=>console.log(res));
```
### a. What will be the output of the above? Justify your answer.
#### Answer:
```
Part a
```
* The reason is that when a promise is resolved with the resolve() function, it transitions to the fulfilled state and triggers the then() method callback. However, a promise can only be resolved once, and subsequent resolve() calls have no effect.
* In the given code, a new promise p is created with the new Promise() constructor. Inside the promise executor function, two consecutive resolve() calls are made. However, only the first resolve() call is effective, resolving the promise with the value "Part a".
* When the promise p is fulfilled, the then() method callback is triggered. It receives the resolved value as the res parameter. In this case, the console.log(res) statement inside the then() callback will log "Part a" to the console.
* The second resolve() call, which resolves the promise with "Part b", is ignored since the promise was already resolved with "Part a". Therefore, "Part b" is not part of the output.

### b. What code should we write to get both the resolved results.
#### Answer:
```
const p = new Promise((resolve, reject) => {
  const results = [];
  results.push("Part a");
  results.push("Part b");
  resolve(results);
});

p.then((res) => {
  console.log(res[0]); 
  console.log(res[1]); 
});
```
* OUTPUT
```
Part a
Part b
```
### 10. Using async / await syntax, and fetch(), make an API request to ``` https://official-joke-api.appspot.com/random_joke ``` and console the results. Also handle errors if any.
#### Answer:
```
async function fetchRandomJoke() {
  try {
    const response = await fetch('https://official-joke-api.appspot.com/random_joke');
    if (!response.ok) {
      throw new Error('Failed to fetch joke');
    }
    const jokeData = await response.json();
    console.log('Random Joke:', jokeData);
  } catch (error) {
    console.error('Error:', error.message);
  }
}

fetchRandomJoke();
```



