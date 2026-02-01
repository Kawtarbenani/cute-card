# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cute Invitation Card</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Comic Sans MS', 'Chalkboard SE', cursive;
        }
        
        body {
            background: linear-gradient(135deg, #f9c5d1, #c2e9fb);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .card-container {
            max-width: 500px;
            width: 100%;
        }
        
        .card {
            background-color: white;
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            text-align: center;
            position: relative;
            overflow: hidden;
            border: 8px solid #ffccd5;
        }
        
        .card-header {
            margin-bottom: 20px;
        }
        
        h1 {
            color: #ff6699;
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        
        .invite-text {
            font-size: 1.3rem;
            color: #555;
            margin-bottom: 5px;
        }
        
        .highlight {
            background-color: #ffebf3;
            padding: 5px 10px;
            border-radius: 10px;
            color: #ff3366;
            font-weight: bold;
        }
        
        .buttons-container {
            margin: 30px 0;
            position: relative;
            min-height: 150px;
        }
        
        button {
            border: none;
            border-radius: 50px;
            padding: 15px 40px;
            font-size: 1.4rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        #oui-btn {
            background-color: #4cd964;
            color: white;
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 2;
        }
        
        #oui-btn:hover {
            background-color: #3bc853;
            transform: translateX(-50%) scale(1.05);
        }
        
        #non-btn {
            background-color: #ff3b30;
            color: white;
            position: absolute;
            top: 80px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 3;
        }
        
        #non-btn:hover {
            background-color: #ff2317;
        }
        
        .message-container {
            margin: 20px 0;
            min-height: 80px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        #message {
            font-size: 1.5rem;
            color: #ff3366;
            font-weight: bold;
            padding: 10px 20px;
            border-radius: 10px;
            background-color: #fff0f5;
            display: none;
        }
        
        .celebration {
            display: none;
            margin-top: 20px;
        }
        
        .celebration img {
            width: 100%;
            max-width: 300px;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .celebration-text {
            font-size: 2rem;
            color: #ff3366;
            margin-top: 15px;
            animation: pulse 1s infinite;
        }
        
        .counter {
            font-size: 1.1rem;
            color: #777;
            margin-top: 10px;
        }
        
        .heart {
            color: #ff3366;
            animation: heartbeat 1.2s infinite;
            display: inline-block;
        }
        
        .footer {
            margin-top: 20px;
            color: #888;
            font-size: 0.9rem;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.1); }
            10% { transform: scale(1); }
            15% { transform: scale(1.1); }
            20% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        @keyframes celebrate {
            0% { transform: translateY(0px); }
            25% { transform: translateY(-10px); }
            50% { transform: translateY(0px); }
            75% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        @media (max-width: 600px) {
            .card {
                padding: 20px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .invite-text {
                font-size: 1.1rem;
            }
            
            button {
                padding: 12px 30px;
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="card-container">
        <div class="card">
            <div class="card-header">
                <h1><i class="fas fa-heart heart"></i> Une petite question... <i class="fas fa-heart heart"></i></h1>
                <p class="invite-text">Chère <span class="highlight">Sofia</span>,</p>
                <p class="invite-text">Veux-tu aller prendre un verre avec moi</p>
                <p class="invite-text">ce <span class="highlight">vendredi</span> ?</p>
            </div>
            
            <div class="buttons-container">
                <button id="oui-btn">OUI ! <i class="fas fa-check"></i></button>
                <button id="non-btn">Non <i class="fas fa-times"></i></button>
            </div>
            
            <div class="message-container">
                <div id="message"></div>
            </div>
            
            <div class="celebration" id="celebration">
                <img src="https://media.giphy.com/media/26tknCqiJrBQG6DrC/giphy.gif" alt="Celebration GIF">
                <div class="celebration-text">Super ! À vendredi ! <i class="fas fa-glass-cheers"></i></div>
            </div>
            
            <div class="counter">
                Tentatives de cliquer sur "Non": <span id="counter">0</span>
            </div>
            
            <div class="footer">
                <p>Cette carte a été créée spécialement pour toi <i class="fas fa-heart heart" style="color: #ff3366;"></i></p>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const ouiBtn = document.getElementById('oui-btn');
            const nonBtn = document.getElementById('non-btn');
            const message = document.getElementById('message');
            const celebration = document.getElementById('celebration');
            const counter = document.getElementById('counter');
            
            let clickCount = 0;
            const messages = [
                "Tu es sûre ?",
                "Réfléchis bien !",
                "Je pense que tu devrais reconsiderer...",
                "Essaie encore !",
                "Oh non, tu m'as presque eu !",
                "Presque ! Mais pas tout à fait...",
                "Tu y es presque !",
                "Un dernier essai ?"
            ];
            
            // Function to move the "Non" button to a random position
            function moveNonButton() {
                const container = document.querySelector('.buttons-container');
                const containerRect = container.getBoundingClientRect();
                const buttonRect = nonBtn.getBoundingClientRect();
                
                // Calculate max positions to keep button within container
                const maxX = containerRect.width - buttonRect.width - 20;
                const maxY = containerRect.height - buttonRect.height - 20;
                
                // Generate random positions
                const randomX = Math.max(10, Math.floor(Math.random() * maxX));
                const randomY = Math.max(10, Math.floor(Math.random() * maxY));
                
                // Apply new position
                nonBtn.style.left = `${randomX}px`;
                nonBtn.style.top = `${randomY}px`;
                nonBtn.style.transform = 'none';
                
                // Update click counter
                clickCount++;
                counter.textContent = clickCount;
                
                // Show a funny message
                if (clickCount <= messages.length) {
                    message.textContent = messages[clickCount - 1];
                    message.style.display = 'block';
                }
                
                // Make button smaller each time it's clicked
                const currentWidth = nonBtn.offsetWidth;
                const currentHeight = nonBtn.offsetHeight;
                const newWidth = Math.max(70, currentWidth - 10);
                const newHeight = Math.max(30, currentHeight - 5);
                
                nonBtn.style.width = `${newWidth}px`;
                nonBtn.style.height = `${newHeight}px`;
                
                // Change button color as it gets smaller
                const redValue = Math.min(255, 255 - clickCount * 10);
                const greenBlueValue = Math.max(0, 48 - clickCount * 5);
                nonBtn.style.backgroundColor = `rgb(${redValue}, ${greenBlueValue}, ${greenBlueValue})`;
                
                // If button is very small, change its text
                if (clickCount >= 5) {
                    nonBtn.innerHTML = "Non <i class='fas fa-running'></i>";
                }
                
                // If button is tiny, make it almost invisible
                if (clickCount >= 8) {
                    nonBtn.style.opacity = "0.3";
                }
                
                // After 10 clicks, disable the non button and force yes
                if (clickCount >= 10) {
                    nonBtn.style.display = 'none';
                    message.textContent = "Tu n'as plus le choix maintenant !";
                    message.style.display = 'block';
                }
            }
            
            // Function to handle "Oui" button click
            function handleOuiClick() {
                // Hide buttons and message
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Show celebration
                celebration.style.display = 'block';
                
                // Add celebration animation
                celebration.style.animation = "celebrate 1s ease 3";
            }
            
            // Add event listeners
            nonBtn.addEventListener('click', moveNonButton);
            nonBtn.addEventListener('mouseover', function() {
                // Sometimes move the button when hovering too
                if (Math.random() > 0.7 && clickCount < 8) {
                    setTimeout(moveNonButton, 200);
                }
            });
            
            ouiBtn.addEventListener('click', handleOuiClick);
            
            // Initial setup
            message.textContent = "Fais ton choix !";
            message.style.display = 'block';
        });
    </script>
</body>
</html>
