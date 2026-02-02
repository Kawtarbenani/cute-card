# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Question pour Sofia</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial Rounded MT Bold', 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #ffafcc 0%, #a2d2ff 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
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
            font-size: 2.5rem;
            color: #ff006e;
            margin-bottom: 20px;
            text-shadow: 2px 2px 0 #ffafcc;
        }
        
        .question {
            font-size: 1.8rem;
            color: #333;
            margin-bottom: 30px;
            padding: 15px;
            background: #f8f9fa;
            border-radius: 15px;
            border: 3px dashed #ffafcc;
        }
        
        .sofia-name {
            color: #ff006e;
            font-weight: bold;
            background: #ffafcc;
            padding: 5px 15px;
            border-radius: 20px;
            display: inline-block;
            margin: 0 5px;
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
            background: #4cd964;
            color: white;
            border: none;
            padding: 18px 50px;
            font-size: 1.8rem;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(76, 217, 100, 0.4);
            position: absolute;
            top: 30px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 2;
            transition: all 0.3s;
            font-weight: bold;
        }
        
        .oui-btn:hover {
            transform: translateX(-50%) scale(1.1);
            box-shadow: 0 12px 25px rgba(76, 217, 100, 0.6);
        }
        
        .non-btn {
            background: #ff5c8d;
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 6px 15px rgba(255, 92, 141, 0.4);
            position: absolute;
            top: 110px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 3;
            transition: all 0.2s;
            font-weight: bold;
        }
        
        .non-btn span {
            font-size: 0.9rem;
            opacity: 0.8;
            margin-left: 8px;
        }
        
        .message {
            font-size: 1.3rem;
            color: #ff006e;
            margin: 20px 0;
            min-height: 40px;
            font-weight: bold;
            padding: 10px;
            background: #fff5f9;
            border-radius: 10px;
            display: none;
        }
        
        .celebration {
            display: none;
            margin-top: 20px;
        }
        
        .celebration-gif {
            width: 100%;
            max-width: 300px;
            border-radius: 15px;
            margin: 15px 0;
        }
        
        .yay-text {
            font-size: 2.5rem;
            color: #ff006e;
            font-weight: bold;
            margin: 10px 0;
            animation: bounce 0.8s infinite alternate;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-15px); }
        }
        
        .counter {
            font-size: 1.1rem;
            color: #666;
            margin-top: 15px;
            background: #f8f9fa;
            padding: 8px 15px;
            border-radius: 20px;
            display: inline-block;
        }
        
        .emoji {
            font-size: 1.3em;
        }
        
        .footer {
            margin-top: 20px;
            color: #888;
            font-size: 0.9rem;
        }
        
        /* Mobile responsive */
        @media (max-width: 600px) {
            .card {
                padding: 30px 20px;
            }
            
            .title {
                font-size: 2rem;
            }
            
            .question {
                font-size: 1.5rem;
            }
            
            .oui-btn, .non-btn {
                padding: 15px 30px;
                font-size: 1.5rem;
            }
            
            .non-btn {
                font-size: 1.3rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <h1 class="title">👋 Question pour toi!</h1>
            
            <div class="question">
                <span class="sofia-name">Sofia</span>, 
                veux-tu sortir vendredi ? 😊
            </div>
            
            <div class="buttons-container" id="buttonsArea">
                <button class="oui-btn" id="ouiBtn">
                    <i class="fas fa-check"></i> OUI !
                </button>
                <button class="non-btn" id="nonBtn">
                    <i class="fas fa-times"></i> Non <span>(a bit shy 😈)</span>
                </button>
            </div>
            
            <div class="message" id="message"></div>
            
            <div class="celebration" id="celebration">
                <img class="celebration-gif" src="https://media.giphy.com/media/26tknCqiJrBQG6DrC/giphy.gif" alt="Celebration">
                <div class="yay-text">🎉 YAY! À vendredi! 🎉</div>
            </div>
            
            <div class="counter">
                ✨ Essaies: <span id="counter">0</span>
            </div>
            
            <div class="footer">
                <p>PS: Le bouton "Non" est un peu timide... 😉</p>
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
            const buttonsArea = document.getElementById('buttonsArea');
            
            let escapeCount = 0;
            let isNonBtnMoving = false;
            
            // Make NON button escape when mouse gets close (BEFORE clicking!)
            buttonsArea.addEventListener('mousemove', function(event) {
                const rect = buttonsArea.getBoundingClientRect();
                const mouseX = event.clientX - rect.left;
                const mouseY = event.clientY - rect.top;
                
                const btnRect = nonBtn.getBoundingClientRect();
                const btnX = btnRect.left - rect.left + nonBtn.offsetWidth / 2;
                const btnY = btnRect.top - rect.top + nonBtn.offsetHeight / 2;
                
                // Distance between mouse and button center
                const distance = Math.sqrt(
                    Math.pow(mouseX - btnX, 2) + 
                    Math.pow(mouseY - btnY, 2)
                );
                
                // If mouse is within 80px of button, move it away
                if (distance < 80 && !isNonBtnMoving) {
                    isNonBtnMoving = true;
                    escapeCount++;
                    counter.textContent = escapeCount;
                    
                    // Calculate escape direction (away from mouse)
                    const escapeAngle = Math.atan2(btnY - mouseY, btnX - mouseX);
                    const escapeDistance = 150 + Math.random() * 100;
                    
                    // Calculate new position
                    let newX = btnX + Math.cos(escapeAngle) * escapeDistance;
                    let newY = btnY + Math.sin(escapeAngle) * escapeDistance;
                    
                    // Keep button inside container
                    const maxX = buttonsArea.offsetWidth - nonBtn.offsetWidth;
                    const maxY = buttonsArea.offsetHeight - nonBtn.offsetHeight;
                    
                    newX = Math.max(10, Math.min(newX, maxX - 10));
                    newY = Math.max(10, Math.min(newY, maxY - 10));
                    
                    // Apply movement with animation
                    nonBtn.style.transition = 'all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1)';
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
                    const scale = Math.max(0.5, 1 - escapeCount * 0.05);
                    nonBtn.style.transform = `scale(${scale})`;
                    
                    // Change button color
                    const red = Math.min(255, 255 - escapeCount * 20);
                    nonBtn.style.backgroundColor = `rgb(${red}, 92, 141)`;
                    
                    // Add wiggle effect
                    setTimeout(() => {
                        nonBtn.style.transform = `scale(${scale}) rotate(5deg)`;
                        setTimeout(() => {
                            nonBtn.style.transform = `scale(${scale}) rotate(-5deg)`;
                            setTimeout(() => {
                                nonBtn.style.transform = `scale(${scale}) rotate(0deg)`;
                                isNonBtnMoving = false;
                            }, 100);
                        }, 100);
                    }, 400);
                    
                    // After 8 escapes, make button disappear
                    if (escapeCount >= 8) {
                        setTimeout(() => {
                            nonBtn.style.display = 'none';
                            message.textContent = "Trop tard! Clique sur OUI maintenant! 😄";
                        }, 400);
                    }
                }
            });
            
            // Also make button escape if somehow mouse gets on it
            nonBtn.addEventListener('mouseenter', function(event) {
                if (!isNonBtnMoving) {
                    // Trigger a fake mousemove to escape
                    const fakeEvent = new MouseEvent('mousemove', {
                        clientX: event.clientX,
                        clientY: event.clientY
                    });
                    buttonsArea.dispatchEvent(fakeEvent);
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
            
            // Initial button position (centered)
            nonBtn.style.position = 'absolute';
            nonBtn.style.left = '50%';
            nonBtn.style.top = '110px';
            nonBtn.style.transform = 'translateX(-50%)';
        });
    </script>
</body>
</html>
