# cute-card
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Une petite question 💕</title>

  <style>
    body {
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: "Comic Sans MS", "Segoe UI", sans-serif;
      background: linear-gradient(135deg, #ffe6f0, #fff7fb);
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 35px;
      border-radius: 25px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.15);
      text-align: center;
      width: 340px;
      position: relative;
    }

    h1 {
      font-size: 24px;
      margin-bottom: 10px;
    }

    p {
      font-size: 16px;
      margin: 8px 0;
    }

    .hint {
      font-size: 14px;
      color: #ff5fa2;
      margin-top: 5px;
    }

    button {
      padding: 12px 25px;
      font-size: 16px;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      margin: 15px 10px;
      transition: transform 0.2s ease;
    }

    button:hover {
      transform: scale(1.05);
    }

    #yes {
      background-color: #ff8acb;
      color: white;
    }

    #no {
      background-color: #ffd1e6;
      color: #b30059;
      position: absolute;
    }

    .hidden {
      display: none;
    }

    img {
      width: 220px;
      margin-top: 20px;
      border-radius: 15px;
    }
  </style>
</head>

<body>

  <!-- First card -->
  <div class="card" id="card">
    <h1>Sofia 💗</h1>

    <p>Est-ce que tu veux sortir avec moi ce vendredi ?</p>

    <p class="hint">(Tu peux essayer de cliquer sur « Non » 😏)</p>

    <button id="yes">Oui 💕</button>
    <button id="no">Non 🙈</button>
  </div>

  <!-- Success card -->
  <div class="card hidden" id="success">
    <h1>YAAAAAY 🎉💖</h1>
    <p>Je savais que tu dirais oui 😌</p>
    <p>À vendredi alors ✨</p>

    <img src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif">
  </div>

  <script>
    const noButton = document.getElementById("no");
    const yesButton = document.getElementById("yes");
    const card = document.getElementById("card");
    const success = document.getElementById("success");

    noButton.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 120);
      const y = Math.random() * (window.innerHeight - 80);
      noButton.style.left = x + "px";
      noButton.style.top = y + "px";
    });

    yesButton.addEventListener("click", () => {
      card.classList.add("hidden");
      success.classList.remove("hidden");
    });
  </script>

</body>
</html>

