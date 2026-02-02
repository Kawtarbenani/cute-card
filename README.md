<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour Sofia</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Comic+Neue:wght@700&family=Nunito:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Nunito', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #ffafcc 0%, #a2d2ff 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
            position: relative;
            cursor: default;
            overflow-x: hidden;
            overflow-y: auto;
        }
        
        .container {
            max-width: 500px;
            width: 100%;
            z-index: 10;
            position: relative;
            margin: 20px 0;
        }
        
        .card {
            background: white;
            border-radius: 25px;
            padding: 40px 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
            text-align: center;
            border: 8px solid #ffafcc;
            position: relative;
            overflow: visible;
        }
        
        .card::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: linear-gradient(45deg, #ffafcc, #a2d2ff, #cdb4db);
            z-index: -1;
            border-radius: 30px;
            animation: rotate 4s linear infinite;
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .title {
            font-family: 'Comic Neue', cursive;
            font-size: 2rem;
            color: #ff006e;
            margin-bottom: 25px;
            text-shadow: 2px 2px 0 #ffafcc;
            transition: all 0.5s ease;
        }
        
        .question-box {
            background: linear-gradient(135deg, #fff5f9 0%, #f0f8ff 100%);
            border-radius: 18px;
            padding: 25px;
            margin: 25px 0 30px 0;
            border: 3px dashed #ffafcc;
            position: relative;
            z-index: 5;
            transition: all 0.5s ease;
        }
        
        .question {
            font-size: 1.7rem;
            color: #444;
            line-height: 1.4;
            padding: 10px 0;
            transition: all 0.5s ease;
        }
        
        .sofia-name {
            color: #ff006e;
            font-weight: 800;
            background: #ffe5ec;
            padding: 8px 20px;
            border-radius: 50px;
            display: inline-block;
            margin: 0 8px 15px 8px;
            border: 3px solid #ffafcc;
        }
        
        .buttons-wrapper {
            position: relative;
            margin: 20px 0 40px 0;
            min-height: 200px;
            z-index: 10;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 30px;
        }
        
        .oui-btn {
            background: linear-gradient(135deg, #4cd964 0%, #2ecc71 100%);
            color: white;
            border: none;
            padding: 20px 50px;
            font-size: 1.8rem;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(76, 217, 100, 0.4);
            position: relative;
            z-index: 15;
            transition: all 0.3s;
            font-weight: 800;
            display: inline-flex;
            align-items: center;
            gap: 15px;
            order: 1;
        }
        
        .oui-btn:hover {
            transform: scale(1.08);
            box-shadow: 0 15px 30px rgba(76, 217, 100, 0.6);
        }
        
        .non-btn {
            background: linear-gradient(135deg, #ff8fab 0%, #ff5c8d 100%);
            color: white;
            border: none;
            padding: 18px 45px;
            font-size: 1.6rem;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(255, 92, 141, 0.4);
            position: relative;
            z-index: 20;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 10px;
            order: 2;
            margin-top: 10px;
            transition: none !important; /* NO TRANSITION FOR INSTANT MOVEMENT */
        }
        
        .non-btn .shy-text {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-left: 8px;
            font-weight: 600;
            font-style: italic;
        }
        
        .message {
            font-size: 1.4rem;
            color: #ff6b9d;
            margin: 30px 0 20px 0;
            min-height: 50px;
            font-weight: 700;
            padding: 15px 25px;
            background: #fff5f9;
            border-radius: 15px;
            border: 3px solid #ffafcc;
            display: none;
            animation: messagePop 0.3s ease;
            position: relative;
            z-index: 5;
        }
        
        @keyframes messagePop {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .celebration-container {
            display: none;
            margin-top: 30px;
            animation: celebrateIn 0.8s ease;
            position: relative;
            z-index: 5;
            text-align: center;
        }
        
        @keyframes celebrateIn {
            0% { transform: scale(0); opacity: 0; }
            60% { transform: scale(1.1); }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .yay-text {
            font-family: 'Comic Neue', cursive;
            font-size: 2.8rem;
            color: #ff006e;
            font-weight: 900;
            margin: 10px 0 20px 0;
            animation: bounce 0.6s infinite alternate;
            text-shadow: 3px 3px 0 #ffafcc;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-15px); }
        }
        
        .celebration-gif-container {
            position: relative;
            width: 100%;
            max-width: 320px;
            margin: 10px auto;
        }
        
        .celebration-gif {
            width: 100%;
            border-radius: 20px;
            border: 6px solid #ffafcc;
            box-shadow: 0 15px 30px rgba(255, 107, 157, 0.3);
        }
        
        .final-message {
            font-family: 'Comic Neue', cursive;
            font-size: 2rem;
            color: #ff006e;
            font-weight: 900;
            margin: 20px 0;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }
        
        .footer {
            margin-top: 30px;
            color: #888;
            font-size: 1rem;
            font-style: italic;
            position: relative;
            z-index: 5;
        }
        
        .cute-emoji {
            position: absolute;
            font-size: 2rem;
            z-index: 1;
            animation: float 3s ease-in-out infinite;
        }
        
        .emoji-1 { top: 20px; left: 20px; }
        .emoji-2 { top: 20px; right: 20px; animation-delay: 0.5s; }
        .emoji-3 { bottom: 20px; left: 20px; animation-delay: 1s; }
        .emoji-4 { bottom: 20px; right: 20px; animation-delay: 1.5s; }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(5deg); }
        }
        
        /* Mobile responsive */
        @media (max-width: 500px) {
            .container {
                max-width: 95%;
            }
            
            .card {
                padding: 30px 20px;
            }
            
            .title {
                font-size: 1.8rem;
            }
            
            .question {
                font-size: 1.5rem;
            }
            
            .oui-btn {
                padding: 18px 40px;
                font-size: 1.6rem;
            }
            
            .non-btn {
                padding: 16px 35px;
                font-size: 1.4rem;
            }
            
            .yay-text {
                font-size: 2.2rem;
            }
            
            .celebration-gif-container {
                max-width: 280px;
            }
            
            .final-message {
                font-size: 1.8rem;
            }
            
            .cute-emoji {
                font-size: 1.6rem;
            }
        }
        
        /* Make sure page is scrollable but not horizontally */
        html {
            overflow-y: scroll;
            overflow-x: hidden;
            width: 100%;
        }
        
        body {
            min-height: 120vh;
            width: 100%;
            overflow-x: hidden;
        }
    </style>
</head>
<body>
    <div class="cute-emoji emoji-1">🌸</div>
    <div class="cute-emoji emoji-2">✨</div>
    <div class="cute-emoji emoji-3">💖</div>
    <div class="cute-emoji emoji-4">🎀</div>
    
    <div class="container">
        <div class="card">
            <h1 class="title" id="mainTitle">Question pour toi ✨</h1>
            
            <div class="question-box" id="questionBox">
                <p class="question" id="questionText">
                    <span class="sofia-name">Sofia</span><br>
                    veux-tu sortir vendredi ? 
                    <span style="font-size: 2rem; display: block; margin-top: 15px;">😊</span>
                </p>
            </div>
            
            <div class="celebration-container" id="celebrationContainer">
                <div class="yay-text">🎉 YAY! À vendredi! 🎉</div>
                
                <div class="celebration-gif-container">
                    <img class="celebration-gif" id="celebrationGif" src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif" alt="Man Celebrating">
                </div>
                
                <div class="final-message" id="finalMessage">✨ On se voit vendredi! ✨</div>
            </div>
            
            <div class="buttons-wrapper">
                <button class="oui-btn" id="ouiBtn">
                    <i class="fas fa-heart"></i> OUI !
                </button>
                
                <button class="non-btn" id="nonBtn">
                    <i class="fas fa-grin-tongue-squint"></i> Non 
                    <span class="shy-text">(shy 😈)</span>
                </button>
            </div>
            
            <div class="message" id="message"></div>
            
            <div class="footer">
                <p>Le bouton "Non" fuit partout sur la page! 😉</p>
            </div>
        </div>
    </div>

    <div style="height: 200px; width: 100%;"></div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const ouiBtn = document.getElementById('ouiBtn');
            const nonBtn = document.getElementById('nonBtn');
            const message = document.getElementById('message');
            const questionBox = document.getElementById('questionBox');
            const celebrationContainer = document.getElementById('celebrationContainer');
            const mainTitle = document.getElementById('mainTitle');
            const finalMessage = document.getElementById('finalMessage');
            const celebrationGif = document.getElementById('celebrationGif');
            
            let isCelebrating = false;
            let isNonFixed = false;
            let gifRestartInterval = null;
            let lastPosition = { x: 0, y: 0 };
            
            // Restart GIF function
            function restartGif() {
                const gifSrc = celebrationGif.src;
                celebrationGif.src = "";
                celebrationGif.src = gifSrc;
            }
            
            // Function to move button to random position
            function moveButtonRandomly() {
                if (isCelebrating) return;
                
                // ALWAYS move to fixed position
                if (!isNonFixed) {
                    nonBtn.style.position = 'fixed';
                    nonBtn.style.zIndex = '100';
                    isNonFixed = true;
                }
                
                // Random position
                const randomX = Math.random() * (window.innerWidth - nonBtn.offsetWidth - 80) + 40;
                const randomY = Math.random() * (window.innerHeight - nonBtn.offsetHeight - 80) + 40;
                
                // INSTANT movement
                nonBtn.style.transition = 'none';
                nonBtn.style.left = `${randomX}px`;
                nonBtn.style.top = `${randomY}px`;
                lastPosition = { x: randomX, y: randomY };
                
                // Show message 30% of the time
                if (Math.random() > 0.7) {
                    const messages = [
                        "Trop rapide! ⚡",
                        "Raté! 😆",
                        "Pas si vite! 🏃‍♂️",
                        "Haha! 😈",
                        "Essaie encore! 💨",
                        "Presque! 🙈",
                        "Impossible! 🚀",
                        "Il fuit! 🌪️",
                        "Tu m'as presque eu! 😅",
                        "Trop lent! 🐢"
                    ];
                    message.textContent = messages[Math.floor(Math.random() * messages.length)];
                    message.style.display = 'block';
                    
                    setTimeout(() => {
                        if (!isCelebrating) {
                            message.style.display = 'none';
                        }
                    }, 600);
                }
                
                // Visual effect
                nonBtn.style.boxShadow = '0 0 0 8px rgba(255, 255, 255, 0.9), 0 20px 40px rgba(255, 92, 141, 0.8)';
                setTimeout(() => {
                    nonBtn.style.boxShadow = '0 8px 20px rgba(255, 92, 141, 0.4)';
                }, 50);
                
                // Scale effect
                const scale = 0.5 + Math.random() * 0.6;
                nonBtn.style.transform = `scale(${scale})`;
            }
            
            // Make Non button move INSTANTLY when mouse approaches
            document.addEventListener('mousemove', function(event) {
                if (isCelebrating) return;
                
                const btnRect = nonBtn.getBoundingClientRect();
                const btnCenterX = btnRect.left + btnRect.width / 2;
                const btnCenterY = btnRect.top + btnRect.height / 2;
                
                const distance = Math.sqrt(
                    Math.pow(event.clientX - btnCenterX, 2) + 
                    Math.pow(event.clientY - btnCenterY, 2)
                );
                
                // EXTREME sensitivity - moves from FAR away
                if (distance < 200) { // Reacts from 200px away
                    moveButtonRandomly();
                }
            });
            
            // Escape also when mouse enters button
            nonBtn.addEventListener('mouseenter', function(event) {
                if (!isCelebrating) {
                    // Move button to opposite side of mouse
                    const newX = event.clientX > window.innerWidth/2 ? 
                        Math.random() * (window.innerWidth/3) : 
                        window.innerWidth - nonBtn.offsetWidth - Math.random() * 100;
                    
                    const newY = event.clientY > window.innerHeight/2 ? 
                        Math.random() * (window.innerHeight/3) : 
                        window.innerHeight - nonBtn.offsetHeight - Math.random() * 100;
                    
                    if (!isNonFixed) {
                        nonBtn.style.position = 'fixed';
                        nonBtn.style.zIndex = '100';
                        isNonFixed = true;
                    }
                    
                    nonBtn.style.transition = 'none';
                    nonBtn.style.left = `${newX}px`;
                    nonBtn.style.top = `${newY}px`;
                }
            });
            
            // Try to click the button - makes it JUMP
            nonBtn.addEventListener('mousedown', function(event) {
                event.preventDefault();
                event.stopPropagation();
                
                // Jump FAR to opposite corner
                const jumpX = Math.random() > 0.5 ? 
                    Math.random() * 100 + 20 : 
                    window.innerWidth - nonBtn.offsetWidth - Math.random() * 100 - 20;
                
                const jumpY = Math.random() > 0.5 ? 
                    Math.random() * 100 + 20 : 
                    window.innerHeight - nonBtn.offsetHeight - Math.random() * 100 - 20;
                
                if (!isNonFixed) {
                    nonBtn.style.position = 'fixed';
                    nonBtn.style.zIndex = '100';
                    isNonFixed = true;
                }
                
                nonBtn.style.transition = 'none';
                nonBtn.style.left = `${jumpX}px`;
                nonBtn.style.top = `${jumpY}px`;
                nonBtn.style.transform = 'scale(0.7)';
                
                message.textContent = "Haha! Presque réussi! Mais NON! 😅";
                message.style.display = 'block';
                
                // Jump animation
                nonBtn.style.transform += ' translateY(-50px)';
                setTimeout(() => {
                    nonBtn.style.transform = nonBtn.style.transform.replace('translateY(-50px)', '');
                }, 100);
            });
            
            // Auto-move button every 1.5 seconds to keep it active
            setInterval(() => {
                if (!isCelebrating && Math.random() > 0.3) {
                    moveButtonRandomly();
                }
            }, 1500);
            
            // When OUI is clicked
            ouiBtn.addEventListener('click', function() {
                isCelebrating = true;
                
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                mainTitle.style.opacity = '0';
                mainTitle.style.transform = 'translateY(-20px)';
                
                setTimeout(() => {
                    mainTitle.textContent = 'YAY! ✨';
                    mainTitle.style.opacity = '1';
                    mainTitle.style.transform = 'translateY(0)';
                    
                    questionBox.style.opacity = '0';
                    questionBox.style.transform = 'translateY(-20px)';
                    
                    setTimeout(() => {
                        questionBox.style.display = 'none';
                        celebrationContainer.style.display = 'block';
                        
                        gifRestartInterval = setInterval(restartGif, 2800);
                        setTimeout(() => restartGif(), 100);
                        
                        setTimeout(() => {
                            finalMessage.style.opacity = '1';
                            finalMessage.style.transform = 'translateY(0)';
                        }, 1000);
                        
                        // Create confetti
                        for (let i = 0; i < 200; i++) {
                            setTimeout(() => {
                                createConfetti();
                            }, i * 3);
                        }
                        
                        document.body.style.background = 'linear-gradient(135deg, #ff9ec0 0%, #a29bfe 33%, #74b9ff 66%, #ffd166 100%)';
                        document.body.style.animation = 'rainbowBG 10s infinite linear';
                        
                        const style = document.createElement('style');
                        style.textContent = `
                            @keyframes rainbowBG {
                                0% { filter: hue-rotate(0deg); }
                                100% { filter: hue-rotate(360deg); }
                            }
                        `;
                        document.head.appendChild(style);
                    }, 500);
                }, 500);
            });
            
            // Create confetti
            function createConfetti() {
                const confetti = document.createElement('div');
                const emojis = ['🎉', '✨', '🎊', '🥳', '💖', '🌟', '😊', '💕'];
                confetti.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
                confetti.style.position = 'fixed';
                confetti.style.fontSize = (Math.random() * 30 + 15) + 'px';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-50px';
                confetti.style.zIndex = '1000';
                confetti.style.opacity = '0.9';
                
                document.body.appendChild(confetti);
                
                const duration = Math.random() * 1000 + 400;
                const endX = (Math.random() * 300 - 150) + 'px';
                
                confetti.animate([
                    { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                    { transform: `translateY(${window.innerHeight + 100}px) translateX(${endX}) rotate(${Math.random() * 720}deg)`, opacity: 0 }
                ], {
                    duration: duration,
                    easing: 'cubic-bezier(0.215, 0.61, 0.355, 1)'
                });
                
                setTimeout(() => confetti.remove(), duration);
            }
            
            // Initial message
            message.textContent = "Essaie de cliquer sur 'Non'... si tu peux! 😈";
            message.style.display = 'block';
            
            // Initial random move after 1 second
            setTimeout(() => {
                if (!isCelebrating) {
                    moveButtonRandomly();
                }
            }, 1000);
        });
    </script>
</body>
</html>
