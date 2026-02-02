# cute-card
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <title>Just a tiny question 💌</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #fce7f3, #e0f2fe);
      font-family: "Poppins", system-ui, sans-serif;
      overflow: hidden;
    }

    .card {
      background: rgba(255, 255, 255, 0.9);
      backdrop-filter: blur(10px);
      padding: 40px;
      border-radius: 28px;
      width: 360px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
      position: relative;
    }

    h1 {
      font-size: 22px;
      margin-bottom: 8px;
    }

    .question {
      font-size: 17px;
      margin-bottom: 6px;
    }

    .tease {
      font-size: 14px;
      color: #ec4899;
      margin-bottom: 25px;
    }

    .buttons {
      position: relative;
      height: 80px;
    }

    button {
      border: none;
      padding: 12px 26px;
      font-size: 15px;
      border-radius: 999px;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.15);
    }

    #yes {
      background: #fb7185;
      color: white;
      margin-right: 10px;
    }

    #no {
      background: #fce7f3;
      color: #be185d;
      position: absolute;
      left: 180px;
      top: 0;
      transition: left 0.3s ease, top 0.3s ease;
    }

    .hidden {
      display: none;
    }

    .success h1 {
      font-size: 24px;
    }

    .success p {
      font-size: 16px;
      margin: 10px 0;
    }

    img {
      width: 220px;
      margin-top: 20px;
      border-radius: 18px;
    }
  </style>
</head>

<body>

  <!-- Question card -->
  <div class="card" id="card">
    <h1>Sofia 💕</h1>

    <p class="question">
      Tu serais libre pour sortir avec moi ce vendredi ?
    </p>

    <p class="tease">
      (Vas-y… essaye « Non » 😌)
    </p>

    <div class="buttons">
      <button id="yes">Oui 💖</button>
      <button id="no">Non 👀</button>
    </div>
  </div>

  <!-- Success card -->
  <div class="card success hidden" id="success">
    <h1>YAY ✨💃</h1>
    <p>Bon choix 😏</p>
    <p>À vendredi alors 💗</p>

    <img
      src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM3o1bXBmdDdkMnU1bTNpaHJkZTRsNnM4OWRwbmVjbTR4bWJ6ZmM3eiZlcD12MV9naWZzX3NlYXJjaCZjdD1n/3oriO0OEd9QIDdllqo/giphy.gif"
      alt="celebration"
    />
  </div>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const card = document.getElementById("card");
    const success = document.getElementById("success");

    noBtn.addEventListener("mouseenter", () => {
      const maxX = card.clientWidth - noBtn.offsetWidth;
      const maxY = 50;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    });

    yesBtn.addEventListener("click", () => {
      card.classList.add("hidden");
      success.classList.remove("hidden");
    });
  </script>

</body>
</html>

