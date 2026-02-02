# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Question pour Sofia</title>
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
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 500px;
            width: 100%;
        }
        
        .card {
            background: white;
            border-radius: 25px;
            padding: 40px 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
            text-align: center;
            border: 8px solid #ffafcc;
            position: relative;
            overflow: hidden;
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
            font-size: 2.5rem;
            color: #ff006e;
            margin-bottom: 20px;
            text-shadow: 2px 2px 0 #ffafcc;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
        }
        
        .title i {
            font-size: 2.2rem;
            animation: heartbeat 1.2s infinite;
            color: #ff6b9d;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.1); }
            10% { transform: scale(1); }
            15% { transform: scale(1.1); }
            20% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        .question {
            font-size: 2rem;
            color: #333;
            margin-bottom: 30px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 15px;
            border: 3px dashed #ffafcc;
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
        
        .buttons-container {
            position: relative;
            height: 200px;
            margin: 30px 0;
            background: #f8f9fa;
            border-radius: 20px;
            border: 3px solid #a2d2ff;
            overflow: hidden;
        }
        
        .oui-btn {
            background: linear-gradient(135deg, #4cd964 0%, #2ecc71 100%);
            color: white;
            border: none;
            padding: 20px 60px;
            font-size: 1.9rem;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(76, 217, 100, 0.4);
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
            transform: translateX(-50%) scale(1.1);
            box-shadow: 0 15px 30px rgba(76, 217, 100, 0.6);
        }
        
        .non-btn {
            background: linear-gradient(135deg, #ff8fab 0%, #ff5c8d 100%);
            color: white;
            border: none;
            padding: 18px 50px;
            font-size: 1.7rem;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(255, 92, 141, 0.4);
            position: absolute;
            top: 110px;
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
            margin-top: 20px;
            animation: celebrateIn 1s ease;
        }
        
        @keyframes celebrateIn {
            0% { transform: scale(0); opacity: 0; }
            60% { transform: scale(1.1); }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .celebration-gif {
            width: 100%;
            max-width: 300px;
            border-radius: 15px;
            margin: 15px 0;
            border: 6px solid #ffafcc;
            box-shadow: 0 15px 30px rgba(255, 107, 157, 0.3);
        }
        
        .yay-text {
            font-family: 'Comic Neue', cursive;
            font-size: 2.8rem;
            color: #ff006e;
            font-weight: 900;
            margin: 15px 0;
            animation: bounce 0.8s infinite alternate;
            text-shadow: 3px 3px 0 #ffafcc;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-15px); }
        }
        
        .counter {
            font-size: 1.3rem;
            color: #666;
            margin-top: 20px;
            background: #f8f9fa;
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
            margin-top: 20px;
            color: #888;
            font-size: 1rem;
            font-style: italic;
        }
        
        .cute-emoji {
            position: absolute;
            font-size: 2.5rem;
            z-index: 1;
            animation: float 3s ease-in-out infinite;
        }
        
        .emoji-1 { top: 15px; left: 15px; }
        .emoji-2 { top: 15px; right: 15px; animation-delay: 0.5s; }
        .emoji-3 { bottom: 15px; left: 15px; animation-delay: 1s; }
        .emoji-4 { bottom: 15px; right: 15px; animation-delay: 1.5s; }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(5deg); }
        }
        
        /* Mobile responsive */
        @media (max-width: 600px) {
            .card {
                padding: 30px 20px;
            }
            
            .title {
                font-size: 2rem;
            }
            
            .title i {
                font-size: 1.8rem;
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
                font-size: 2.2rem;
            }
            
            .cute-emoji {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Cute emojis in corners -->
    <div class="cute-emoji emoji-1">🌸</div>
    <div class="cute-emoji emoji-2">✨</div>
    <div class="cute-emoji emoji-3">💖</div>
    <div class="cute-emoji emoji-4">🎀</div>
    
    <div class="container">
        <div class="card">
            <h1 class="title">
                <i class="fas fa-star"></i>
                Question pour toi
                <i class="fas fa-star"></i>
            </h1>
            
            <div class="question">
                <span class="sofia-name">Sofia</span>, 
                veux-tu sortir avec moi vendredi ? 
                <span style="font-size: 2.2rem;">😊</span>
            </div>
            
            <div class="buttons-container" id="playground">
                <button class="oui-btn" id="ouiBtn">
                    <i class="fas fa-check"></i> OUI !
                </button>
                <button class="non-btn" id="nonBtn">
                    <i class="fas fa-times"></i> Non 
                    <span class="shy-text">(shy 😈)</span>
                </button>
            </div>
            
            <div class="message" id="message"></div>
            
            <div class="celebration" id="celebration">
                <img class="celebration-gif" src="https://media.giphy.com/media/26tknCqiJrBQG6DrC/giphy.gif" alt="Celebration">
                <div class="yay-text">🎉 YAY! À vendredi! 🎉</div>
            </div>
            
            <div class="counter">
                <i class="fas fa-running"></i> Essaies: 
                <span id="counter">0</span>
            </div>
            
            <div class="footer">
                <p>Le bouton "Non" fuit quand tu t'approches! 😉</p>
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
            
            let escapeCount = 0;
            let isMoving = false;
            
            // Position the non button initially
            nonBtn.style.position = 'absolute';
            nonBtn.style.left = '50%';
            nonBtn.style.top = '110px';
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
                
                // If mouse is within 80px, escape!
                if (distance < 80) {
                    isMoving = true;
                    escapeCount++;
                    counter.textContent = escapeCount;
                    
                    // Calculate escape direction (away from mouse)
                    const angle = Math.atan2(btnY - mouseY, btnX - mouseX);
                    const escapeDist = 150 + Math.random() * 100;
                    
                    // New position
                    let newX = btnX + Math.cos(angle) * escapeDist;
                    let newY = btnY + Math.sin(angle) * escapeDist;
                    
                    // Keep inside playground
                    const maxX = playground.offsetWidth - nonBtn.offsetWidth;
                    const maxY = playground.offsetHeight - nonBtn.offsetHeight;
                    
                    newX = Math.max(10, Math.min(newX, maxX - 10));
                    newY = Math.max(10, Math.min(newY, maxY - 10));
                    
                    // Move button with animation
                    nonBtn.style.transition = 'all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55)';
                    nonBtn.style.left = newX + 'px';
                    nonBtn.style.top = newY + 'px';
                    
                    // Show message
                    if (escapeCount === 1) {
                        message.textContent = "Haha! Il s'échappe! 😆";
                        message.style.display = 'block';
                    } else if (escapeCount === 3) {
                        message.textContent = "Il ne veut pas être cliqué! 🏃‍♂️";
                    } else if (escapeCount === 5) {
                        message.textContent = "Il est trop rapide! ⚡";
                    } else if (escapeCount === 7) {
                        message.textContent = "Bon OK... clique sur OUI alors! 😅";
                    }
                    
                    // Make button smaller and change color
                    const scale = Math.max(0.5, 1 - escapeCount * 0.07);
                    nonBtn.style.transform = `scale(${scale})`;
                    
                    // Change button color gradient
                    const hue = 340 - escapeCount * 15;
                    nonBtn.style.background = `linear-gradient(135deg, hsl(${hue}, 100%, 75%) 0%, hsl(${hue}, 100%, 65%) 100%)`;
                    
                    // Add wiggle effect
                    setTimeout(() => {
                        nonBtn.style.transform = `scale(${scale}) rotate(5deg)`;
                        setTimeout(() => {
                            nonBtn.style.transform = `scale(${scale}) rotate(-5deg)`;
                            setTimeout(() => {
                                nonBtn.style.transform = `scale(${scale}) rotate(0deg)`;
                                isMoving = false;
                            }, 100);
                        }, 100);
                    }, 400);
                    
                    // After 8 escapes, make button disappear
                    if (escapeCount >= 8) {
                        setTimeout(() => {
                            nonBtn.style.opacity = '0';
                            nonBtn.style.transform = 'scale(0.5)';
                            setTimeout(() => {
                                nonBtn.style.display = 'none';
                                message.textContent = "Trop tard! Clique sur OUI maintenant! 😄";
                            }, 300);
                        }, 400);
                    }
                }
            });
            
            // Also make button escape if somehow mouse gets on it
            nonBtn.addEventListener('mouseenter', function(event) {
                if (!isMoving) {
                    // Trigger a fake mousemove to escape
                    const fakeEvent = new MouseEvent('mousemove', {
                        clientX: event.clientX,
                        clientY: event.clientY
                    });
                    playground.dispatchEvent(fakeEvent);
                }
            });
            
            // When OUI is clicked
            ouiBtn.addEventListener('click', function() {
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Show celebration
                celebration.style.display = 'block';
                
                // Add confetti effect
                for (let i = 0; i < 50; i++) {
                    createConfetti();
                }
            });
            
            // Create confetti particles
            function createConfetti() {
                const confetti = document.createElement('div');
                confetti.innerHTML = ['🎉', '✨', '🎊', '🥳', '💖', '🌟'][Math.floor(Math.random() * 6)];
                confetti.style.position = 'absolute';
                confetti.style.fontSize = (Math.random() * 20 + 15) + 'px';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-50px';
                confetti.style.zIndex = '1000';
                confetti.style.opacity = '0.9';
                
                document.body.appendChild(confetti);
                
                // Animation
                const animation = confetti.animate([
                    { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                    { transform: `translateY(${window.innerHeight + 100}px) rotate(${Math.random() * 360}deg)`, opacity: 0 }
                ], {
                    duration: Math.random() * 2000 + 1000,
                    easing: 'cubic-bezier(0.215, 0.61, 0.355, 1)'
                });
                
                animation.onfinish = () => confetti.remove();
            }
        });
    </script>
</body>
</html>
