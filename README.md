# Simple-Calculator-with-React

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
Calculator.js
```
import React, { useState } from "react";
import "./Calculator.css";

const Calculator = () => {
  const [input, setInput] = useState("");

  // Append numbers/operators
  const handleClick = (value) => {
    setInput((prev) => prev + value);
  };

  // Clear all input
  const handleClear = () => {
    setInput("");
  };

  // Delete last character
  const handleBackspace = () => {
    setInput(input.slice(0, -1));
  };

  // Evaluate the expression safely
  const handleCalculate = () => {
    try {
      const result = eval(input); // simple for demo (avoid in prod)
      setInput(result.toString());
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator-container">
      <div className="display">{input || "0"}</div>
      <div className="buttons">
        <button onClick={handleClear} className="span-two">C</button>
        <button onClick={handleBackspace}>⌫</button>
        <button onClick={() => handleClick("/")}>÷</button>

        <button onClick={() => handleClick("7")}>7</button>
        <button onClick={() => handleClick("8")}>8</button>
        <button onClick={() => handleClick("9")}>9</button>
        <button onClick={() => handleClick("*")}>×</button>

        <button onClick={() => handleClick("4")}>4</button>
        <button onClick={() => handleClick("5")}>5</button>
        <button onClick={() => handleClick("6")}>6</button>
        <button onClick={() => handleClick("-")}>−</button>

        <button onClick={() => handleClick("1")}>1</button>
        <button onClick={() => handleClick("2")}>2</button>
        <button onClick={() => handleClick("3")}>3</button>
        <button onClick={() => handleClick("+")}>+</button>

        <button onClick={() => handleClick("0")} className="span-two">0</button>
        <button onClick={() => handleClick(".")}>.</button>
        <button onClick={handleCalculate}>=</button>
      </div>
    </div>
  );
};

export default Calculator;
```
Calculator.css
```

.calculator-container {
  width: 300px;
  background: #1e1e2f;
  border-radius: 15px;
  padding: 20px;
  margin: 60px auto;
  box-shadow: 0 8px 20px rgba(0,0,0,0.3);
  display: flex;
  flex-direction: column;
  align-items: center;
}

.display {
  width: 100%;
  height: 60px;
  background: #000;
  color: #0ff;
  text-align: right;
  font-size: 2rem;
  padding: 10px;
  border-radius: 8px;
  margin-bottom: 15px;
  overflow-x: auto;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  width: 100%;
}

button {
  background: #3b3b4f;
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1.2rem;
  padding: 15px;
  cursor: pointer;
  transition: background 0.2s;
}

button:hover {
  background: #5b5b7f;
}

button:active {
  background: #7777a8;
}

.span-two {
  grid-column: span 2;
}

@media (max-width: 400px) {
  .calculator-container {
    width: 90%;
  }
  .display {
    font-size: 1.5rem;
  }
  button {
    padding: 12px;
    font-size: 1rem;
  }
}
```
App.js
```
import React from "react";
import Calculator from "./components/Calculator";

function App() {
  return (
    <div>
      <h1 style={{ textAlign: "center", marginTop: "20px" }}>React Calculator</h1>
      <Calculator />
    </div>
  );
}

export default App;
```



## OUTPUT

<img width="1009" height="491" alt="image" src="https://github.com/user-attachments/assets/a446cac0-d83a-4f4d-afe2-eea7161cd0b6" />



## RESULT
The program for developing a simple calculator in React.js is executed successfully.
