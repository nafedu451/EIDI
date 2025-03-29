<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎁 Salami on Bikash - Send Me Love! 💖</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        body {
            font-family: 'Comic Sans MS', 'Marker Felt', cursive, sans-serif;
            text-align: center;
            background: linear-gradient(45deg, #ff9a9e, #fad0c4, #fbc2eb, #a6c1ee, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: rainbowBG 10s infinite;
            margin: 0;
            padding: 0;
            overflow: hidden;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        @keyframes rainbowBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            max-width: 90%;
            position: relative;
            overflow: hidden;
        }

        h1 {
            color: #ff6b6b;
            font-size: 3rem;
            margin-bottom: 10px;
            text-shadow: 3px 3px 0 #fff, 5px 5px 0 rgba(0, 0, 0, 0.1);
            animation: bounce 1s infinite alternate;
        }

        .salam {
            font-size: 5rem;
            margin: 20px 0;
            animation: swing 2s infinite ease-in-out;
        }

        .buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 30px;
        }

        button {
            padding: 15px 40px;
            font-size: 1.5rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }

        #yesBtn {
            background: linear-gradient(45deg, #4CAF50, #8BC34A);
            color: white;
            z-index: 1;
        }

        #yesBtn:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        #yesBtn:active {
            transform: scale(0.95);
        }

        #noBtn {
            background: linear-gradient(45deg, #FF5252, #FF4081);
            color: white;
            z-index: 1;
            transition: all 0.5s;
        }

        #noBtn:hover {
            transform: scale(1.1);
        }

        #noBtn:active {
            transform: scale(0.95);
        }

        .bikash-info {
            margin-top: 30px;
            background: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            display: none;
            animation: fadeIn 1s;
        }

        .bikash-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #FF5722;
            margin: 15px 0;
            background: linear-gradient(45deg, #FF5722, #FF9800);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 2px 2px 0 rgba(255, 255, 255, 0.5);
        }

        .final-salam {
            font-size: 4rem;
            margin-top: 20px;
            display: none;
            animation: spin 1s, rainbowText 3s infinite;
        }

        .salami-dance {
            font-size: 3rem;
            position: absolute;
            bottom: -50px;
            animation: dance 4s infinite;
        }

        /* Animations */
        @keyframes bounce {
            0% { transform: translateY(0); }
            100% { transform: translateY(-10px); }
        }

        @keyframes swing {
            0% { transform: rotate(-5deg); }
            50% { transform: rotate(5deg); }
            100% { transform: rotate(-5deg); }
        }

        @keyframes spin {
            0% { transform: rotate(0); }
            100% { transform: rotate(360deg); }
        }

        @keyframes dance {
            0% { transform: translateX(0) rotate(0); }
            25% { transform: translateX(50px) rotate(20deg); }
            50% { transform: translateX(0) rotate(0); }
            75% { transform: translateX(-50px) rotate(-20deg); }
            100% { transform: translateX(0) rotate(0); }
        }

        @keyframes rainbowText {
            0% { color: #FF5252; }
            20% { color: #FF9800; }
            40% { color: #FFEB3B; }
            60% { color: #4CAF50; }
            80% { color: #2196F3; }
            100% { color: #9C27B0; }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Trapped Screen */
        .trapped {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            display: none;
        }

        .trapped-message {
            background: linear-gradient(45deg, #FF416C, #FF4B2B);
            color: white;
            padding: 30px;
            border-radius: 20px;
            max-width: 80%;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Confetti */
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #f00;
            opacity: 0.7;
            animation: confettiFall 5s linear infinite;
        }

        @keyframes confettiFall {
            0% { transform: translateY(-100vh) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🎁 Want to Send Me Salami? 🎁</h1>
        <div class="salam">🕌 As-salamu alaykum! 🕌</div>
        <p style="font-size: 1.5rem; color: #555;">A little salami = A lot of happiness! 😍</p>
        
        <div class="buttons">
            <button id="yesBtn">YES! 😍 (I Love You)</button>
            <button id="noBtn">NO 😢 (I'm Heartless)</button>
        </div>
        
        <div class="bikash-info" id="bikashInfo">
            <h2 style="color: #FF5722;">❤️ Thank You! ❤️</h2>
            <p style="font-size: 1.3rem;">Send your salami to my Bikash number:</p>
            <div class="bikash-number">01533672249</div>
            <p style="font-size: 1.2rem;">Opening Bikash app in <span id="countdown">3</span>...</p>
        </div>
        
        <div class="final-salam" id="finalSalam">🕌 Walaykum salam! ❤️</div>
        <div class="salami-dance" id="salamiDance">🥓💃</div>
    </div>
    
    <!-- Trapped Screen -->
    <div class="trapped" id="trapped">
        <div class="trapped-message">
            <h2>🚨 Oops! Trying to Escape? 🚨</h2>
            <p style="font-size: 1.3rem;">You can't leave without sending salami! 😈</p>
            <p style="font-size: 1.2rem;">Click YES or suffer eternal guilt! 😭</p>
            <button id="trappedYesBtn" style="margin-top: 20px; background: white; color: #FF416C; font-weight: bold; font-size: 1.2rem;">OKAY, I'LL CLICK YES! 😅</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const bikashInfo = document.getElementById('bikashInfo');
        const finalSalam = document.getElementById('finalSalam');
        const trapped = document.getElementById('trapped');
        const trappedYesBtn = document.getElementById('trappedYesBtn');
        const salamiDance = document.getElementById('salamiDance');
        const countdownEl = document.getElementById('countdown');

        let noCount = 0;
        const maxNoCount = 5;
        const noMessages = [
            "Are you sure? 😢",
            "Really sure? 😭",
            "Think again! 😟",
            "Last chance! 😥",
            "You're breaking my heart! 💔"
        ];

        // Make the salami dance randomly
        setInterval(() => {
            salamiDance.style.left = Math.random() * 80 + '%';
        }, 4000);

        noBtn.addEventListener('click', function() {
            noCount++;
            
            if (noCount < maxNoCount) {
                // Change button text
                noBtn.textContent = noMessages[noCount - 1];
                
                // Make button smaller & run away
                noBtn.style.transform = `translate(${Math.random() * 200 - 100}px, ${Math.random() * 200 - 100}px) scale(${1 - noCount * 0.1})`;
                
                // Shake the screen
                document.body.style.transform = `translate(${Math.random() * 20 - 10}px, ${Math.random() * 20 - 10}px)`;
                setTimeout(() => {
                    document.body.style.transform = 'translate(0, 0)';
                }, 300);
                
                // Play crying sound (uncomment if you add a sound)
                // new Audio('cry.mp3').play();
            } else {
                // Remove NO button after max tries
                noBtn.style.display = 'none';
                
                // Show funny message
                setTimeout(() => {
                    alert("😂 The NO button ran away! Now you HAVE to click YES! 🎁");
                }, 500);
            }
        });

        yesBtn.addEventListener('click', function() {
            // Shoot confetti!
            confetti({
                particleCount: 150,
                spread: 70,
                origin: { y: 0.6 }
            });

            // Show Bikash info
            bikashInfo.style.display = 'block';
            document.querySelector('.buttons').style.display = 'none';
            document.querySelector('.salam').style.display = 'none';
            salamiDance.style.display = 'none';

            // Countdown to "redirect"
            let countdown = 3;
            const timer = setInterval(() => {
                countdown--;
                countdownEl.textContent = countdown;
                if (countdown <= 0) {
                    clearInterval(timer);
                    bikashInfo.style.display = 'none';
                    finalSalam.style.display = 'block';
                    
                    // More confetti!
                    confetti({
                        particleCount: 200,
                        spread: 100,
                        origin: { y: 0.6 }
                    });

                    // Simulate redirect to Bikash (in real site, use deep link)
                    setTimeout(() => {
                        alert("📱 Opening Bikash app... Send to 01533672249! 💖");
                    }, 1000);
                }
            }, 1000);
        });

        // Trap the user - they can't leave without clicking YES
        window.addEventListener('mouseout', function(e) {
            if (e.clientY < 0 && noCount > 0 && noCount < maxNoCount) {
                trapped.style.display = 'flex';
                document.body.style.overflow = 'hidden';
            }
        });

        trappedYesBtn.addEventListener('click', function() {
            trapped.style.display = 'none';
            document.body.style.overflow = 'auto';
            yesBtn.click(); // Simulate clicking the YES button
        });

        // Prevent right click and other tricks
        document.addEventListener('contextmenu', function(e) {
            e.preventDefault();
            alert("🚫 No cheating! Just click YES! 😜");
        });

        // Easter egg for keyboard users
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                alert("🛑 No escaping the salami! Click YES to proceed! 🎁");
            }
        });
    </script>
</body>
</html>
