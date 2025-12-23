<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Jeu de devinette</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f0f0f0;
            padding: 50px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin-top: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>🎲 Jeu de devinette</h1>
    <p>Devine le nombre entre 1 et 10 !</p>
    <input type="number" id="guess" min="1" max="10" placeholder="Ton nombre">
    <br>
    <button onclick="playGame()">Vérifier</button>
    <p id="result"></p>

    <script>
        function playGame() {
            const secret = Math.floor(Math.random() * 10) + 1;
            const guess = Number(document.getElementById('guess').value);
            const result = document.getElementById('result');

            if (!guess) {
                result.textContent = "⚠️ Entre un nombre !";
            } else if (guess === secret) {
                result.textContent = "🎉 Bravo ! Tu as trouvé le nombre " + secret;
            } else {
                result.textContent = "❌ Non ! Le nombre était " + secret;
            }
        }
    </script>
</body>
</html>
