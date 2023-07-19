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

