### 1. Write a JavaScript program that adds a new item to the list whenever a user inputs a text into the input field and clicks the button.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Add Item to the List</title>
</head>
<body>
  <input type="text" id="userInput" placeholder="Enter the item">
  <button id="addItemButton">Add Item</button>
  <ul id="itemList"></ul>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const userInput = document.getElementById('userInput');
      const addItemButton = document.getElementById('addItemButton');
      const itemList = document.getElementById('itemList');

      addItemButton.addEventListener('click', function() {
        const newItemText = userInput.value.trim();
        if (newItemText !== '') {
          const newItem = document.createElement('li');
          newItem.textContent = newItemText;
          itemList.appendChild(newItem);
          userInput.value = '';
        }
      });
    });
  </script>
</body>
</html>
```
### 2. Write a JS function to change the font size,bg-color, and font-family for the paragraph in the HTML snippet below on clicking the button.
```
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title>JS DOM paragraph styling</title>
</head>
<body>
<p id ='text'>It is a long established fact that a reader
will be distracted by the readable content of a page when
looking at its layout. </p>
<div>
<button id="jsstyle"> Style </button>
</div>
</body>
</html>
```
#### Answer:

### 3. Write a JavaScript program that calculates the area of a rectangle when the user inputs the width and height into two input fields and clicks a button.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Rectangle Area Calculator</title>
</head>
<body>
  <h2>Rectangle Area Calculator</h2>
  <label for="inputWidth">Width:</label>
  <input type="number" id="inputWidth" placeholder="Enter width" required>
  <br>
  <label for="inputHeight">Height:</label>
  <input type="number" id="inputHeight" placeholder="Enter height" required>
  <br>
  <button onclick="calculateArea()">Calculate Area</button>
  <br>
  <p id="outputResult"></p>

  <script>
    function calculateArea() {
     
      const width = parseFloat(document.getElementById("inputWidth").value);
      const height = parseFloat(document.getElementById("inputHeight").value);

      // Check if the input values are valid numbers
      if (isNaN(width) || isNaN(height)) {
        document.getElementById("outputResult").textContent = "Enter valid numbers for width and height.";
      } else {
     
        const area = width * height;
        document.getElementById("outputResult").textContent = `The area is: ${area}`;
      }
    }
  </script>
</body>
</html>
```

### 4. Write a JavaScript program that displays an alert message to the user when they submit a form.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Form Alert Submission</title>
</head>
<body>
  <form id="myForm">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>

    <input type="submit" value="Submit">
  </form>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const myForm = document.getElementById('myForm');

      myForm.addEventListener('submit', function(event) {
        event.preventDefault(); 
        alert('Form has been successfully submitted!'); 
      });
    });
  </script>
</body>
</html>
```
### 5. Write a JavaScript program that displays an alert message to the user when they resize the browser window.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Resize Window Alert</title>
</head>
<body>

  <script>
    function showCustomAlert() {
      alert('Browser window has been resized!');
    }

    window.addEventListener('resize', showCustomAlert);
  </script>
</body>
</html>
```

### 6. Write a JavaScript program that uses AJAX to fetch and display data from a text file when the user clicks on a button.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Text File Fetch using AJAX</title>
</head>
<body>
  <button id="fetchDataButton">Fetch Data</button>
  <div id="dataDisplay"></div>

  <script>
    document.getElementById('fetchDataButton').addEventListener('click', function() {
      const xhttp = new XMLHttpRequest();

      xhttp.onreadystatechange = function() {
        if (xhttp.readyState === 4) {
          if (xhttp.status === 200) {
            const dataDisplay = document.getElementById('dataDisplay');
            dataDisplay.textContent = xhttp.responseText;
          } else {
            alert('Failed to fetch data');
          }
        }
      };

      xhttp.open('GET', '1914016.pdf', true);
      xhttp.send();
    });
  </script>
</body>
</html>
```

### 7. Write a JavaScript program that uses AJAX to fetch and display an image from an API when the user clicks on a button.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Random Cat Image from an API</title>
</head>
<body>
  <h2>Random Cat Image</h2>
  <button id="fetchButton">Fetch Cat Image</button>
  <br>
  <img id="catImage" src="" alt="Random Cat Image">

  <script>
    function fetchCatImage() {
      const apiUrl = "https://aws.random.cat/meow";
      const catImageElement = document.getElementById("catImage");

      const request = new XMLHttpRequest();

      request.open("GET", apiUrl);

      request.onload = function() {
        if (request.status === 200) {
       
          const responseData = JSON.parse(request.responseText);

          const catImageUrl = responseData.file;

          catImageElement.src = catImageUrl;
        } else {
          console.error("Error fetching cat image:", request.status);
        }
      };

      request.send();
    }

    document.getElementById("fetchButton").addEventListener("click", fetchCatImage);
  </script>
</body>
</html>
```
