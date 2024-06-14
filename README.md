<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Marcus Brown Performance</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: royalblue;
            color: white;
            text-align: center;
            padding: 20px;
        }
        .container {
            padding: 20px;
            max-width: 800px;
            margin: auto;
        }
        .section {
            margin-bottom: 40px;
        }
        h2 {
            color: royalblue;
        }
        input[type="number"], select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            background-color: royalblue;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: darkblue;
        }
        p {
            white-space: pre-wrap;
        }
        .footer {
            text-align: center;
            padding: 10px;
            background-color: #f1f1f1;
            margin-top: 20px;
        }
        .footer a {
            color: royalblue;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <header>
        <h1>Marcus Brown Performance</h1>
        <p>@mbperformance100</p>
    </header>
    <div class="container">
        <div class="section">
            <h2>Pound to Kilogram Converter</h2>
            <input type="number" id="pounds" placeholder="Enter weight in pounds">
            <button onclick="convertWeight()">Convert to Kilograms</button>
            <p id="kilograms"></p>
        </div>
        <div class="section">
            <h2>Plate Calculator</h2>
            <p>Enter the total weight (including barbell):</p>
            <input type="number" id="totalWeight" placeholder="Total weight in kg">
            <button onclick="calculatePlates()">Calculate Plates</button>
            <p id="platesResult"></p>
        </div>
        <div class="section">
            <h2>RPE Calculator</h2>
            <p>Enter your RPE:</p>
            <input type="number" id="rpe" placeholder="RPE">
            <button onclick="calculateRPE()">Calculate</button>
            <p id="rpeResult"></p>
        </div>
        <div class="section">
            <h2>Powerlifting Commands & Techniques</h2>
            <h3>Squat:</h3>
            <p>Commands: Squat, Rack</p>
            <p>Technique: Stand with feet shoulder-width apart, barbell on your shoulders...</p>
            <h3>Bench Press:</h3>
            <p>Commands: Start, Press, Rack</p>
            <p>Technique: Lie on the bench, feet flat on the ground...</p>
            <h3>Deadlift:</h3>
            <p>Commands: Lift, Down</p>
            <p>Technique: Stand with feet hip-width apart, grip the barbell...</p>
        </div>
        <div class="section">
            <h2>Attempt Selector</h2>
            <p>Enter your goal 3rd attempt:</p>
            <input type="number" id="goalAttempt" placeholder="Goal 3rd attempt weight">
            <button onclick="calculateAttempts()">Calculate Attempts</button>
            <p id="attemptsResult"></p>
        </div>
    </div>
    <footer class="footer">
        <p>Follow us on <a href="https://www.instagram.com/mbperformance100" target="_blank">Instagram</a></p>
    </footer>
    <script>
        function convertWeight() {
            let pounds = document.getElementById("pounds").value;
            let kilograms = (pounds * 0.453592).toFixed(2);
            document.getElementById("kilograms").innerText = pounds + " lbs = " + kilograms + " kg";
        }

        function calculatePlates() {
            let totalWeight = document.getElementById("totalWeight").value;
            let barbellWeight = 20; // Assuming 20kg barbell
            let plateWeight = totalWeight - barbellWeight;
            document.getElementById("platesResult").innerText = "Plates to use: " + plateWeight + " kg";
        }

        function calculateRPE() {
            let rpe = document.getElementById("rpe").value;
            let estimatedMax = (100 - (10 - rpe) * 2.5);
            document.getElementById("rpeResult").innerText = "Estimated Max Effort: " + estimatedMax + "%";
        }

        function calculateAttempts() {
            let goalAttempt = document.getElementById("goalAttempt").value;
            let firstAttempt = (goalAttempt * 0.90).toFixed(2);
            let secondAttempt = (goalAttempt * 0.95).toFixed(2);
            let thirdAttempt = (goalAttempt * 1.00).toFixed(2);
            document.getElementById("attemptsResult").innerText = 
                "First Attempt: " + firstAttempt + " kg\n" +
                "Second Attempt: " + secondAttempt + " kg\n" +
                "Third Attempt: " + thirdAttempt + " kg";
        }
    </script>
</body>
</html>
