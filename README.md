# cute-card
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <title>Une décision importante 💗</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: radial-gradient(circle at top, #fff1f2, #fdf2f8);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: system-ui, -apple-system, sans-serif;
    }

    .scene {
      width: 380px;
      background: white;
      border-radius: 30px;
      padding: 35px;
      box-shadow: 0 25px 60px rgba(0,0,0,0.15);
      text-align: center;
    }

    h1 {
      font-size: 22px;
      margin-bottom: 10px;
    }

    .text {
      font-size: 16px;
      margin-bottom: 20px;
    }

    .meter {
      width: 100%;
      height: 14px;
      background: #fce7f3;
      border-radius: 999px;
      overflow: hidden;
      margin-bottom: 10px;
    }

    .fill {
      height: 100%;
      width: 0%;
      background: linear-gradient(90deg, #fb7185, #f472b6);
      transition: width 0.4s ease;
    }

    .meter-text {
      font-size: 13px;
      color: #be185d;
      margin-bottom: 25px;
    }

    button {
      border: none;
      border-radius: 999px;
      padding: 14px 30px;
      font-size: 15px;
      cursor: pointer;
      background: #fb7185;
      color: white;
      box-shadow: 0 10px 25px rgba(251,113,133,0.4);
      transition: transform 0.2s ease;
    }

    button:hover {
      transform: translateY(-2px);
    }

    .secondary {
      background: none;
      color: #9f1239;
      box-shadow: none;
      margin-top: 15px;
      font-size: 14px;
    }

    .hidden {
      display: none;
    }

    img {
      width: 220px;
      margin-top: 20px;
      border-radius: 20px;
    }
  </style>
</head>

<body>

  <!-- MAIN SCENE -->
  <div class="scene" id="scene">
    <h1>Sofia 💗</h1>
    <p class="text" id="text">
      Est-ce que tu accepterais de sortir avec moi ce vendredi ?
    </p>

    <div class="meter">
      <div class="fill" id="fill"></div>
    </div>

    <p class="meter-text" id="meterText">
      Hésitation détectée 😌
    </p>

    <button id="chooseBtn">Je choisis…</button>
    <button class="secondary" id="noBtn">Hmm… pas sûr 🙈</button>
  </div>

  <!-- SUCCESS SCENE -->
  <div class="scene hidden" id="success">
    <h1>Décision validée ✨</h1>
    <p>Bonne réponse 😏</p>
    <p>À vendredi 💕</p>

    <img src="https://media.giphy.com/media/l0MYC0LajbaPoEADu/giphy.gif">
  </div>

  <script>
    let level = 0;

    const fill = document.getElementById("fill");
    const meterText = document.getElementById("meterText");
    const noBtn = document.getElementById("noBtn");
    const chooseBtn = document.getElementById("chooseBtn");
    const scene = document.getElementById("scene");
    const success = document.getElementById("success");

    const messages = [
      "Hmm… réfléchis encore 😌",
      "Ton sourire dit oui 😏",
      "La barre ne ment jamais 💗",
      "Bon… on sait tous la réponse 😄"
    ];

    noBtn.addEventListener("click", () => {
      level += 25;
      fill.style.width = level + "%";
      meterText.textContent = messages[Math.min(level / 25 - 1, messages.length - 1)];

      if (level >= 100) {
        scene.classList.add("hidden");
        success.classList.remove("hidden");
      }
    });

    chooseBtn.addEventListener("click", () => {
      scene.classList.add("hidden");
      success.classList.remove("hidden");
    });
  </script>

</body>
</html>
