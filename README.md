# cute-card
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <title>Une petite question</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(160deg, #fff1f2, #f8fafc);
      font-family: system-ui, -apple-system, "Segoe UI", sans-serif;
    }

    .card {
      width: 360px;
      background: white;
      border-radius: 24px;
      padding: 28px 26px 30px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.12);
      text-align: center;
    }

    h1 {
      font-size: 18px;
      font-weight: 600;
      margin: 0 0 8px;
    }

    .question {
      font-size: 15px;
      line-height: 1.4;
      margin-bottom: 12px;
      color: #111827;
    }

    .tease {
      font-size: 13px;
      color: #be185d;
      margin-bottom: 22px;
    }

    .meter {
      width: 100%;
      height: 10px;
      background: #fce7f3;
      border-radius: 999px;
      overflow: hidden;
      margin-bottom: 20px;
    }

    .fill {
      height: 100%;
      width: 0%;
      background: linear-gradient(90deg, #fb7185, #f472b6);
      transition: width 0.4s ease;
    }

    button {
      border: none;
      border-radius: 999px;
      padding: 11px 22px;
      font-size: 14px;
      cursor: pointer;
    }

    #yes {
      background: #fb7185;
      color: white;
      box-shadow: 0 8px 20px rgba(251,113,133,0.35);
      margin-right: 8px;
    }

    #no {
      background: none;
      color: #9f1239;
    }

    .hidden {
      display: none;
    }

    .success h1 {
      font-size: 20px;
      margin-bottom: 10px;
    }

    .success p {
      font-size: 14px;
      margin: 6px 0;
    }

    img {
      width: 210px;
      margin-top: 18px;
      border-radius: 16px;
    }
  </style>
</head>

<body>

  <!-- MAIN -->
  <div class="card" id="card">
    <h1>Sofia</h1>

    <p class="question">
      Est-ce que tu serais d’accord pour sortir avec moi ce vendredi ?
    </p>

    <p class="tease">
      Tu peux réfléchir… ou essayer « Non » 🙂
    </p>

    <div class="meter">
      <div class="fill" id="fill"></div>
    </div>

    <button id="yes">Oui</button>
    <button id="no">Non</button>
  </div>

  <!-- SUCCESS -->
  <div class="card success hidden" id="success">
    <h1>C’était évident ✨</h1>
    <p>Bonne décision.</p>
    <p>À vendredi 💗</p>

    <img src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif">
  </div>

  <script>
    let mood = 0;

    const fill = document.getElementById("fill");
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const card = document.getElementById("card");
    const success = document.getElementById("success");

    noBtn.addEventListener("click", () => {
      mood += 25;
      fill.style.width = mood + "%";

      if (mood >= 100) {
        card.classList.add("hidden");
        success.classList.remove("hidden");
      }
    });

    yesBtn.addEventListener("click", () => {
      card.classList.add("hidden");
      success.classList.remove("hidden");
    });
  </script>

</body>
</html>
