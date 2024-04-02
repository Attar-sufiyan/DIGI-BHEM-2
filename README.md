# DIGI-BHEM-2
CREATING HOTEL BOOKING REGISTRATION FORM BY USING HTML,CSS,JAVASCRPT


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Arial', sans-serif;
      margin: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      background-color: #f0f0f0;
      color: #333;
      transition: background-color 0.3s, color 0.3s;
    }

    #calculator {
      background-color: #fff;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      overflow: hidden;
      max-width: 300px;
      width: 100%;
      text-align: center;
    }

    #display {
      width: 100%;
      height: 40px;
      font-size: 18px;
      text-align: right;
      padding: 5px;
      box-sizing: border-box;
      border: none;
      outline: none;
    }

    .button {
      width: 20%;
      height: 40px;
      font-size: 16px;
      border: none;
      outline: none;
      cursor: pointer;
    }

    .row {
      display: flex;
    }

    .operator {
      background-color: #ff9900;
      color: white;
    }

    .equals {
      background-color: #4caf50;
      color: white;
    }

    .dark-mode {
      background-color: #333;
      color: #fff;
    }
  </style>
  <title>NCALC-CASIO Like Calculator</title>
</head>
<body>
  <div id="calculator">
    <input type="text" id="display" readonly>
    <div class="row">
      <button class="button">7</button>
      <button class="button">8</button>
      <button class="button">9</button>
      <button class="button operator">/</button>
    </div>
    <div class="row">
      <button class="button">4</button>
      <button class="button">5</button>
      <button class="button">6</button>
      <button class="button operator">*</button>
    </div>
    <div class="row">
      <button class="button">1</button>
      <button class="button">2</button>
      <button class="button">3</button>
      <button class="button operator">-</button>
    </div>
    <div class="row">
      <button class="button">0</button>
      <button class="button">.</button>
      <button class="button equals">=</button>
      <button class="button operator">+</button>
    </div>
    <div class="row">
      <button class="button dark-mode">Dark Mode</button>
    </div>
  </div>

  <script>
    let displayValue = "";
    let darkMode = false;

    function toggleDarkMode() {
      darkMode = !darkMode;
      document.getElementById("calculator").classList.toggle("dark-mode", darkMode);
      document.body.style.backgroundColor = darkMode ? "#222" : "#f0f0f0";
      document.body.style.color = darkMode ? "#fff" : "#333";
    }

    document.getElementById("calculator").addEventListener("click", function (event) {
      if (event.target.matches("button")) {
        const buttonValue = event.target.innerText;
        if (buttonValue === "=") {
          try {
            displayValue = eval(displayValue).toString();
          } catch (error) {
            displayValue = "Error";
          }
        } else if (buttonValue === "Dark Mode") {
          toggleDarkMode();
        } else {
          displayValue += buttonValue;
        }
        document.getElementById("display").value = displayValue;
      }
    });
  </script>
</body>
</html>
