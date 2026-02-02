<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
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
            position: relative; /* RELATIVE AU DÉBUT */
            z-index: 20;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: none !important;
            animation: none !important;
            order: 2; /* EN DESSOUS DE OUI */
            margin-top: 10px;
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
        
        /* Make sure page is scrollable */
        html {
            overflow-y: scroll;
        }
        
        body {
            min-height: 120vh;
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
            <!-- Title that will change -->
            <h1 class="title" id="mainTitle">✨</h1>
            
            <!-- Question Section (will be replaced) -->
            <div class="question-box" id="questionBox">
                <p class="question" id="questionText">
                    <span class="sofia-name">Sofia</span><br>
                    veux-tu sortir vendredi ? 
                    <span style="font-size: 2rem; display: block; margin-top: 15px;">😊</span>
                </p>
            </div>
            
            <!-- Celebration Section (hidden initially) -->
            <div class="celebration-container" id="celebrationContainer">
                <div class="yay-text">🎉 YAY! À vendredi! 🎉</div>
                
                <!-- Conteneur pour le GIF qui se relance -->
                <div class="celebration-gif-container">
                    <img class="celebration-gif" id="celebrationGif" src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif" alt="Celebration">
                </div>
                
                <!-- Message final qui apparaîtra -->
                <div class="final-message" id="finalMessage">✨ On se voit vendredi! ✨</div>
            </div>
            
            <div class="buttons-wrapper">
                <!-- OUI est AU-DESSUS -->
                <button class="oui-btn" id="ouiBtn">
                    <i class="fas fa-heart"></i> OUI !
                </button>
                
                <!-- NON est EN DESSOUS -->
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

    <!-- Add some extra space at bottom for scrolling -->
    <div style="height: 200px; width: 100%;"></div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const ouiBtn = document.getElementById('ouiBtn');
            const nonBtn = document.getElementById('nonBtn');
            const message = document.getElementById('message');
            const questionBox = document.getElementById('questionBox');
            const questionText = document.getElementById('questionText');
            const celebrationContainer = document.getElementById('celebrationContainer');
            const mainTitle = document.getElementById('mainTitle');
            const finalMessage = document.getElementById('finalMessage');
            const celebrationGif = document.getElementById('celebrationGif');
            
            let lastMoveTime = 0;
            let isCelebrating = false;
            let isNonFixed = false;
            let gifRestartInterval = null;
            
            // Fonction pour redémarrer le GIF automatiquement
            function restartGif() {
                // Technique pour forcer le redémarrage du GIF
                const gifSrc = celebrationGif.src;
                celebrationGif.src = "";
                setTimeout(() => {
                    celebrationGif.src = gifSrc;
                }, 50);
            }
            
            // Position initiale - S'assurer que Non est BIEN en dessous de Oui
            function positionNonButtonInitially() {
                // Réinitialiser la position du bouton Non
                nonBtn.style.position = 'relative';
                nonBtn.style.left = '0';
                nonBtn.style.top = '0';
                nonBtn.style.transform = 'translate(0, 0)';
                nonBtn.style.zIndex = '20';
                
                // Forcer le reflow pour s'assurer que les positions sont correctes
                void nonBtn.offsetWidth;
                
                isNonFixed = false;
            }
            
            // Position initiale
            setTimeout(positionNonButtonInitially, 100);
            
            // Faire bouger le bouton Non PARTOUT quand la souris s'approche
            document.addEventListener('mousemove', function(event) {
                if (isCelebrating) return;
                
                const now = Date.now();
                if (now - lastMoveTime < 70) return;
                
                const btnRect = nonBtn.getBoundingClientRect();
                const btnCenterX = btnRect.left + btnRect.width / 2;
                const btnCenterY = btnRect.top + btnRect.height / 2;
                
                const distance = Math.sqrt(
                    Math.pow(event.clientX - btnCenterX, 2) + 
                    Math.pow(event.clientY - btnCenterY, 2)
                );
                
                // Si la souris est à moins de 100px, ÉCHAPPE VITE!
                if (distance < 100) {
                    lastMoveTime = now;
                    
                    // Passer en position FIXED pour bouger partout
                    if (!isNonFixed) {
                        nonBtn.style.position = 'fixed';
                        nonBtn.style.zIndex = '100';
                        isNonFixed = true;
                    }
                    
                    // Calculer la direction d'échappement
                    const angle = Math.atan2(btnCenterY - event.clientY, btnCenterX - event.clientX);
                    
                    // Distance d'échappement aléatoire
                    const escapeDistance = 120 + Math.random() * 180;
                    
                    // Nouvelle position - N'IMPORTE OÙ sur la page!
                    let newX = btnCenterX + Math.cos(angle) * escapeDistance;
                    let newY = btnCenterY + Math.sin(angle) * escapeDistance;
                    
                    // Garder dans les limites de la fenêtre
                    const padding = 40;
                    newX = Math.max(padding, Math.min(newX, window.innerWidth - nonBtn.offsetWidth - padding));
                    newY = Math.max(padding, Math.min(newY, window.innerHeight - nonBtn.offsetHeight - padding));
                    
                    // MOUVEMENT INSTANTANÉ
                    nonBtn.style.left = `${newX}px`;
                    nonBtn.style.top = `${newY}px`;
                    nonBtn.style.transform = 'translate(0, 0)';
                    
                    // Afficher un message
                    if (Math.random() > 0.6) {
                        const messages = [
                            "Trop rapide! ⚡",
                            "Raté! 😆",
                            "Pas si vite! 🏃‍♂️",
                            "Haha! 😈",
                            "Essaie encore! 💨",
                            "Presque! 🙈",
                            "Impossible à attraper! 🚀",
                            "Il court partout! 🌪️"
                        ];
                        message.textContent = messages[Math.floor(Math.random() * messages.length)];
                        message.style.display = 'block';
                        
                        setTimeout(() => {
                            if (!isCelebrating) {
                                message.style.display = 'none';
                            }
                        }, 1000);
                    }
                    
                    // Effet visuel
                    nonBtn.style.boxShadow = '0 0 0 4px rgba(255, 255, 255, 0.9), 0 10px 25px rgba(255, 92, 141, 0.6)';
                    setTimeout(() => {
                        nonBtn.style.boxShadow = '0 8px 20px rgba(255, 92, 141, 0.4)';
                    }, 100);
                    
                    // Téléportation parfois
                    if (Math.random() > 0.8) {
                        setTimeout(() => {
                            // Position aléatoire
                            const randomX = Math.random() * (window.innerWidth - nonBtn.offsetWidth - 80) + 40;
                            const randomY = Math.random() * (window.innerHeight - nonBtn.offsetHeight - 80) + 40;
                            
                            nonBtn.style.left = `${randomX}px`;
                            nonBtn.style.top = `${randomY}px`;
                            
                            // Effet de téléportation
                            const teleport = document.createElement('div');
                            teleport.innerHTML = '🌀';
                            teleport.style.position = 'fixed';
                            teleport.style.left = `${randomX}px`;
                            teleport.style.top = `${randomY}px`;
                            teleport.style.fontSize = '40px';
                            teleport.style.zIndex = '99';
                            teleport.style.opacity = '0';
                            teleport.style.transform = 'scale(0)';
                            document.body.appendChild(teleport);
                            
                            teleport.animate([
                                { transform: 'scale(0)', opacity: 0 },
                                { transform: 'scale(2)', opacity: 0.8 },
                                { transform: 'scale(0)', opacity: 0 }
                            ], {
                                duration: 500,
                                easing: 'ease-out'
                            });
                            
                            setTimeout(() => teleport.remove(), 500);
                        }, 50);
                    }
                    
                    // Effet de scale
                    if (Math.random() > 0.4) {
                        const scale = 0.7 + Math.random() * 0.4;
                        nonBtn.style.transform = `scale(${scale})`;
                    }
                }
            });
            
            // Échappe aussi si la souris entre sur le bouton
            nonBtn.addEventListener('mouseenter', function(event) {
                if (!isCelebrating) {
                    const fakeEvent = new MouseEvent('mousemove', {
                        clientX: event.clientX,
                        clientY: event.clientY
                    });
                    document.dispatchEvent(fakeEvent);
                }
            });
            
            // Essayer de cliquer sur le bouton
            nonBtn.addEventListener('mousedown', function(event) {
                event.preventDefault();
                
                const fakeEvent = new MouseEvent('mousemove', {
                    clientX: event.clientX + 200,
                    clientY: event.clientY + 200
                });
                document.dispatchEvent(fakeEvent);
                
                message.textContent = "Haha! Presque réussi! Mais NON! 😅";
                message.style.display = 'block';
                
                // Effet de saut
                nonBtn.style.transform += ' translateY(-25px)';
                setTimeout(() => {
                    nonBtn.style.transform = nonBtn.style.transform.replace('translateY(-25px)', '');
                }, 200);
            });
            
            // Quand OUI est cliqué
            ouiBtn.addEventListener('click', function() {
                isCelebrating = true;
                
                // Retirer les écouteurs d'événements
                document.removeEventListener('mousemove', arguments.callee);
                
                // Cacher les boutons et message
                ouiBtn.style.display = 'none';
                nonBtn.style.display = 'none';
                message.style.display = 'none';
                
                // Changer le titre "✨" → "YAY! ✨"
                mainTitle.style.opacity = '0';
                mainTitle.style.transform = 'translateY(-20px)';
                
                setTimeout(() => {
                    mainTitle.textContent = 'YAY! ✨';
                    mainTitle.style.opacity = '1';
                    mainTitle.style.transform = 'translateY(0)';
                    
                    // Animation de disparition de la question
                    questionBox.style.opacity = '0';
                    questionBox.style.transform = 'translateY(-20px)';
                    
                    setTimeout(() => {
                        // Cacher la question
                        questionBox.style.display = 'none';
                        
                        // Afficher la célébration
                        celebrationContainer.style.display = 'block';
                        
                        // Démarrer le redémarrage automatique du GIF
                        // Redémarrer toutes les 3 secondes
                        gifRestartInterval = setInterval(restartGif, 3000);
                        
                        // Faire apparaître le message final après 1 seconde
                        setTimeout(() => {
                            finalMessage.style.opacity = '1';
                            finalMessage.style.transform = 'translateY(0)';
                        }, 1000);
                        
                        // Créer des confettis
                        for (let i = 0; i < 120; i++) {
                            setTimeout(() => {
                                createConfetti();
                            }, i * 10);
                        }
                        
                        // Changer le background
                        document.body.style.background = 'linear-gradient(135deg, #ff9ec0 0%, #a29bfe 33%, #74b9ff 66%, #ffd166 100%)';
                        document.body.style.animation = 'rainbowBG 10s infinite linear';
                        
                        // Ajouter l'animation arc-en-ciel
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
            
            // Créer des confettis
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
                
                const duration = Math.random() * 1500 + 800;
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
            
            // Gérer le redimensionnement de la fenêtre
            window.addEventListener('resize', function() {
                if (!isCelebrating && !isNonFixed) {
                    // Re-positionner Non si ce n'est pas en mode fixed
                    positionNonButtonInitially();
                }
            });
            
            // Nettoyer l'intervalle si la page se ferme
            window.addEventListener('beforeunload', function() {
                if (gifRestartInterval) {
                    clearInterval(gifRestartInterval);
                }
            });
            
            // Message initial
            message.textContent = "Essaie de cliquer sur 'Non'... si tu peux! 😈";
            message.style.display = 'block';
        });
    </script>
</body>
</html>
