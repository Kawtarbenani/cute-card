# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Cute Invitation 💌</title>
  <style>
    body {
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #ffd6e8, #fff);
      overflow: hidden;
    }

    .card {
      text-align: center;
      background: white;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      width: 320px;
    }

    h1 {
      font-size: 22px;
    }

    button {
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      margin: 10px;
    }

    #yes {
      background-color: #4CAF50;
      color: white;
    }

    #no {
      background-color: #f44336;
      color: white;
      position: absolute;
    }

    .hidden {
      display: none;
    }

    img {
      width: 200px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <div class="card" id="card">
    <h1>Sofia 💖</h1>
    <p>Tu veux sortir avec moi ce vendredi ?</p>

    <button id="yes">Oui</button>
    <button id="no">Non</button>
  </div>

  <div class="card hidden" id="success">
    <h1>YAYYYY 🎉💃</h1>
    <p>À vendredi alors 😍</p>
    <img src="https://media.giphy.com/media/26ufdipQqU2lhNA4g/giphy.gif">
  </div>

  <script>
    const noButton = document.getElementById("no");
    const yesButton = document.getElementById("yes");
    const card = document.getElementById("card");
    const success = document.getElementById("success");

    noButton.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 50);
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
