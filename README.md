<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Advanced Percentage Calculator</title>
  <style>
    /* General Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Arial', sans-serif;
    }

    body {
      background: linear-gradient(135deg, #6a11cb, #2575fc);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      color: #fff;
    }

    .calculator {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      border-radius: 15px;
      padding: 2rem;
      width: 100%;
      max-width: 400px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
    }

    h1 {
      text-align: center;
      margin-bottom: 1.5rem;
      font-size: 1.8rem;
      font-weight: 600;
    }

    .input-group {
      margin-bottom: 1.5rem;
    }

    .input-group label {
      display: block;
      margin-bottom: 0.5rem;
      font-size: 1rem;
      font-weight: 500;
    }

    .input-group input {
      width: 100%;
      padding: 0.8rem;
      border: none;
      border-radius: 8px;
      background: rgba(255, 255, 255, 0.2);
      color: #fff;
      font-size: 1rem;
      outline: none;
    }

    .input-group input::placeholder {
      color: rgba(255, 255, 255, 0.7);
    }

    .input-group input:focus {
      background: rgba(255, 255, 255, 0.3);
    }

    .button-group {
      display: flex;
      justify-content: space-between;
      gap: 1rem;
    }

    .button-group button {
      flex: 1;
      padding: 0.8rem;
      border: none;
      border-radius: 8px;
      background: #2575fc;
      color: #fff;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    .button-group button:hover {
      background: #1b5fd9;
    }

    .result {
      margin-top: 1.5rem;
      text-align: center;
      font-size: 1.2rem;
      font-weight: 600;
    }

    .result span {
      color: #ffeb3b;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <h1>Advanced Percentage Calculator</h1>
    <div class="input-group">
      <label for="number">Enter Number:</label>
      <input type="number" id="number" placeholder="Enter a number">
    </div>
    <div class="input-group">
      <label for="percentage">Enter Percentage:</label>
      <input type="number" id="percentage" placeholder="Enter percentage">
    </div>
    <div class="button-group">
      <button onclick="calculatePercentage()">Calculate Percentage</button>
      <button onclick="calculateIncrease()">Increase by Percentage</button>
      <button onclick="calculateDecrease()">Decrease by Percentage</button>
    </div>
    <div class="result">
      <p>Result: <span id="result">0</span></p>
    </div>
  </div>

  <script>
    function calculatePercentage() {
      const number = parseFloat(document.getElementById('number').value);
      const percentage = parseFloat(document.getElementById('percentage').value);
      if (isNaN(number) || isNaN(percentage)) {
        alert('Please enter valid numbers.');
        return;
      }
      const result = (number * percentage) / 100;
      document.getElementById('result').textContent = result.toFixed(2);
    }

    function calculateIncrease() {
      const number = parseFloat(document.getElementById('number').value);
      const percentage = parseFloat(document.getElementById('percentage').value);
      if (isNaN(number) || isNaN(percentage)) {
        alert('Please enter valid numbers.');
        return;
      }
      const result = number + (number * percentage) / 100;
      document.getElementById('result').textContent = result.toFixed(2);
    }

    function calculateDecrease() {
      const number = parseFloat(document.getElementById('number').value);
      const percentage = parseFloat(document.getElementById('percentage').value);
      if (isNaN(number) || isNaN(percentage)) {
        alert('Please enter valid numbers.');
        return;
      }
      const result = number - (number * percentage) / 100;
      document.getElementById('result').textContent = result.toFixed(2);
    }
  </script>
</body>
</html>
