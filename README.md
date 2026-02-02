# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌸 Question pour Sofia 🌸</title>
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
            background: linear-gradient(135deg, #ffcfe0 0%, #b5deff 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .bubbles {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        
        .bubble {
            position: absolute;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            animation: floatUp 15s linear infinite;
        }
        
        @keyframes floatUp {
            0% {
                transform: translateY(100vh) scale(0.5);
                opacity: 0;
            }
            10% {
                opacity: 0.7;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(-100px) scale(1);
                opacity: 0;
            }
        }
        
        .container {
            max-width: 550px;
            width: 100%;
            position: relative;
            z-index: 2;
        }
        
        .card {
            background: white;
            border-radius: 30px;
            padding: 40px 35px;
            box-shadow: 
                0 25px 50px rgba(255, 107, 157, 0.2),
                0 0 0 12px white,
                0 0 0 25px rgba(255, 255, 255, 0.3);
            text-align: center;
            position: relative;
            border: 5px solid #ffafcc;
        }
        
        .card-header {
            margin-bottom: 25px;
        }
        
        .title {
            font-family: 'Comic Neue', cursive;
            font-size: 2.8rem;
            color: #ff6b9d;
            margin-bottom: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
        }
        
        .title i {
            font-size: 2.5rem;
            animation: heartbeat 1.2s infinite;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.1); }
            10% { transform: scale(1); }
            15% { transform: scale(1.1); }
            20% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        .question-box {
            background: linear-gradient(135deg, #fff5f9 0%, #f0f8ff 100%);
            border-radius: 20px;
            padding: 25px;
            margin: 20px 0;
            border: 4px dotted #ffafcc;
            position: relative;
        }
        
        .question-box::before {
            content: '❓';
            position: absolute;
            top: -25px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 2rem;
            background: white;
            padding: 5px 15px;
            border-radius: 50%;
            border: 3px solid #ffafcc;
        }
        
        .question {
            font-size: 2rem;
            color: #444;
            line-height: 1.4;
        }
        
        .sofia-name {
            color: #ff006e;
            font-weight: 800;
            background: #ffe5ec;
            padding: 8px 20px;
            border-radius: 50px;
            display: inline-block;
            margin: 0 8px;
            border: 3px solid #ffafcc;
            box-shadow: 0 4px 0 #ff8fab;
            transform: translateY(-2px);
        }
        
        .buttons-playground {
            position: relative;
            height: 220px;
            margin: 35px 0;
            background: #f8f9ff;
            border-radius: 25px;
            border: 4px solid #a2d2ff;
            overflow: hidden;
            box-shadow: inset 0 0 20px rgba(162, 210, 255, 0.2);
        }
        
        .oui-btn {
            background: linear-gradient(135deg, #4cd964 0%, #2ecc71 100%);
            color: white;
            border: none;
            padding: 22px 60px;
            font-size: 1.9rem;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 
                0 10px 25px rgba(76, 217, 100, 0.4),
                0 0 0 5px rgba(255, 255, 255, 0.8);
            position: absolute;
            top: 30px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 2;
            transition: all 0.3s;
            font-weight: 800;
            letter-spacing: 1px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .oui-btn:hover {
            transform: translateX(-50%) scale(1.08);
            box-shadow: 
                0 15px 30px rgba(76, 217, 100, 0.6),
                0 0 0 5px rgba(255, 255, 255, 0.8);
            animation: wiggle 0.5s ease;
        }
        
        @keyframes wiggle {
            0%, 100% { transform: translateX(-50%) rotate(0deg); }
            25% { transform: translateX(-50%) rotate(-5deg); }
            75% { transform: translateX(-50%) rotate(5deg); }
        }
        
        .non-btn {
            background: linear-gradient(135deg, #ff8fab 0%, #ff5c8d 100%);
            color: white;
            border: none;
            padding: 20px 50px;
            font-size: 1.7rem;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 
                0 8px 20px rgba(255, 92, 141, 0.4),
                0 0 0 4px rgba(255, 255, 255, 0.8);
            position: absolute;
            top: 120px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 3;
            transition: all 0.2s;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .non-btn .shy-text {
            font-size: 1rem;
            opacity: 0.9;
            margin-left: 8px;
            font-weight: 600;
            font-style: italic;
        }
        
        .message {
            font-size: 1.5rem;
            color: #ff6b9d;
            margin: 25px 0;
            min-height: 50px;
            font-weight: 700;
            padding: 15px 25px;
            background: #fff5f9;
            border-radius: 15px;
            border: 3px solid #ffafcc;
            display: none;
            animation: messagePop 0.5s ease;
        }
        
        @keyframes messagePop {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .celebration {
            display: none;
            margin-top: 25px;
            animation: celebrateIn 1s ease;
        }
        
        @keyframes celebrateIn {
            0% { transform: scale(0); opacity: 0; }
            60% { transform: scale(1.1); }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .celebration-gif {
            width: 100%;
            max-width: 350px;
            border-radius: 20px;
            margin: 20px 0;
            border: 6px solid #ffafcc;
            box-shadow: 0 15px 30px rgba(255, 107, 157, 0.3);
        }
        
        .yay-text {
            font-family: 'Comic Neue', cursive;
            font-size: 3rem;
            color: #ff006e;
            font-weight: 900;
            margin: 15px 0;
            animation: bounce 0.8s infinite alternate, rainbow 4s infinite;
            text-shadow: 3px 3px 0 #ffafcc;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-20px); }
        }
        
        @keyframes rainbow {
            0% { color: #ff006e; }
            25% { color: #ff8e00; }
            50% { color: #00c851; }
            75% { color: #2d8cff; }
            100% { color: #ff006e; }
        }
        
        .counter {
            font-size: 1.3rem;
            color: #666;
            margin-top: 20px;
            background: linear-gradient(135deg, #f8f9ff 0%, #fff5f9 100%);
            padding: 12px 25px;
            border-radius: 50px;
            display: inline-block;
            border: 3px solid #a2d2ff;
            font-weight: 700;
        }
        
        .counter i {
            color: #ff6b9d;
            margin-right: 8px;
        }
        
        .footer {
            margin-top: 25px;
            color: #999;
            font-size: 1rem;
            font-style: italic;
        }
        
        .cute-animal {
            position: absolute;
            font-size: 3rem;
            z-index: 1;
            animation: float 3s ease-in-out infinite;
        }
        
        .cat { top: 20px; left: 20px; }
        .rabbit { top: 20px; right: 20px; animation-delay: 0.5s; }
        .panda { bottom: 20px; left: 20px; animation-delay: 1s; }
        .unicorn { bottom: 20px; right: 20px; animation-delay: 1.5s; }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(5deg); }
        }
        
        /* Mobile responsive */
        @media (max-width: 600px) {
            .card {
                padding: 30px 20px;
            }
            
            .title {
                font-size: 2.2rem;
            }
            
            .title i {
                font-size: 2rem;
            }
            
            .question {
                font-size: 1.7rem;
            }
            
            .oui-btn, .non-btn {
                padding: 18px 40px;
                font-size: 1.6rem;
            }
            
            .non-btn {
                font-size: 1.4rem;
            }
            
            .yay-text {
                font-size: 2.5rem;
            }
            
            .cute-animal {
                font-size: 2.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Bubbles background -->
    <div class="bubbles" id="bubbles"></div>
    
    <!-- Cute animals -->
    <div class="cute-animal cat">🐱</div>
    <div class="cute-animal rabbit">🐰</div>
    <div class="cute-animal panda">🐼</div>
    <div class="cute-animal unicorn">🦄</div>
    
    <div class="container">
        <div class="card">
            <div class="card-header">
                <h1 class="title">
                    <i class="fas fa-star"></i>
                    Question Spéciale
                    <i class="fas fa-star"></i>
                </h1>
            </div>
            
            <div class="question-box">
                <p class="question">
                    <span class="sofia-name">Sofia</span>, 
                    veux-tu sortir avec moi vendredi ? 
                    <span style="font-size: 2.5rem;">🥰</span>
                </p>
            </div>
            
            <div class="buttons-playground" id="playground">
                <button class="oui-btn" id="ouiBtn">
                    <i class="fas fa-heart"></i> OUI ! <i class="fas fa-heart"></i>
                </button>
                <button class="non-btn" id="nonBtn">
                    <i class="fas fa-grin-tongue-squint"></i> Non 
                    <span class="shy-text">(timide 😈)</span>
                </button>
            </div>
            
            <div class="message" id="message"></div>
            
            <div class="celebration" id="celebration">
                <img class="celebration-gif" src="https://media.giphy.com/media/26tknCqiJrBQG6DrC/giphy.gif" alt="Celebration">
                <div class="yay-text">🎉 YOUPIIII! À VENDREDI! 🎉</div>
            </div>
            
            <div class="counter">
                <i class="fas fa-running"></i> Le bouton s'est échappé: 
                <span id="counter">0</span> fois
            </div>
            
            <div class="footer">
                <p>✨ Le bouton "Non" est très timide... il fuit quand tu t'approches! ✨</p>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const ouiBtn = document.getElementById('ouiBtn');
            const nonBtn = document.getElementById('nonBtn');
            const message = document.getElementById('message');
            const celebration = document.getElementById('celebration');
            const counter = document.getElementById('counter');
            const playground = document.getElementById('playground');
            const bubbles = document.getElementById('bubbles');
            
            let escapeCount = 0;
            let isMoving = false;
            
            // Create floating bubbles
            function createBubbles() {
                for (let i = 0; i < 20; i++) {
                    const bubble = document.createElement('div');
                    bubble.className = 'bubble';
                    const size = Math.random() * 60 + 20;
                    bubble.style.width = `${size}px`;
                    bubble.style.height = `${size}px`;
                    bubble.style.left = `${Math.random() * 100}vw`;
                    bubble.style.animationDelay = `${Math.random() * 15}s`;
                    bubble.style.opacity = `${Math.random() * 0.4 + 0.2}`;
                    bubbles.appendChild(bubble);
                }
            }
            
            // Position the non button initially
            nonBtn.style.position = 'absolute';
            nonBtn.style.left = '50%';
            nonBtn.style.top = '120px';
            nonBtn.style.transform = 'translateX(-50%)';
            
            // Make NON button escape when mouse gets close
            playground.addEventListener('mousemove', function(event) {
                if (isMoving) return;
                
                const rect = playground.getBoundingClientRect();
                const mouseX = event.clientX - rect.left;
                const mouseY = event.clientY - rect.top;
                
                const btnRect = nonBtn.getBoundingClientRect();
                const btnX = btnRect.left - rect.left + nonBtn.offsetWidth / 2;
                const btnY = btnRect.top - rect.top + nonBtn.offsetHeight / 2;
                
                // Distance between mouse and button
                const distance = Math.sqrt(
                    Math.pow(mouseX - btnX, 2) + 
                    Math.pow(mouseY - btnY, 2)
                );
                
                // If mouse is within 90px, escape!
                if (distance < 90) {
                    isMoving = true;
                    escapeCount++;
                    counter.textContent = escapeCount;
                    
                    // Play cute sound effect (using emoji animation instead)
                    const emoji = document.createElement('div');
                    emoji.innerHTML = '💨';
                    emoji.style.position = 'absolute';
                    emoji.style.left = `${btnX}px`;
                    emoji.style.top = `${btnY}px`;
                    emoji.style.fontSize = '30px';
                    emoji.style.zIndex = '10';
                    emoji.style.pointerEvents = 'none';
                    playground.appendChild(emoji);
                    
                    // Animate emoji
                    emoji.animate([
                        { transform: 'scale(1) rotate(0deg)', opacity: 1 },
                        { transform: 'scale(1.5) rotate(180deg) translateX(50px)', opacity: 0 }
                    ], {
                        duration: 600,
                        easing: 'ease-out'
                    });
                    
                    setTimeout(() => emoji.remove(), 600);
                    
                    // Calculate escape direction (opposite of mouse)
                    const angle = Math.atan2(btnY - mouseY, btnX - mouseX);
                    const escapeDist = 120 + Math.random() * 100;
                    
                    // New position
                    let newX = btnX + Math.cos(angle) * escapeDist;
                    let newY = btnY + Math.sin(angle) * escapeDist;
                    
                    // Keep inside playground
                    const maxX = playground.offsetWidth - nonBtn.offsetWidth;
                    const maxY = playground.offsetHeight - nonBtn.offsetHeight;
                    
                    newX = Math.max(15, Math.min(newX, maxX - 15));
                    newY = Math.max(15, Math.min(newY, maxY - 15));
                    
                    // Move button with bounce effect
                    nonBtn.style.transition = 'all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55)';
                    nonBtn.style.left = `${newX}px`;
                    nonBtn.style.top = `${newY}px`;
                    
                    // Cute messages
                    const messages = [
                        "Oops! Il s'échappe! 🏃‍♂️",
                        "Trop rapide! ⚡",
                        "Haha! Encore raté! 😂",
                        "Il est insaisissable! 🎯",
                        "Presque... mais non! 😅",
                        "Tu y es presque! 👀",
                        "Dernière chance! 🎉",
                        "Ok ok... clique sur OUI! 🥰"
                    ];
                    
                    if (escapeCount <= messages.length) {
                        message.textContent = messages[escapeCount - 1];
                        message.style.display = 'block';
                    }
                    
                    // Make button cuter as it escapes
                    const scale = Math.max(0.45, 1 - escapeCount * 0.07);
                    const hue = 340 - escapeCount * 10;
                    nonBtn.style.transform = `scale(${scale})`;
                    nonBtn.style.background = `linear-gradient(135deg, hsl(${hue}, 100%, 75%) 0%, hsl(${hue}, 100%, 65%) 100%)`;
                    
                    // Add cute wiggle
                    setTimeout(() => {
                        nonBtn.style.transform = `scale(${scale}) rotate(8deg)`;
                        setTimeout(() => {
                            nonBtn.style.transform = `scale(${scale}) rotate(-8deg)`;
                            setTimeout(() => {
                                nonBtn.style.transform = `scale(${scale}) rotate(0deg)`;
                                isMoving = false;
                            }, 150);
                        }, 150);
                    }, 400);
                    
                    // After 8 escapes, button disappears
                    if (escapeCount >= 8) {
                        setTimeout(() => {
                            nonBtn.style.opacity = '0';
                            nonBtn.style.transform = 'scale(0.5)';
                            setTimeout(() => {
                                nonBtn.style.display = 'none';
                                message.textContent = "YAY! Maintenant clique sur OUI! 🎊";
                            }, 300);
                        }, 400);
                    }
                }
            });
            
            // Prevent clicking by escaping on mouseenter too
            nonBtn.addEventListener('mouseenter', function() {
                if (!isMoving) {
                    // Simulate mousemove to trigger escape
                    const event = new MouseEvent('mousemove', {
                        clientX: event.clientX,
                        clientY: event.clientY
                    });
                    playground.dispatchEvent(event);
                }
            });
            
            // When OUI is clicked
            ouiBtn.addEventListener('click', function() {
                // Hide everything
                ouiBtn.style.display = 'none';
                if (nonBtn.style.display !== 'none') nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Show celebration
                celebration.style.display = 'block';
                
                // Create lots of floating hearts
                for (let i = 0; i < 100; i++) {
                    setTimeout(() => {
                        const heart = document.createElement('div');
                        heart.innerHTML = ['💖', '💕', '💗', '💓', '❤️', '🥰'][Math.floor(Math.random() * 6)];
                        heart.style.position = 'fixed';
                        heart.style.left = Math.random() * 100 + 'vw';
                        heart.style.fontSize = (Math.random() * 30 + 20) + 'px';
                        heart.style.zIndex = '1000';
                        heart.style.opacity = '0.9';
                        
                        document.body.appendChild(heart);
                        
                        // Animate heart
                        heart.animate([
                            { transform: 'translateY(100vh) rotate(0deg)', opacity: 1 },
                            { transform: `translateY(-100px) rotate(${Math.random() * 360}deg)`, opacity: 0 }
                        ], {
                            duration: Math.random() * 3000 + 2000,
                            easing: 'cubic-bezier(0.215, 0.61, 0.355, 1)'
                        });
                        
                        setTimeout(() => heart.remove(), 5000);
                    }, i * 30);
                }
                
                // Change background to party mode
                document.body.style.background = 'linear-gradient(135deg, #ffafcc 0%, #cdb4db 33%, #bde0fe 66%, #a2d2ff 100%)';
                document.body.style.animation = 'rainbowBG 10s infinite alternate';
                
                // Add rainbow background animation
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes rainbowBG {
                        0% { filter: hue-rotate(0deg); }
                        100% { filter: hue-rotate(360deg); }
                    }
                `;
                document.head.appendChild(style);
            });
            
            // Initialize bubbles
            createBubbles();
        });
    </script>
</body>
</html>
