### 1) Create a Class AlertBox.
### AlertBox:
### Constructor:
### take 1 variable(applicationName) and store it as an instance variable.
### Methods:
### showAlertBox(message) which shows an alert dialog with the message
### In format “{applicationName}: {message}”.
### ii) Create a new instance of AlertBox and show a message.
#### Answer:
```
class AlertBox {
  constructor(applicationName) {
    this.applicationName = applicationName;
  }

  showAlertBox(message) {
    const formattedMessage = `${this.applicationName}: ${message}`;
    alert(formattedMessage);
  }
}

const myBox = new AlertBox("ABC Application");
myBox.showAlertBox("Servers are busy");
```
### 2) Create a new class SuccessMessage which extends AlertBox. Override the showAlertBox method.
### SuccessMessage <- AlertBox
### showAlertBox(message) - shows alert messages in this format. “{applicationName}:
### Success: {message}”.
### Create a new instance of SuccessMessage and call the showAlertBox method.
#### Answer:
```
class AlertBox {
  constructor(applicationName) {
    this.applicationName = applicationName;
  }

  showAlertBox(message) {
    const formattedMessage = `${this.applicationName}: ${message}`;
    alert(formattedMessage);
  }
}

class SuccessMessage extends AlertBox {
  showAlertBox(message) {
    const formattedMessage = `${this.applicationName}: Success: ${message}`;
    alert(formattedMessage);
  }
}

const myMsg = new SuccessMessage("ABC Application");
myMsg.showAlertBox("Execution is successfull");
```
### 3) What is inheritance and prototypes? Can you achieve inheritance using prototypes? If yes, how?
#### Answer:
* Inheritance: Inheritance is a mechanism that allows objects to inherit properties and methods from other objects. It is a way to create a hierarchy of objects where a derived object (child) can inherit the properties and behaviors of a base object (parent).
* Prototypes: Prototypes are a fundamental part of JavaScript's inheritance mechanism. Every JavaScript object has a prototype, which serves as a blueprint for creating new objects. The prototype object contains properties and methods that are shared among all instances created from it. 
