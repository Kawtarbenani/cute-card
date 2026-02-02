# cute-card
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>✨ For Sofia ✨</title>
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
            font-size: 1.8rem;
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
            height: 250px;
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
            z-index: 2;
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
            position: absolute;
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
        
        .devil-emoji {
            font-size: 1.2em;
            margin-left: 10px;
            animation: devilWiggle 0.5s infinite alternate;
        }
        
        @keyframes devilWiggle {
            0% { transform: rotate(-10deg); }
            100% { transform: rotate(10deg); }
        }
        
        .shy-text {
            font-size: 0.8em;
            opacity: 0.7;
            font-style: italic;
            margin-left: 5px;
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
                font-size: 1.5rem;
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
                <h1><i class="fas fa-heart"></i> Pour Sofia <i class="fas fa-heart"></i></h1>
                <p class="invite-text">Sofia, on sort vendredi ?</p>
            </div>
            
            <div class="invitation-box">
                <p class="invite-text">Juste une soirée magique ensemble ✨</p>
                <p class="invite-text">Promis, ça sera génial ! 💖</p>
            </div>
            
            <div class="buttons-container">
                <button id="oui-btn">
                    <i class="fas fa-heart"></i> OUI ! <i class="fas fa-heart"></i>
                </button>
                <button id="non-btn">
                    Non <span class="shy-text">(a bit shy)</span> <span class="devil-emoji">😈</span>
                </button>
            </div>
            
            <div class="message-container">
                <div id="message">Fais ton choix Sofia! 💖</div>
            </div>
            
            <div class="celebration" id="celebration">
                <img class="celebration-gif" src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif" alt="Celebration">
                <div class="celebration-text">Super! À vendredi Sofia! 🥂✨</div>
            </div>
            
            <div class="counter">
                <i class="fas fa-redo"></i> Times "Non" tried to escape: <span id="counter">0</span>
            </div>
            
            <div class="footer">
                <p>Avec tout mon amour ❤️</p>
                <p class="secret-note">P.S. Essaie de cliquer sur "Non" 😉</p>
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
            let nonBtnPosition = { x: 50, y: 100 }; // Starting position
            
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
            
            // Function to move the "Non" button away from cursor
            function moveNonButtonAwayFromCursor(event) {
                const container = document.querySelector('.buttons-container');
                const containerRect = container.getBoundingClientRect();
                const buttonRect = nonBtn.getBoundingClientRect();
                
                // Get cursor position relative to container
                const cursorX = event.clientX - containerRect.left;
                const cursorY = event.clientY - containerRect.top;
                
                // Get button center position
                const buttonCenterX = nonBtn.offsetLeft + buttonRect.width / 2;
                const buttonCenterY = nonBtn.offsetTop + buttonRect.height / 2;
                
                // Calculate distance from cursor to button
                const distanceX = cursorX - buttonCenterX;
                const distanceY = cursorY - buttonCenterY;
                const distance = Math.sqrt(distanceX * distanceX + distanceY * distanceY);
                
                // If cursor is getting close to button (within 100px), move it away
                if (distance < 100) {
                    // Calculate opposite direction from cursor
                    const moveX = -distanceX * 2;
                    const moveY = -distanceY * 2;
                    
                    // Calculate new position
                    let newX = buttonCenterX + moveX - buttonRect.width / 2;
                    let newY = buttonCenterY + moveY - buttonRect.height / 2;
                    
                    // Keep button within container bounds
                    newX = Math.max(10, Math.min(newX, containerRect.width - buttonRect.width - 10));
                    newY = Math.max(10, Math.min(newY, containerRect.height - buttonRect.height - 10));
                    
                    // Apply smooth movement
                    nonBtn.style.transition = 'all 0.3s ease';
                    nonBtn.style.left = `${newX}px`;
                    nonBtn.style.top = `${newY}px`;
                    nonBtn.style.transform = 'none';
                    
                    // Add a little wobble effect
                    setTimeout(() => {
                        nonBtn.style.transform = 'rotate(5deg)';
                        setTimeout(() => {
                            nonBtn.style.transform = 'rotate(-5deg)';
                            setTimeout(() => {
                                nonBtn.style.transform = 'rotate(0deg)';
                            }, 100);
                        }, 100);
                    }, 300);
                }
            }
            
            // Function to randomly move button (when actually clicked)
            function moveNonButtonOnClick() {
                const container = document.querySelector('.buttons-container');
                const containerRect = container.getBoundingClientRect();
                const buttonRect = nonBtn.getBoundingClientRect();
                
                // More dramatic escape when clicked
                const escapeDistance = 300;
                
                // Calculate random angle for escape
                const angle = Math.random() * Math.PI * 2;
                const moveX = Math.cos(angle) * escapeDistance;
                const moveY = Math.sin(angle) * escapeDistance;
                
                // Calculate new position
                let newX = nonBtn.offsetLeft + moveX;
                let newY = nonBtn.offsetTop + moveY;
                
                // Keep button within container
                newX = Math.max(10, Math.min(newX, containerRect.width - buttonRect.width - 10));
                newY = Math.max(10, Math.min(newY, containerRect.height - buttonRect.height - 10));
                
                // Apply movement with bounce effect
                nonBtn.style.transition = 'all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55)';
                nonBtn.style.left = `${newX}px`;
                nonBtn.style.top = `${newY}px`;
                
                // Update counter
                clickCount++;
                counter.textContent = clickCount;
                
                // Make button smaller and change devil emoji
                const scale = Math.max(0.4, 1 - clickCount * 0.1);
                nonBtn.style.transform = `scale(${scale})`;
                
                // Change devil emoji based on click count
                const devilEmojis = ['😈', '👿', '😏', '😅', '🏃‍♂️', '💨', '⚡', '🎯'];
                const devilEmoji = nonBtn.querySelector('.devil-emoji');
                if (devilEmoji && clickCount <= devilEmojis.length) {
                    devilEmoji.textContent = devilEmojis[clickCount - 1];
                }
                
                // Make button more transparent
                nonBtn.style.opacity = Math.max(0.3, 1 - clickCount * 0.1);
                
                // Create escape effect particles
                for (let i = 0; i < 8; i++) {
                    createEscapeParticle(nonBtn);
                }
                
                // After 5 clicks, make button very hard to click
                if (clickCount >= 5) {
                    nonBtn.style.pointerEvents = "auto";
                    nonBtn.style.cursor = "not-allowed";
                    const shyText = nonBtn.querySelector('.shy-text');
                    if (shyText) {
                        shyText.textContent = "(ok maybe yes)";
                    }
                }
                
                // After 7 clicks, button disappears
                if (clickCount >= 7) {
                    nonBtn.style.display = 'none';
                    message.textContent = "D'accord, d'accord! Clique sur OUI maintenant! 😘";
                    message.style.display = 'block';
                }
            }
            
            // Create escape particles
            function createEscapeParticle(button) {
                const particle = document.createElement('div');
                particle.innerHTML = '💨';
                particle.style.position = 'absolute';
                particle.style.left = button.getBoundingClientRect().left + 'px';
                particle.style.top = button.getBoundingClientRect().top + 'px';
                particle.style.fontSize = '20px';
                particle.style.zIndex = '5';
                particle.style.opacity = '0.8';
                
                // Random direction
                const angle = Math.random() * Math.PI * 2;
                const distance = 50 + Math.random() * 100;
                const duration = 0.5 + Math.random() * 0.5;
                
                particle.style.transition = `all ${duration}s ease-out`;
                particle.style.transform = `translate(${Math.cos(angle) * distance}px, ${Math.sin(angle) * distance}px) rotate(${angle}rad)`;
                particle.style.opacity = '0';
                
                document.body.appendChild(particle);
                setTimeout(() => particle.remove(), duration * 1000);
            }
            
            // Function to handle "Oui" button click
            function handleOuiClick() {
                // Hide buttons and message
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Create explosion of hearts
                for (let i = 0; i < 30; i++) {
                    setTimeout(() => {
                        const heart = document.createElement('div');
                        heart.className = 'heart';
                        heart.innerHTML = '💖';
                        heart.style.left = '50%';
                        heart.style.top = '50%';
                        heart.style.fontSize = '30px';
                        heart.style.color = '#ff6b9d';
                        heart.style.animation = 'float 2s linear forwards';
                        document.body.appendChild(heart);
                        setTimeout(() => heart.remove(), 2000);
                    }, i * 50);
                }
                
                // Show celebration
                setTimeout(() => {
                    celebration.style.display = 'block';
                }, 500);
                
                // Change background to celebration
                document.body.style.background = 'linear-gradient(135deg, #ff9ec0 0%, #a29bfe 50%, #74b9ff 100%)';
            }
            
            // Add event listeners
            
            // Make button move away when mouse gets close
            document.querySelector('.buttons-container').addEventListener('mousemove', moveNonButtonAwayFromCursor);
            
            // Make button escape when clicked
            nonBtn.addEventListener('click', moveNonButtonOnClick);
            
            // Also make button twitch randomly
            setInterval(() => {
                if (Math.random() > 0.7 && clickCount < 3) {
                    nonBtn.style.transform = 'translateX(5px)';
                    setTimeout(() => {
                        nonBtn.style.transform = 'translateX(-5px)';
                        setTimeout(() => {
                            nonBtn.style.transform = 'translateX(0)';
                        }, 100);
                    }, 100);
                }
            }, 2000);
            
            ouiBtn.addEventListener('click', handleOuiClick);
            
            // Initial setup
            message.textContent = "Sofia, fais ton choix! 💖";
            message.style.display = 'block';
            createHearts();
        });
    </script>
</body>
</html>
