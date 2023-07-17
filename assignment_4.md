### 1. Given a string “Azad Ram Madiha Yash”. Return a string with the first letter of every word from the string. (Use built in methods).
#### Answer:
```
const input = "Azad Ram Madiha Yash";
const first = input.split(' ').map(word => word.charAt(0));
const final = first.join('');

console.log(final);
```
### 2. Given an array [1, -4, 12, 0, -3, 29, -150]. Calculate the sum of all positive numbers (use built in array methods).
#### Answer:
```
const arr = [1, -4, 12, 0, -3, 29, -150];

const result = arr.reduce((accumulator, currentValue) =>
{
  if (currentValue > 0)
  {
    return accumulator + currentValue;
  }
  else
  {
    return accumulator;
  }
}, 0);

console.log(result);
```
### 3. Given an array [1, 2, 3, 4, 5]. Create a new array with the square of each element(use built in array methods).
#### Answer:
```
const arr1 = [1, 2, 3, 4, 5];

const arr2 = arr1.map(num => num * num);

console.log(arr2);
```
### 4. Given an array [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name:'Vice-president James' }, { id: 3016, name: 'House-captain Otis' }, { id:4818, name: 'Prefect Finneas' }]. Create an array containing just the id ofevery individual. (write two solution one using iterator and another using built-in method)
#### Answer:
```
