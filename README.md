# Ex06 BMI Calculator
## Date: 20/05/2026

## AIM
To develop a responsive and interactive Body Mass Index (BMI) Calculator using React that allows users to input their height and weight, and calculates their BMI to categorize their health status (e.g., Underweight, Normal, Overweight, Obese).

## DESIGN STEPS

### STEP 1: Initialize React Project

<li>Create a new React app using create-react-app.</li>
<li>Install React Router using:</li>
npm install react-router-dom

### STEP 2: Set Up Routing

Create routing structure with react-router-dom:

<li>Home route (/) – Intro or Navigation</li>

<li>BMI Calculator route (/bmi)</li>

<li>Result route (/result)</li>

### STEP 3: Design the BMI Form Page

<li>Create a form to accept Height (in cm or m) and Weight (in kg).</li>

<li>On form submit, navigate to the result page with entered values via URL query params or context/state.</li>

## STEP 4: Handle Input Validation

<li>Check if height and weight are valid numbers.</li>

<li>Optionally, show error messages for invalid inputs.</li>

### STEP 5: Perform BMI Calculation

<li>In the result component:

<li>Extract height and weight from the route (URL or passed state).</li>

<li>Apply the BMI formula:</li>

![image](https://github.com/user-attachments/assets/ec785506-c96b-489e-8783-fb1a5d36101a)
​
 
<li>Convert height from cm to m if needed.</li></li>

### STEP 6: Display Result

<li>Show calculated BMI.</li>

<li>Show category based on BMI range:

<li>Underweight, Normal, Overweight, Obese, etc.</li></li>

### STEP 7: Navigation Options

<li>Provide a button to go back to the BMI form to calculate again.</li>

### STEP 8: Enhancements

<li>Add styling using CSS or Tailwind.</li>

## PROGRAM

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Glassmorphism BMI Calculator</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Verdana, sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ff9a9e,#fad0c4,#fad0c4);
}

.container{
    width:380px;
    padding:35px;
    border-radius:25px;
    background:rgba(255,255,255,0.2);
    backdrop-filter:blur(12px);
    box-shadow:0 8px 32px rgba(0,0,0,0.2);
    text-align:center;
    color:white;
}

.container h1{
    margin-bottom:25px;
    font-size:32px;
}

.input-box{
    margin:18px 0;
}

input{
    width:100%;
    padding:14px;
    border:none;
    border-radius:12px;
    outline:none;
    font-size:16px;
    background:rgba(255,255,255,0.3);
    color:#333;
}

input::placeholder{
    color:#555;
}

button{
    width:100%;
    padding:14px;
    border:none;
    border-radius:12px;
    margin-top:15px;
    background:#ffffff;
    color:#ff4b6e;
    font-size:18px;
    font-weight:bold;
    cursor:pointer;
    transition:0.3s;
}

button:hover{
    transform:scale(1.05);
}

#result{
    margin-top:25px;
    padding:18px;
    border-radius:15px;
    background:rgba(255,255,255,0.25);
    display:none;
}

#bmi{
    font-size:40px;
    font-weight:bold;
    margin:10px 0;
}

#status{
    font-size:24px;
    font-weight:bold;
}

</style>

</head>

<body>

<div class="container">

    <h1>🌸 BMI Calculator</h1>

    <div class="input-box">
        <input type="number" id="weight" placeholder="Enter Weight in KG">
    </div>

    <div class="input-box">
        <input type="number" id="height" placeholder="Enter Height in CM">
    </div>

    <button onclick="calculateBMI()">Check BMI</button>

    <div id="result">
        <p>Your BMI</p>
        <div id="bmi">0</div>
        <div id="status"></div>
    </div>

</div>

<script>

function calculateBMI(){

    let weight = document.getElementById("weight").value;
    let height = document.getElementById("height").value;

    if(weight==="" || height===""){
        alert("Please enter all values");
        return;
    }

    let meter = height / 100;

    let bmi = (weight / (meter * meter)).toFixed(2);

    let status = "";

    if(bmi < 18.5){
        status = "Underweight 😔";
    }

    else if(bmi >= 18.5 && bmi < 24.9){
        status = "Normal Weight 😊";
    }

    else if(bmi >= 25 && bmi < 29.9){
        status = "Overweight 😐";
    }

    else{
        status = "Obesity ⚠️";
    }

    document.getElementById("result").style.display="block";

    document.getElementById("bmi").innerHTML = bmi;

    document.getElementById("status").innerHTML = status;
}

</script>

</body>
</html>
```


## OUTPUT

<img width="1911" height="906" alt="image" src="https://github.com/user-attachments/assets/34de7292-9186-432f-82cd-6bf464993974" />

<img width="1911" height="912" alt="image" src="https://github.com/user-attachments/assets/75684c60-994e-4818-984a-796e9977bb97" />

<img width="1905" height="917" alt="image" src="https://github.com/user-attachments/assets/023d37a4-094e-4c56-9773-676473ee3342" />

<img width="1903" height="912" alt="image" src="https://github.com/user-attachments/assets/fe0864c3-b8ea-4ce8-b7b1-11dee83dcfe5" />


## RESULT

The BMI Calculator successfully takes user input for height and weight, performs the BMI calculation in real-time using React state and event handling, and displays the BMI value along with the corresponding health category.
