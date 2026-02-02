# cute-card
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
            justify-content: center;
            align-items: center;
            padding: 20px;
            position: relative;
            overflow: hidden;
            cursor: default;
        }
        
        .container {
            max-width: 500px;
            width: 100%;
            z-index: 10;
            position: relative;
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
        }
        
        .question-box {
            background: linear-gradient(135deg, #fff5f9 0%, #f0f8ff 100%);
            border-radius: 18px;
            padding: 25px;
            margin: 25px 0 40px 0;
            border: 3px dashed #ffafcc;
        }
        
        .question {
            font-size: 1.7rem;
            color: #444;
            line-height: 1.4;
            padding: 10px 0;
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
        
        .buttons-area {
            position: relative;
            margin: 30px 0;
            min-height: 120px;
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
            z-index: 5;
            transition: all 0.3s;
            font-weight: 800;
            display: inline-flex;
            align-items: center;
            gap: 15px;
            margin-top: 20px;
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
            position: fixed;
            z-index: 100;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: none !important;
            animation: none !important;
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
        }
        
        @keyframes messagePop {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .celebration {
            display: none;
            margin-top: 30px;
            animation: celebrateIn 0.8s ease;
        }
        
        @keyframes celebrateIn {
            0% { transform: scale(0); opacity: 0; }
            60% { transform: scale(1.1); }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .celebration-gif {
            width: 100%;
            max-width: 300px;
            border-radius: 20px;
            margin: 20px 0;
            border: 5px solid #ffafcc;
            box-shadow: 0 15px 30px rgba(255, 107, 157, 0.3);
        }
        
        .yay-text {
            font-family: 'Comic Neue', cursive;
            font-size: 2.5rem;
            color: #ff006e;
            font-weight: 900;
            margin: 15px 0;
            animation: bounce 0.6s infinite alternate;
            text-shadow: 3px 3px 0 #ffafcc;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-15px); }
        }
        
        .footer {
            margin-top: 30px;
            color: #888;
            font-size: 1rem;
            font-style: italic;
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
                font-size: 2rem;
            }
            
            .cute-emoji {
                font-size: 1.6rem;
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
            <h1 class="title">Question pour toi ✨</h1>
            
            <div class="question-box">
                <p class="question">
                    <span class="sofia-name">Sofia</span><br>
                    veux-tu sortir vendredi ? 
                    <span style="font-size: 2rem; display: block; margin-top: 15px;">😊</span>
                </p>
            </div>
            
            <div class="buttons-area">
                <button class="oui-btn" id="ouiBtn">
                    <i class="fas fa-heart"></i> OUI !
                </button>
                <button class="non-btn" id="nonBtn">
                    <i class="fas fa-grin-tongue-squint"></i> Non 
                    <span class="shy-text">(shy 😈)</span>
                </button>
            </div>
            
            <div class="message" id="message"></div>
            
            <div class="celebration" id="celebration">
                <img class="celebration-gif" src="https://media.giphy.com/media/26tknCqiJrBQG6DrC/giphy.gif" alt="Celebration">
                <div class="yay-text">🎉 YAY! À vendredi! 🎉</div>
            </div>
            
            <div class="footer">
                <p>Le bouton "Non" fuit SUPER VITE! 😉</p>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const ouiBtn = document.getElementById('ouiBtn');
            const nonBtn = document.getElementById('nonBtn');
            const message = document.getElementById('message');
            const celebration = document.getElementById('celebration');
            
            let lastMoveTime = 0;
            let isCelebrating = false;
            
            // Position non button initially
            nonBtn.style.left = '50%';
            nonBtn.style.top = '50%';
            nonBtn.style.transform = 'translate(-50%, -50%)';
            
            // Make button escape FAST when mouse gets close
            document.addEventListener('mousemove', function(event) {
                if (isCelebrating) return;
                
                const now = Date.now();
                if (now - lastMoveTime < 100) return; // Limit to 10 moves per second max
                
                const btnRect = nonBtn.getBoundingClientRect();
                const btnCenterX = btnRect.left + btnRect.width / 2;
                const btnCenterY = btnRect.top + btnRect.height / 2;
                
                const distance = Math.sqrt(
                    Math.pow(event.clientX - btnCenterX, 2) + 
                    Math.pow(event.clientY - btnCenterY, 2)
                );
                
                // If mouse is within 120px of button, ESCAPE FAST!
                if (distance < 120) {
                    lastMoveTime = now;
                    
                    // Calculate escape direction
                    const angle = Math.atan2(btnCenterY - event.clientY, btnCenterX - event.clientX);
                    
                    // Random escape distance (shorter for faster response)
                    const escapeDistance = 100 + Math.random() * 150;
                    
                    // Calculate new position
                    let newX = btnCenterX + Math.cos(angle) * escapeDistance;
                    let newY = btnCenterY + Math.sin(angle) * escapeDistance;
                    
                    // Keep button within viewport
                    const padding = 30;
                    newX = Math.max(padding, Math.min(newX, window.innerWidth - nonBtn.offsetWidth - padding));
                    newY = Math.max(padding, Math.min(newY, window.innerHeight - nonBtn.offsetHeight - padding));
                    
                    // INSTANT movement (no transition)
                    nonBtn.style.left = `${newX}px`;
                    nonBtn.style.top = `${newY}px`;
                    nonBtn.style.transform = 'translate(0, 0)';
                    
                    // Show message (but not every time to avoid spam)
                    if (Math.random() > 0.7) {
                        const messages = [
                            "Trop rapide! ⚡",
                            "Raté! 😆",
                            "Pas si vite! 🏃‍♂️",
                            "Haha! 😈",
                            "Essaie encore! 💨",
                            "Presque! 🙈",
                            "Trop lent! 😄",
                            "Attrape-moi! 🎯"
                        ];
                        message.textContent = messages[Math.floor(Math.random() * messages.length)];
                        message.style.display = 'block';
                        
                        // Hide message after 1 second
                        setTimeout(() => {
                            if (!isCelebrating) {
                                message.style.display = 'none';
                            }
                        }, 1000);
                    }
                    
                    // Add quick visual effect
                    nonBtn.style.boxShadow = '0 0 0 3px rgba(255, 255, 255, 0.8)';
                    setTimeout(() => {
                        nonBtn.style.boxShadow = '0 8px 20px rgba(255, 92, 141, 0.4)';
                    }, 100);
                    
                    // Sometimes teleport to random location for extra challenge
                    if (Math.random() > 0.85) {
                        setTimeout(() => {
                            const randomX = Math.random() * (window.innerWidth - nonBtn.offsetWidth - 60) + 30;
                            const randomY = Math.random() * (window.innerHeight - nonBtn.offsetHeight - 60) + 30;
                            nonBtn.style.left = `${randomX}px`;
                            nonBtn.style.top = `${randomY}px`;
                            
                            // Teleport effect
                            const teleport = document.createElement('div');
                            teleport.innerHTML = '🌀';
                            teleport.style.position = 'fixed';
                            teleport.style.left = `${randomX}px`;
                            teleport.style.top = `${randomY}px`;
                            teleport.style.fontSize = '30px';
                            teleport.style.zIndex = '99';
                            teleport.style.opacity = '0';
                            teleport.style.transform = 'scale(0)';
                            document.body.appendChild(teleport);
                            
                            // Animate teleport effect
                            teleport.animate([
                                { transform: 'scale(0)', opacity: 0 },
                                { transform: 'scale(1.5)', opacity: 0.7 },
                                { transform: 'scale(0)', opacity: 0 }
                            ], {
                                duration: 400,
                                easing: 'ease-out'
                            });
                            
                            setTimeout(() => teleport.remove(), 400);
                        }, 50);
                    }
                    
                    // Make button slightly smaller sometimes
                    if (Math.random() > 0.5) {
                        const scale = 0.85 + Math.random() * 0.15;
                        nonBtn.style.transform = `scale(${scale})`;
                    }
                }
            });
            
            // Also escape immediately if mouse enters button
            nonBtn.addEventListener('mouseenter', function(event) {
                // Trigger immediate escape
                const fakeEvent = new MouseEvent('mousemove', {
                    clientX: event.clientX,
                    clientY: event.clientY
                });
                document.dispatchEvent(fakeEvent);
            });
            
            // Try to click the button (will be very hard!)
            nonBtn.addEventListener('mousedown', function(event) {
                event.preventDefault();
                
                // Even on click attempt, move away
                const fakeEvent = new MouseEvent('mousemove', {
                    clientX: event.clientX + 150,
                    clientY: event.clientY + 150
                });
                document.dispatchEvent(fakeEvent);
                
                // Show "almost" message
                message.textContent = "Haha! Presque réussi! 😅";
                message.style.display = 'block';
                
                // Make button jump
                nonBtn.style.transform = 'translateY(-20px)';
                setTimeout(() => {
                    nonBtn.style.transform = 'translateY(0)';
                }, 200);
            });
            
            // When OUI is clicked
            ouiBtn.addEventListener('click', function() {
                isCelebrating = true;
                
                // Remove all event listeners
                document.removeEventListener('mousemove', arguments.callee);
                
                // Hide buttons
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Show celebration
                celebration.style.display = 'block';
                
                // Create massive fast confetti
                for (let i = 0; i < 100; i++) {
                    setTimeout(() => {
                        createConfetti();
                    }, i * 15);
                }
                
                // Change background
                document.body.style.background = 'linear-gradient(135deg, #ff9ec0 0%, #a29bfe 50%, #74b9ff 100%)';
                
                // Add sparkle effect
                for (let i = 0; i < 20; i++) {
                    setTimeout(() => {
                        createSparkle();
                    }, i * 100);
                }
            });
            
            // Create fast confetti
            function createConfetti() {
                const confetti = document.createElement('div');
                confetti.innerHTML = ['🎉', '✨', '🎊', '🥳', '💖', '🌟'][Math.floor(Math.random() * 6)];
                confetti.style.position = 'fixed';
                confetti.style.fontSize = (Math.random() * 25 + 15) + 'px';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-50px';
                confetti.style.zIndex = '1000';
                confetti.style.opacity = '0.9';
                
                document.body.appendChild(confetti);
                
                // Fast animation
                const duration = Math.random() * 1000 + 500;
                
                confetti.animate([
                    { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                    { transform: `translateY(${window.innerHeight + 100}px) rotate(${Math.random() * 720}deg)`, opacity: 0 }
                ], {
                    duration: duration,
                    easing: 'cubic-bezier(0.215, 0.61, 0.355, 1)'
                });
                
                setTimeout(() => confetti.remove(), duration);
            }
            
            // Create sparkle effect
            function createSparkle() {
                const sparkle = document.createElement('div');
                sparkle.innerHTML = '✨';
                sparkle.style.position = 'fixed';
                sparkle.style.fontSize = '40px';
                sparkle.style.left = Math.random() * 100 + 'vw';
                sparkle.style.top = Math.random() * 100 + 'vh';
                sparkle.style.zIndex = '1001';
                sparkle.style.opacity = '0';
                
                document.body.appendChild(sparkle);
                
                sparkle.animate([
                    { transform: 'scale(0) rotate(0deg)', opacity: 0 },
                    { transform: 'scale(1.5) rotate(180deg)', opacity: 0.8 },
                    { transform: 'scale(0) rotate(360deg)', opacity: 0 }
                ], {
                    duration: 800,
                    easing: 'ease-out'
                });
                
                setTimeout(() => sparkle.remove(), 800);
            }
            
            // Handle window resize
            window.addEventListener('resize', function() {
                const btnRect = nonBtn.getBoundingClientRect();
                if (btnRect.left < 0 || btnRect.top < 0 || 
                    btnRect.right > window.innerWidth || btnRect.bottom > window.innerHeight) {
                    nonBtn.style.left = '50%';
                    nonBtn.style.top = '50%';
                    nonBtn.style.transform = 'translate(-50%, -50%)';
                }
            });
            
            // Initial message
            message.textContent = "Essaie de cliquer sur 'Non'... si tu peux! 😈";
            message.style.display = 'block';
        });
    </script>
</body>
</html>
