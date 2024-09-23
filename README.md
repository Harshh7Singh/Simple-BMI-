# Simple-BMI-
In This I Just Used HTML,CSS and Basic JS 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMI Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        .container {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            width: 100%;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .input-group {
            margin-bottom: 1rem;
        }
        label {
            display: block;
            margin-bottom: 0.5rem;
            color: #666;
        }
        input {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        button {
            width: 100%;
            padding: 0.75rem;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #45a049;
        }
        #result {
            margin-top: 1rem;
            text-align: center;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>BMI Calculator</h1>
        <div class="input-group">
            <label for="height">Height (cm):</label>
            <input type="number" id="height" placeholder="Enter height in cm" required>
        </div>
        <div class="input-group">
            <label for="weight">Weight (kg):</label>
            <input type="number" id="weight" placeholder="Enter weight in kg" required>
        </div>
        <button onclick="calculateBMI()">Calculate BMI</button>
        <div id="result"></div>
    </div>

    <script>
        function calculateBMI() {
            const height = document.getElementById('height').value;
            const weight = document.getElementById('weight').value;
            const resultDiv = document.getElementById('result');

            if (height && weight) {
                const heightInMeters = height / 100;
                const bmi = (weight / (heightInMeters * heightInMeters)).toFixed(2);
                let category = '';

                if (bmi < 18.5) {
                    category = 'Underweight';
                } else if (bmi >= 18.5 && bmi < 25) {
                    category = 'Normal weight';
                } else if (bmi >= 25 && bmi < 30) {
                    category = 'Overweight';
                } else {
                    category = 'Obese';
                }

                resultDiv.innerHTML = `Your BMI is ${bmi}<br>Category: ${category}`;
            } else {
                resultDiv.innerHTML = 'Please enter both height and weight.';
            }
        }
    </script>
</body>
</html>
