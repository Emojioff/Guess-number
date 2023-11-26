# Guess-number
<!DOCTYPE html>
<html>
<head>
  <title>Jeu de devinette</title>
  <style>
    body {
      text-align: center;
      padding: 50px;
      font-family: Arial, sans-serif;
    }
  </style>
</head>
<body>
  <h1>Jeu de devinette</h1>
  <p>Devinez un nombre entre 1 et 100 :</p>
  <input type="number" id="guess" min="1" max="100">
  <button onclick="checkGuess()">Vérifier</button>
  <p id="result"></p>

  <script>
    // Générer un nombre aléatoire entre 1 et 100
    const randomNumber = Math.floor(Math.random() * 100) + 1;
    let attempts = 0;

    function checkGuess() {
      // Obtenir la valeur devinée
      const guess = parseInt(document.getElementById("guess").value);

      // Vérifier la devinette
      if (guess === randomNumber) {
        document.getElementById("result").innerHTML = `Bravo! Vous avez deviné le bon nombre en ${attempts} tentative(s).`;
        document.getElementById("guess").disabled = true;
      } else if (guess < randomNumber) {
        document.getElementById("result").innerHTML = "Le nombre à deviner est plus grand.";
      } else {
        document.getElementById("result").innerHTML = "Le nombre à deviner est plus petit.";
      }

      // Augmenter le nombre de tentatives
      attempts++;
    }
  </script>
</body>
</html>
