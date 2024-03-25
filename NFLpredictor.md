---
title: NFL Simulator
layout: post
permalink: /NFL
type: tangibles
courses: { compsci: { week: 11 } }
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NFL Game Prediction</title>
</head>
<body>
    <form id="nflForm">
        <label for="team1">Team 1:</label>
        <input type="text" id="team1" name="team1" required><br><br>
        <label for="team2">Team 2:</label>
        <input type="text" id="team2" name="team2" required><br><br>
        <button type="button" onclick="predictWinner()">Predict Winner</button>
    </form>
    <div id="result"></div>

    <script>
        function predictWinner() {
            var form = document.getElementById('nflForm');
            var team1 = document.getElementById('team1').value;
            var team2 = document.getElementById('team2').value;
            var resultDiv = document.getElementById('result');

            fetch('http://localhost:8084/api/NFL/predict', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'Accept': 'application/json'
                },
                body: JSON.stringify({ "team1": team1, "team2": team2 })
            })
            .then(response => response.json())
            .then(data => {
                resultDiv.innerHTML = '<h2>Predicted Likelihood of Winning</h2>';
                resultDiv.innerHTML += '<p>' + team1 + ': ' + data[team1] + '%</p>';
                resultDiv.innerHTML += '<p>' + team2 + ': ' + data[team2] + '%</p>';
            })
            .catch(error => {
                console.error('Error:', error);
            });
        }
    </script>
</body>
</html>
