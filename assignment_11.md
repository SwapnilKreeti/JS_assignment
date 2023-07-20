### 1. Create a button with the ID "clickMe" that, when clicked, changes the background color of the body element to red using jQuery.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Background Color</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <button id="clickMe">Click Me</button>

  <script>
    $(document).ready(function() {
      $("#clickMe").click(function() {
        $("body").css("background-color", "red");
      });
    });
  </script>
</body>
</html>
```
### 2. Write a jQuery function that takes the text inside a paragraph element with the ID "myPara" and appends it with another paragraph element with the ID "newPara" using jQuery.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Appending Paragraph Text</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <p id="myPara">This is the old paragraph.</p>
  <p id="newPara">This is the new parargraph</p>

  <script>
    $(document).ready(function() {
      const sourceText = $("#myPara").text(); 
      $("#newPara").append(sourceText); 
    });
  </script>
</body>
</html>
```
### 3. Create a form that has a text input field with the ID "myInput" and a submit button. Write a jQuery function that alerts the user with the text they entered in the input field when they click the submit button.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>Form Submission</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <form id="userForm">
    <label for="myInput">Enter text:</label>
    <input type="text" id="myInput" name="myInput" required>
    <input type="submit" value="Submit">
  </form>

  <script>
    $(document).ready(function() {
      $("#userForm").submit(function(event) {
        event.preventDefault(); /
        const enteredText = $("#myInput").val(); 
        alert("You have entered : " + enteredText); 
      });
    });
  </script>
</body>
</html>
```
#### 4. Create a list with the ID "myList" that contains five list items. Write a jQuery function to highlight the first and last list items in the list with red color.
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>List Items</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <ul id="myList">
    <li>Home</li>
    <li>About Us</li>
    <li>Services</li>
    <li>People</li>
    <li>Review</li>
  </ul>

  <script>
    $(document).ready(function() {
      $("#myList li:first-child, #myList li:last-child").css("color", "red");
    });
  </script>
</body>
</html>
```
### 5. Create an HTML table with the ID "myTable" that has three columns: Name, Age, and Occupation. Write a jQuery function that adds a new row to the table with the name - "John", age - "30", and occupation - "Developer".
#### Answer:
```
<!DOCTYPE html>
<html>
<head>
  <title>My Table</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <table id="myTable">
    <thead>
      <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Occupation</th>
      </tr>
    </thead>
    <tbody>
      
    </tbody>
  </table>

  <script>
    $(document).ready(function() {
      const name = "John";
      const age = "30";
      const occupation = "Developer";

      const newRow = "<tr><td>" + name + "</td><td>" + age + "</td><td>" + occupation + "</td></tr>";

      $("#myTable tbody").append(newRow);
    });
  </script>
</body>
</html>
```
