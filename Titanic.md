---
title: Titanic Simulator
layout: post
permalink: /titanic
type: tangibles
courses: { compsci: { week: 11 } }
---

<style>
    body {
        background-color: #f3f3f3;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        margin: 0;
        padding: 0;
    }

    h1 {
        color: #3a3a3a;
        text-transform: uppercase;
        margin-top: 20px;
        text-align: center;
        font-size: 2.5em;
        /* Add a fancy text shadow */
        text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
    }

    form {
        background-color: #ffffff;
        max-width: 500px;
        margin: 20px auto;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        /* Add a subtle animation */
        transition: transform 0.3s ease;
        /* Add a fancy gold border */
        border: 2px solid gold;
    }

    label {
        display: block;
        margin-bottom: 5px;
        color: #3a3a3a;
        font-size: 1.1em;
    }

    input[type="text"],
    input[type="number"],
    select {
        width: 100%;
        padding: 10px;
        margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        box-sizing: border-box;
        font-size: 1em;
        /* Add a nice border glow on focus */
        outline: none;
        box-shadow: 0 0 5px rgba(76, 175, 80, 0.5);
    }

    button {
        background-color: #9fa265;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1.1em;
        transition: background-color 0.3s ease;
    }

    button:hover {
        background-color: #45a049;
        /* Slightly darken the hover color */
        filter: brightness(1.1);
    }

    #result {
        margin-top: 20px;
        background-color: #ffffff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        text-align: center;
    }

    #result h2 {
        color: #3a3a3a;
        margin-bottom: 10px;
        font-size: 1.5em;
    }

    #result h3 {
        color: #ff0000;
        font-size: 1.2em;
    }

    /* Add some fancy text styles */
    p1 {
        color: #000000;
        font-weight: bold;
        font-style: italic;
    }

    p {
        color: #ffffff;
        /* Add a gradient background */
        background: linear-gradient(45deg, #4caf50, #45a049);
        padding: 10px;
        border-radius: 5px;
    }

    audio {
        margin-top: 20px;
        display: block;
        margin-left: auto;
        margin-right: auto;
    }
</style>



<body>
    <img src="Screenshot 2024-03-20 at 12.25.24 AM.png" alt="something">
    <form id="titanicForm">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required><br><br>
        <label for="pclass">Passenger Class:</label>
        <select id="pclass" name="pclass" required>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
        </select><br><br>
        <label for="sex">Gender (There are only two):</label>
        <select id="sex" name="sex" required>
            <option value="male">Male</option>
            <option value="female">Female</option>
        </select><br><br>
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" required><br><br>
        <label for="sibsp">Siblings/Spouses Aboard:</label>
        <input type="number" id="sibsp" name="sibsp" required><br><br>
        <label for="parch">Parents/Children Aboard:</label>
        <input type="number" id="parch" name="parch" required><br><br>
        <label for="fare">Price of Ticket:</label>
        <input type="number" id="fare" name="fare" required><br><br>
        <label for="embarked">City Left From:</label>
        <select id="embarked" name="embarked" required>
            <option value="C">Cherbourg</option>
            <option value="Q">Queenstown</option>
            <option value="S">Southampton</option>
        </select><br><br>
        <label for="alone">Alone:</label>
        <input type="checkbox" id="alone" name="alone"><br><br>
        <button type="button" onclick="predictSurvival()">Will You Live????</button>
    </form>
    <div id="result"></div>
    <script>
    function predictSurvival() {
        var form = document.getElementById('titanicForm');
        var name = document.getElementById('name');
        var resultDiv = document.getElementById('result');
        var formData = new FormData(form);
        fetch('http://localhost:8084/api/titanic/predict', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Accept': 'application/json'
            },
            body: JSON.stringify(Object.fromEntries(formData))
        })
        .then(response => response.json())
        .then(data => {
            resultDiv.innerHTML = '<h2>Prediction Result for ' + name.value + '</h2>';
            for (var key in data) {
                resultDiv.innerHTML += '<p1>' + key + ': ' + data[key] + '</p1>';
            }
            var deathProbability = parseFloat(data['Death probability']);
            var survivalProbability = parseFloat(data['Survival probability']);
            console.log(survivalPrabability);
            if (survivalProbability > deathProbability) {
                resultDiv.innerHTML += '<h3>Congrats You Most Likely Didnt Die!!!</h3>';
            } else {
                resultDiv.innerHTML += '<h3>Youre probably dead my boy :( WOMP WOMP</h3>';
            }
        })
        .catch(error => {
            console.error('Error:', error);
        });
    }
    </script>
</body>
