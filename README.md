## Weight Converter

This is a simple weight converter that converts pounds to kilograms.

### How to use

1. Clone the repository.
2. Open the `index.html` file in a web browser.
3. Enter a weight in pounds in the input field.
4. Click the "Convert" button.
5. The converted weight in kilograms will be displayed in the result field.

### Code

The code for the weight converter is very simple. The HTML file contains a form with an input field and a button. The JavaScript file contains a function that converts the weight from pounds to kilograms.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Weight Converter</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="container">
      <h1 class="heading">Weight Converter</h1>
      <div class="input-container">
        <label for="pounds">Pounds:</label>
        <input
          type="number"
          id="input"
          class="input"
          step=".1"
          placeholder="Enter number"
        />
      </div>
      <p>Your weight in kg is: <span id="result"></span></p>
      <p class="error" id="error"></p>
    </div>
    <script src="index.js"></script>
  </body>
</html>
```

```CSS
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  max-width: 500px;
  margin: auto;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.container {
  background: rgba(255, 255, 255, 0.3);
  padding: 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  width: 85%;
  max-width: 450px;
}

.input-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 18px;
  font-weight: 700;
}

.input {
  padding: 10px;
  width: 70%;
  background: rgba(255, 255, 255, 0.3);
  border-color: rgba(255, 255, 255, 0.5);
  font-size: 18px;
  border-radius: 10px;
  color: darkgreen;
  outline: none;
}

.error {
  color: red;
}

```

```javascript
const inputEl = document.getElementById("input");
const errorEl = document.getElementById("error");
const resultEl = document.getElementById("result");
let errorTime;
let resultTime;
function updateResults() {
  if (inputEl.value <= 0 || isNaN(inputEl.value)) {
    errorEl.innerText = "Please enter a valid number!";
    clearTimeout(errorTime);
    errorTime = setTimeout(() => {
      errorEl.innerText = "";
      inputEl.value = "";
    }, 2000);
  } else {
    resultEl.innerText = (+inputEl.value / 2.2).toFixed(2);
    clearTimeout(resultTime);
    resultTime = setTimeout(() => {
      resultEl.innerText = "";
      inputEl.value = "";
    }, 10000);
  }
}

inputEl.addEventListener("input", updateResults);
```
