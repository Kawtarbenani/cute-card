# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>✨ A Special Invitation ✨</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #ffd6e7 0%, #c1f0ff 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            padding: 20px;
        }
        
        .floating-hearts {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        
        .heart {
            position: absolute;
            color: #ff6b9d;
            font-size: 24px;
            animation: float 8s linear infinite;
            opacity: 0.7;
        }
        
        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.7;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        .card-container {
            position: relative;
            z-index: 2;
            max-width: 600px;
            width: 100%;
            perspective: 1000px;
        }
        
        .card {
            background: white;
            border-radius: 30px;
            padding: 40px;
            box-shadow: 
                0 20px 60px rgba(255, 107, 157, 0.3),
                0 0 0 15px #fff0f6,
                0 0 0 30px rgba(255, 240, 246, 0.5);
            text-align: center;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            animation: cardAppear 1s ease-out;
        }
        
        @keyframes cardAppear {
            0% {
                transform: translateY(50px) rotateX(-10deg);
                opacity: 0;
            }
            100% {
                transform: translateY(0) rotateX(0);
                opacity: 1;
            }
        }
        
        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 107, 157, 0.1), transparent);
            transform: rotate(45deg);
            animation: sparkle 4s linear infinite;
        }
        
        @keyframes sparkle {
            0% { transform: rotate(45deg) translateX(-100%); }
            100% { transform: rotate(45deg) translateX(100%); }
        }
        
        .card-header {
            margin-bottom: 30px;
            position: relative;
            z-index: 2;
        }
        
        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3.5rem;
            color: #ff6b9d;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { text-shadow: 0 0 10px #ff6b9d, 0 0 20px #ff6b9d; }
            to { text-shadow: 0 0 15px #ff9ec0, 0 0 25px #ff9ec0; }
        }
        
        .invite-text {
            font-size: 1.4rem;
            color: #555;
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        .highlight {
            background: linear-gradient(120deg, #ff9ec0 0%, #ff6b9d 100%);
            padding: 8px 20px;
            border-radius: 50px;
            color: white;
            font-weight: 600;
            display: inline-block;
            margin: 0 5px;
            box-shadow: 0 4px 15px rgba(255, 107, 157, 0.3);
        }
        
        .invitation-box {
            background: linear-gradient(135deg, #fff9fb 0%, #fff0f6 100%);
            border-radius: 20px;
            padding: 25px;
            margin: 30px 0;
            border: 3px dashed #ff9ec0;
            position: relative;
        }
        
        .invitation-box::before {
            content: '💌';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 2rem;
            background: white;
            padding: 0 15px;
        }
        
        .buttons-container {
            margin: 40px 0;
            position: relative;
            min-height: 200px;
        }
        
        button {
            border: none;
            border-radius: 50px;
            padding: 20px 50px;
            font-size: 1.5rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            position: absolute;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            z-index: 3;
        }
        
        #oui-btn {
            background: linear-gradient(135deg, #4cd964 0%, #2ecc71 100%);
            color: white;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(-10px); }
        }
        
        #oui-btn:hover {
            transform: translateX(-50%) scale(1.1);
            box-shadow: 0 12px 30px rgba(46, 204, 113, 0.4);
        }
        
        #non-btn {
            background: linear-gradient(135deg, #ff9a9e 0%, #ff6b9d 100%);
            color: white;
            top: 100px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 4;
        }
        
        #non-btn:hover {
            transform: translateX(-50%) scale(1.05);
            box-shadow: 0 12px 30px rgba(255, 107, 157, 0.4);
        }
        
        .message-container {
            margin: 30px 0;
            min-height: 80px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        #message {
            font-size: 1.5rem;
            color: #ff6b9d;
            font-weight: 600;
            padding: 15px 30px;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            display: none;
            border: 2px solid #ff9ec0;
            animation: pulseMessage 2s infinite;
        }
        
        @keyframes pulseMessage {
            0% { box-shadow: 0 0 0 0 rgba(255, 107, 157, 0.4); }
            70% { box-shadow: 0 0 0 15px rgba(255, 107, 157, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 107, 157, 0); }
        }
        
        .celebration {
            display: none;
            margin-top: 30px;
            animation: celebrate 1s ease;
        }
        
        @keyframes celebrate {
            0% { transform: scale(0); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        .celebration-gif {
            width: 100%;
            max-width: 400px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            margin: 0 auto;
            display: block;
        }
        
        .celebration-text {
            font-family: 'Dancing Script', cursive;
            font-size: 3rem;
            color: #ff6b9d;
            margin-top: 20px;
            animation: rainbow 3s infinite alternate;
        }
        
        @keyframes rainbow {
            0% { color: #ff6b9d; }
            25% { color: #ff9a9e; }
            50% { color: #a29bfe; }
            75% { color: #74b9ff; }
            100% { color: #00cec9; }
        }
        
        .counter {
            font-size: 1.2rem;
            color: #888;
            margin-top: 20px;
            padding: 10px 20px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 20px;
            display: inline-block;
        }
        
        .flowers {
            position: absolute;
            font-size: 2rem;
            z-index: 1;
        }
        
        .flower-1 { top: 20px; left: 20px; animation: sway 5s infinite ease-in-out; color: #ff9ec0; }
        .flower-2 { top: 20px; right: 20px; animation: sway 5s infinite ease-in-out reverse; color: #ffd166; }
        .flower-3 { bottom: 20px; left: 20px; animation: sway 5s infinite ease-in-out; color: #06d6a0; }
        .flower-4 { bottom: 20px; right: 20px; animation: sway 5s infinite ease-in-out reverse; color: #118ab2; }
        
        @keyframes sway {
            0%, 100% { transform: rotate(-5deg); }
            50% { transform: rotate(5deg); }
        }
        
        .footer {
            margin-top: 30px;
            color: #aaa;
            font-size: 0.9rem;
        }
        
        .secret-note {
            font-size: 0.8rem;
            color: #ccc;
            margin-top: 10px;
        }
        
        /* Mobile responsive */
        @media (max-width: 768px) {
            .card {
                padding: 25px;
            }
            
            h1 {
                font-size: 2.5rem;
            }
            
            .invite-text {
                font-size: 1.2rem;
            }
            
            button {
                padding: 15px 30px;
                font-size: 1.3rem;
            }
            
            .celebration-text {
                font-size: 2.2rem;
            }
        }
        
        /* Secret agent mode - hide all identifying info */
        .secret-agent {
            display: none;
        }
    </style>
</head>
<body>
    <!-- Floating hearts background -->
    <div class="floating-hearts" id="hearts-container"></div>
    
    <!-- Decorative flowers -->
    <div class="flowers flower-1">🌸</div>
    <div class="flowers flower-2">🌺</div>
    <div class="flowers flower-3">🌼</div>
    <div class="flowers flower-4">💮</div>
    
    <div class="card-container">
        <div class="card">
            <div class="card-header">
                <h1><i class="fas fa-heart"></i> Mon Trésor <i class="fas fa-heart"></i></h1>
                <p class="invite-text">Ma chérie, j'ai une petite question pour toi...</p>
            </div>
            
            <div class="invitation-box">
                <p class="invite-text">Veux-tu passer une soirée magique avec moi</p>
                <p class="invite-text">ce <span class="highlight">vendredi</span> ?</p>
                <p class="invite-text">Juste toi, moi, et les étoiles ✨</p>
            </div>
            
            <div class="buttons-container">
                <button id="oui-btn">
                    <i class="fas fa-heart"></i> OUI ! <i class="fas fa-heart"></i>
                </button>
                <button id="non-btn">
                    <i class="fas fa-times"></i> Peut-être... <i class="fas fa-running"></i>
                </button>
            </div>
            
            <div class="message-container">
                <div id="message">Fais ton choix, ma belle! 💖</div>
            </div>
            
            <div class="celebration" id="celebration">
                <img class="celebration-gif" src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif" alt="Celebration">
                <div class="celebration-text">Hourra! À vendredi, mon amour! 🥂✨</div>
            </div>
            
            <div class="counter">
                <i class="fas fa-redo"></i> Tentatives d'échapper: <span id="counter">0</span>
            </div>
            
            <div class="footer">
                <p>Avec tout mon amour ❤️</p>
                <p class="secret-note">P.S. Essaie de cliquer sur "Peut-être"... 😉</p>
            </div>
            
            <!-- Secret info - hidden from user -->
            <div class="secret-agent">
                <p>Created for cousin's girlfriend</p>
                <p>No names in URL</p>
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
            const heartsContainer = document.getElementById('hearts-container');
            
            let clickCount = 0;
            const messages = [
                "Tu es sûre, ma belle? 🥺",
                "Mais pense aux moments magiques! ✨",
                "Je t'offrirai des fleurs! 🌸",
                "Et du chocolat! 🍫",
                "On regardera les étoiles! 🌟",
                "S'il te plaît? 🙏",
                "Je ferai n'importe quoi! 🤲",
                "Dernière chance de dire oui! 😘"
            ];
            
            // Create floating hearts
            function createHearts() {
                for (let i = 0; i < 20; i++) {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.innerHTML = '❤️';
                    heart.style.left = Math.random() * 100 + 'vw';
                    heart.style.animationDelay = Math.random() * 8 + 's';
                    heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
                    heart.style.color = ['#ff6b9d', '#ff9ec0', '#ffd166', '#a29bfe'][Math.floor(Math.random() * 4)];
                    heartsContainer.appendChild(heart);
                }
            }
            
            // Function to move the "Non" button in a fun way
            function moveNonButton() {
                const container = document.querySelector('.buttons-container');
                const containerRect = container.getBoundingClientRect();
                const buttonRect = nonBtn.getBoundingClientRect();
                
                // Different escape patterns
                const patterns = [
                    { x: Math.random() * (containerRect.width - buttonRect.width), y: 10 },
                    { x: 10, y: Math.random() * (containerRect.height - buttonRect.height) },
                    { x: containerRect.width - buttonRect.width - 10, y: Math.random() * (containerRect.height - buttonRect.height) },
                    { x: Math.random() * (containerRect.width - buttonRect.width), y: containerRect.height - buttonRect.height - 10 },
                    { x: Math.random() * (containerRect.width - buttonRect.width), y: Math.random() * (containerRect.height - buttonRect.height) }
                ];
                
                const pattern = patterns[Math.floor(Math.random() * patterns.length)];
                
                // Animate the movement
                nonBtn.style.transition = 'all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55)';
                nonBtn.style.left = `${pattern.x}px`;
                nonBtn.style.top = `${pattern.y}px`;
                nonBtn.style.transform = 'none';
                
                // Update click counter
                clickCount++;
                counter.textContent = clickCount;
                
                // Change button text and appearance
                const buttonTexts = [
                    "Non merci 😅",
                    "Pas cette fois 🏃‍♂️",
                    "Je réfléchis 💭",
                    "Escape! 🚀",
                    "Trop rapide! ⚡",
                    "Presque! 😆",
                    "Encore! 🎯",
                    "Dernier essai! 🏁"
                ];
                
                if (clickCount <= buttonTexts.length) {
                    nonBtn.innerHTML = `<i class="fas fa-running"></i> ${buttonTexts[clickCount-1]} <i class="fas fa-running"></i>`;
                }
                
                // Show message
                if (clickCount <= messages.length) {
                    message.textContent = messages[clickCount - 1];
                    message.style.display = 'block';
                }
                
                // Make button smaller and change color
                const scale = Math.max(0.5, 1 - clickCount * 0.05);
                nonBtn.style.transform = `scale(${scale})`;
                
                // Change button gradient as it gets smaller
                const red1 = Math.max(150, 255 - clickCount * 15);
                const green1 = Math.max(100, 154 - clickCount * 10);
                const red2 = Math.max(100, 107 - clickCount * 10);
                const green2 = Math.max(50, 157 - clickCount * 15);
                nonBtn.style.background = `linear-gradient(135deg, rgb(${red1}, ${green1}, 158) 0%, rgb(${red2}, ${green2}, 157) 100%)`;
                
                // Add floating hearts when button moves
                for (let i = 0; i < 5; i++) {
                    setTimeout(() => createSingleHeart(nonBtn), i * 100);
                }
                
                // After 8 clicks, make the button very small and hard to click
                if (clickCount >= 8) {
                    nonBtn.style.opacity = "0.5";
                    nonBtn.style.pointerEvents = "none";
                    nonBtn.style.cursor = "not-allowed";
                    message.textContent = "Tu n'as plus le choix, ma belle! 😉 Clique sur OUI!";
                    message.style.display = 'block';
                }
            }
            
            // Create single heart at button position
            function createSingleHeart(button) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.innerHTML = '💖';
                heart.style.position = 'absolute';
                heart.style.left = button.getBoundingClientRect().left + 'px';
                heart.style.top = button.getBoundingClientRect().top + 'px';
                heart.style.fontSize = '20px';
                heart.style.animation = 'float 3s linear forwards';
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 3000);
            }
            
            // Function to handle "Oui" button click
            function handleOuiClick() {
                // Hide buttons and message
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Create explosion of hearts
                for (let i = 0; i < 50; i++) {
                    setTimeout(() => {
                        const heart = document.createElement('div');
                        heart.className = 'heart';
                        heart.innerHTML = ['❤️', '💖', '💕', '💗', '💓'][Math.floor(Math.random() * 5)];
                        heart.style.left = Math.random() * 100 + 'vw';
                        heart.style.fontSize = (Math.random() * 30 + 20) + 'px';
                        heart.style.color = ['#ff6b9d', '#ff9ec0', '#ffd166', '#a29bfe', '#00cec9'][Math.floor(Math.random() * 5)];
                        heart.style.animation = 'float 4s linear forwards';
                        document.body.appendChild(heart);
                        setTimeout(() => heart.remove(), 4000);
                    }, i * 50);
                }
                
                // Show celebration
                setTimeout(() => {
                    celebration.style.display = 'block';
                }, 500);
                
                // Change background to celebration mode
                document.body.style.background = 'linear-gradient(135deg, #ff9ec0 0%, #a29bfe 50%, #74b9ff 100%)';
                document.body.style.animation = 'rainbowBackground 10s infinite alternate';
            }
            
            // Add event listeners
            nonBtn.addEventListener('click', moveNonButton);
            nonBtn.addEventListener('mouseover', function() {
                // Sometimes move when hovering (but less often)
                if (Math.random() > 0.8 && clickCount < 6) {
                    setTimeout(() => {
                        nonBtn.style.transform = 'translateX(20px)';
                        setTimeout(() => {
                            nonBtn.style.transform = 'translateX(-20px)';
                            setTimeout(() => {
                                nonBtn.style.transform = 'translateX(0)';
                            }, 100);
                        }, 100);
                    }, 100);
                }
            });
            
            ouiBtn.addEventListener('click', handleOuiClick);
            
            // Initial setup
            message.textContent = "Fais ton choix, ma belle! 💖";
            message.style.display = 'block';
            createHearts();
            
            // Add CSS for rainbow background animation
            const style = document.createElement('style');
            style.textContent = `
                @keyframes rainbowBackground {
                    0% { filter: hue-rotate(0deg); }
                    100% { filter: hue-rotate(360deg); }
                }
            `;
            document.head.appendChild(style);
        });
    </script>
</body>
</html>
