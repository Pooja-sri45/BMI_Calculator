# Ex06 BMI Calculator
## DATE:15/10/2025
## NAME:POOJASRI L
## REG.NO:212223220076

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
## APP.JS
```
import React, { useState } from "react";
import "./App.css";

function App() {
  const [height, setHeight] = useState("");
  const [weight, setWeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState("");

  const calculateBMI = (e) => {
    e.preventDefault();
    if (!height || !weight) {
      alert("Please enter both height and weight!");
      return;
    }

    const heightInMeters = height / 100;
    const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(1);
    setBmi(bmiValue);

    if (bmiValue < 18.5) setMessage("Underweight ⚠️");
    else if (bmiValue >= 18.5 && bmiValue < 24.9) setMessage("Normal ✅");
    else if (bmiValue >= 25 && bmiValue < 29.9) setMessage("Overweight ⚠️");
    else setMessage("Obese 🔴");
  };

  const resetForm = () => {
    setHeight("");
    setWeight("");
    setBmi(null);
    setMessage("");
  };

  return (
    <div className="container">
      <h1>BMI CALCULATOR</h1>

      <form onSubmit={calculateBMI}>
        <div className="input-group">
          <label>Weight (kg)</label>
          <input
            type="number"
            value={weight}
            onChange={(e) => setWeight(e.target.value)}
            placeholder="Enter weight"
          />
        </div>

        <div className="input-group">
          <label>Height (cm)</label>
          <input
            type="number"
            value={height}
            onChange={(e) => setHeight(e.target.value)}
            placeholder="Enter height"
          />
        </div>

        <div className="btn-container">
          <button type="submit" className="btn">Calculate</button>
          <button type="button" className="btn reset" onClick={resetForm}>
            Reset
          </button>
        </div>
      </form>

      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p>{message}</p>
        </div>
      )}

      <footer>Created by <b>PoojaSri L</b></footer>
    </div>
  );
}

export default App;

```
## APP.CSS
```
body {
  margin: 0;
  padding: 0;
  font-family: "Poppins", sans-serif;
  background: linear-gradient(135deg, #89f7fe, #66a6ff);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  background: #fff;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
  text-align: center;
  width: 330px;
}

h1 {
  color: #333;
  margin-bottom: 25px;
  letter-spacing: 1px;
}

.input-group {
  margin: 15px 0;
  text-align: left;
}

label {
  font-weight: 600;
  color: #444;
}

input {
  width: 100%;
  padding: 10px;
  margin-top: 6px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 16px;
}

.btn-container {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
}

.btn {
  background-color: #66a6ff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.3s;
  font-size: 15px;
}

.btn:hover {
  background-color: #4e89ff;
}

.reset {
  background-color: #ff5c5c;
}

.reset:hover {
  background-color: #ff3333;
}

.result {
  margin-top: 25px;
  background: #f1faff;
  padding: 20px;
  border-radius: 10px;
}

.result h2 {
  color: #333;
}

.result p {
  font-size: 18px;
  font-weight: bold;
  color: #444;
}

footer {
  margin-top: 25px;
  font-size: 14px;
  color: #666;
}

```

## OUTPUT
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/56134b3d-59a7-44b2-bb95-348b7597fd20" />
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/9d2d3cd9-ff98-4dad-82f6-85ee1fa91b74" />



## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
