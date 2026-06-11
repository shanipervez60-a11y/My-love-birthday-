<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, My love! ❤️</title>
    <style>
        :root {
            --bg-color: #ffeef2;
            --primary-pink: #ff7597;
            --text-dark: #4a2831;
            --card-pink: #ffd3dd;
            --card-purple: #e8d3ff;
            --card-yellow: #fff2cc;
            --card-green: #d3ffd8;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-dark);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            text-align: center;
            overflow-x: hidden;
        }

        .container {
            max-width: 500px;
            width: 100%;
        }

        /* Music Floating Control */
        .music-control {
            position: fixed;
            top: 20px;
            right: 20px;
            background: white;
            padding: 10px;
            border-radius: 50%;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            cursor: pointer;
            z-index: 1000;
            font-size: 1.5rem;
            width: 45px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s ease;
        }
        
        .music-control.playing {
            animation: spin 4s linear infinite;
        }

        @keyframes spin {
            100% { transform: rotate(360deg); }
        }

        header {
            margin: 30px 0;
        }

        header h1 {
            font-size: 2.2rem;
            color: var(--primary-pink);
            margin-bottom: 5px;
        }

        header p {
            font-style: italic;
            opacity: 0.8;
        }

        /* Interactive Grid Layout */
        .card-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 40px;
        }

        /* 3D Flip Card Magic */
        .flip-card {
            background-color: transparent;
            height: 140px;
            perspective: 1000px;
            cursor: pointer;
        }

        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.6s;
            transform-style: preserve-3d;
            border-radius: 15px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }

        .flip-card.flipped .flip-card-inner {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 10px;
            border-radius: 15px;
        }

        .card-front h3 {
            font-size: 1.2rem;
            margin-top: 8px;
        }

        .card-front span {
            font-size: 0.8rem;
            opacity: 0.6;
        }

        .card-back {
            transform: rotateY(180deg);
            font-size: 0.95rem;
            font-weight: 600;
            line-height: 1.4;
        }

        /* Dynamic Card Colors */
        .c1 { background-color: var(--card-pink); }
        .c2 { background-color: var(--card-purple); }
        .c3 { background-color: var(--card-yellow); }
        .c4 { background-color: var(--card-green); }
        .back-style { background-color: #fff; border: 2px solid var(--primary-pink); }

        /* Birthday Letter Section */
        .letter-section {
            background: white;
            padding: 30px 20px;
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            margin-bottom: 40px;
            text-align: left;
        }

        .letter-section h2 {
            color: var(--primary-pink);
            font-size: 1.5rem;
            margin-bottom: 15px;
            text-align: center;
        }

        .letter-section p {
            font-size: 1rem;
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .letter-signature {
            text-align: right;
            font-weight: bold;
            color: var(--primary-pink);
            margin-top: 20px;
        }

        /* Reasons Section */
        .reasons-section {
            margin-bottom: 40px;
        }

        .reasons-section h2 {
            margin-bottom: 20px;
            color: var(--primary-pink);
        }

        .reason-item {
            background: white;
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 12px;
            text-align: left;
            display: flex;
            align-items: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
        }

        .reason-emoji {
            font-size: 1.8rem;
            margin-right: 15px;
        }

        .reason-text h4 {
            color: var(--primary-pink);
            margin-bottom: 2px;
        }

        .reason-text p {
            font-size: 0.9rem;
            opacity: 0.9;
        }

        /* Interactive Candle Cake Section */
        .cake-section {
            background: #fff;
            padding: 30px 20px;
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            margin-bottom: 5px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .cake-section h2 {
            margin-bottom: 10px;
        }

        .cake-container {
            position: relative;
            width: 120px;
            height: 140px;
            margin: 20px 0;
        }

        .cake {
            position: absolute;
            bottom: 0;
            width: 120px;
            height: 60px;
            background: #f1948a;
            border-radius: 10px 10px 0 0;
            box-shadow: inset 0 5px 0 #ec7063;
        }

        .candle {
            position: absolute;
            bottom: 60px;
            left: 53px;
            width: 14px;
            height: 35px;
            background: repeating-linear-gradient(45deg, #fff, #fff 5px, var(--primary-pink) 5px, var(--primary-pink) 10px);
            border-radius: 3px 3px 0 0;
        }

        .flame {
            position: absolute;
            bottom: 95px;
            left: 55px;
            width: 10px;
            height: 18px;
            background: #ffaa00;
            border-radius: 50% 50% 20% 20%;
            box-shadow: 0 0 10px #ffaa00;
            animation: flicker 0.6s infinite alternate;
            transition: opacity 0.3s ease;
        }

        @keyframes flicker {
            0% { transform: scale(1); }
            100% { transform: scale(1.1) skewX(5deg); }
        }

        .action-btn {
            background-color: var(--primary-pink);
            color: white;
            border: none;
            padding: 12px 25px;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(255, 117, 151, 0.4);
            transition: transform 0.2s;
            margin-top: 10px;
        }

        .action-btn:active {
            transform: scale(0.95);
        }

        .hidden-surprise {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.8s ease-out;
            margin-top: 0;
        }

        .hidden-surprise.reveal {
            max-height: 200px;
            margin-top: 20px;
        }

        .surprise-box {
            background: #fff0f3;
            border: 2px dashed var(--primary-pink);
            padding: 15px;
            border-radius: 10px;
        }
    </style>
</head>
<body onclick="startAudioOnInteraction()">

    <div class="music-control" id="musicBtn" onclick="toggleMusic(event)">🤫</div>

    <audio id="bgMusic" loop src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"></audio>

    <div class="container">
        
        <header>
            <h1>Our Little Story</h1>
            <p>Flip the cards to reveal ✨</p>
        </header>

        <div class="card-grid">
            
            <div class="flip-card" onclick="flipCard(this)">
                <div class="flip-card-inner">
                    <div class="card-front c1">
                        <h3>🎂</h3>
                        <span>Tap to reveal ✨</span>
                    </div>
                    <div class="card-back back-style">
                        The day you were born, the whole world got brighter.
                    </div>
                </div>
            </div>

            <div class="flip-card" onclick="flipCard(this)">
                <div class="flip-card-inner">
                    <div class="card-front c2">
                        <h3>🌸</h3>
                        <span>Tap to reveal ✨</span>
                    </div>
                    <div class="card-back back-style">
                        Your smile is easily my favorite thing.
                    </div>
                </div>
            </div>

            <div class="flip-card" onclick="flipCard(this)">
                <div class="flip-card-inner">
                    <div class="card-front c3">
                        <h3>⭐</h3>
                        <span>Tap to reveal ✨</span>
                    </div>
                    <div class="card-back back-style">
                        Every single day spent with you is golden.
                    </div>
                </div>
            </div>

            <div class="flip-card" onclick="flipCard(this)">
                <div class="flip-card-inner">
                    <div class="card-front c4">
                        <h3>🧸</h3>
                        <span>Tap to reveal ✨</span>
                    </div>
                    <div class="card-back back-style">
                        You're the warmest, safest hug in human form.
                    </div>
                </div>
            </div>

        </div>

        <div class="letter-section">
            <h2>To My Birthday Princess 👑</h2>
            <p>My dearest birthday girl,</p>
            <p>Today marks another year of your incredible existence, and I couldn't be more grateful to celebrate it alongside you. You bring an unmatched happiness wherever you go, and your kind soul genuinely makes the world a much sweeter place.</p>
            <p>On your special day, I wish you endless laughter, perfect health, and success in absolutely everything you pursue. May this year bring you gorgeous memories, thrilling new opportunities, and countless reasons to smile.</p>
            <p>Enjoy your day to the absolute absolute fullest—you deserve the entire universe. Happy Birthday! 🎉💖</p>
            <div class="letter-signature">Forever Yours, <br> Shahzaib</div>
        </div>

        <div class="reasons-section">
            <h2>Reasons I Love You 🥰</h2>
            
            <div class="reason-item">
                <div class="reason-emoji">😊</div>
                <div class="reason-text">
                    <h4>Reason #01</h4>
                    <p>Your laugh lights up my entire day and makes everything better.</p>
                </div>
            </div>

            <div class="reason-item">
                <div class="reason-emoji">💪</div>
                <div class="reason-text">
                    <h4>Reason #02</h4>
                    <p>You are so resilient and strong, inspiring me every single day.</p>
                </div>
            </div>

            <div class="reason-item">
                <div class="reason-emoji">🌙</div>
                <div class="reason-text">
                    <h4>Reason #03</h4>
                    <p>You turn regular, ordinary moments into something absolutely magical.</p>
                </div>
            </div>
        </div>

        <div class="cake-section">
            <h2>Blow the Candle 🎂</h2>
            <p>Make a wish before you blow it out!</p>
            
            <div class="cake-container">
                <div class="flame" id="cakeFlame"></div>
                <div class="candle"></div>
                <div class="cake"></div>
            </div>

            <button class="action-btn" id="blowBtn" onclick="blowCandle()">✨ Tap to Blow Candle</button>

            <div class="hidden-surprise" id="surpriseMessage">
                <div class="surprise-box">
                    <h3>Happy Birthday, Cutie! 🎉</h3>
                    <p>May all your secret wishes come true today! I love you endlessly. ❤️</p>
                </div>
            </div>
        </div>

    </div>

    <script>
        const music = document.getElementById('bgMusic');
        const musicBtn = document.getElementById('musicBtn');
        let hasPlayed = false;

        // Modern browsers block autoplay without interaction. 
        // This plays the song automatically the moment she taps anywhere on the screen.
        function startAudioOnInteraction() {
            if (!hasPlayed) {
                music.play().then(() => {
                    musicBtn.innerText = "🎵";
                    musicBtn.classList.add('playing');
                    hasPlayed = true;
                }).catch(err => console.log("Audio autoplay blocked waiting for specific button click."));
            }
        }

        // Allows her to manually play/pause using the floating button
        function toggleMusic(event) {
            event.stopPropagation(); // Prevents conflict with body click function
            if (music.paused) {
                music.play();
                musicBtn.innerText = "🎵";
                musicBtn.classList.add('playing');
                hasPlayed = true;
            } else {
                music.pause();
                musicBtn.innerText = "🤫";
                musicBtn.classList.remove('playing');
            }
        }

        // Function to toggle individual cards
        function flipCard(card) {
            card.classList.toggle('flipped');
        }

        // Function for blowing the cake candle
        function blowCandle() {
            const flame = document.getElementById('cakeFlame');
            const surprise = document.getElementById('surpriseMessage');
            const button = document.getElementById('blowBtn');
            
            // Extinguish flame
            flame.style.opacity = '0';
            
            // Reveal secret message smoothly
            surprise.classList.add('reveal');
            
            // Update button text
            button.innerText = "❤️ Wish Made! ❤️";
            button.style.backgroundColor = "#75ff91";
            button.style.color = "#284a31";
            button.disabled = true;
        }
    </script>
</body>
</html>
