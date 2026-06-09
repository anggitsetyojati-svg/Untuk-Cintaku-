<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Andrea Nadine ❤️ Premium V2</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Poppins, sans-serif;
        }

        body {
            background: linear-gradient(180deg, #08050d, #130818, #220b1f);
            color: #fff;
            overflow: hidden;
        }

        .page {
            position: fixed;
            inset: 0;
            display: none;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            padding: 20px;
            text-align: center;
        }

        .active {
            display: flex;
        }

        .card {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(18px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            padding: 30px;
            border-radius: 28px;
            width: min(92%, 560px);
            box-shadow: 0 0 40px rgba(255, 105, 180, 0.25);
        }

        h1 {
            font-size: clamp(2rem, 5vw, 3.5rem);
        }

        h2 {
            font-size: clamp(1.5rem, 4vw, 2.5rem);
        }

        button, input {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 14px;
            margin-top: 12px;
        }

        button {
            background: linear-gradient(45deg, #ff4f9f, #ff89c7);
            color: white;
            font-weight: 700;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        button:hover {
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(0);
        }

        input {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        input::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }

        /* Hearts Animation */
        .hearts {
            position: fixed;
            inset: 0;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            animation: rise linear forwards;
        }

        @keyframes rise {
            from {
                transform: translateY(105vh) scale(0.4);
            }
            to {
                transform: translateY(-100px) scale(1.5);
                opacity: 0;
            }
        }

        /* Fireworks Animation */
        .firework {
            position: absolute;
            pointer-events: none;
        }

        .firework-particle {
            position: absolute;
            width: 8px;
            height: 8px;
            border-radius: 50%;
            animation: explode linear forwards;
        }

        @keyframes explode {
            from {
                transform: translate(0, 0) scale(1);
                opacity: 1;
            }
            to {
                transform: translate(var(--tx), var(--ty)) scale(0);
                opacity: 0;
            }
        }

        .glow {
            animation: pulse 2.5s infinite;
        }

        @keyframes pulse {
            50% {
                text-shadow: 0 0 25px #ff75b5;
            }
        }

        /* Envelope */
        .envelope {
            font-size: 140px;
            cursor: pointer;
            transition: 0.5s;
        }

        .envelope:hover {
            transform: scale(1.08) rotate(-3deg);
        }

        #typing {
            line-height: 1.9;
            white-space: pre-wrap;
        }

        /* Gallery */
        .gallery {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 16px;
            max-width: 850px;
        }

        .polaroid {
            background: white;
            padding: 10px;
            border-radius: 6px;
            color: black;
            transform: rotate(calc(var(--r) * 1deg));
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .polaroid:hover {
            transform: rotate(calc(var(--r) * 1deg)) scale(1.05);
        }

        .polaroid img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .polaroid p {
            padding: 8px;
            font-weight: 600;
        }

        /* Modal */
        .modal {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.85);
            display: none;
            justify-content: center;
            align-items: center;
        }

        .modal img {
            max-width: 90%;
            max-height: 90vh;
            border-radius: 16px;
        }

        /* Video */
        video {
            width: min(900px, 95%);
            border-radius: 20px;
            box-shadow: 0 0 40px rgba(255, 255, 255, 0.2);
        }

        /* Final Page */
        .final {
            max-width: 800px;
            line-height: 2;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .gallery {
                grid-template-columns: 1fr;
            }
            
            .card {
                width: 95%;
            }
        }
    </style>
</head>
<body>
    <div class="hearts" id="hearts"></div>

    <!-- Intro Page -->
    <div class="page active" id="intro">
        <h1 class="glow">Andrea Nadine ❤️</h1>
        <p style="margin:20px 0">A special gift has been prepared for you</p>
        <button style="max-width:300px" onclick="go('login')">🎁 Buka Hadiah</button>
    </div>

    <!-- Login Page -->
    <div class="page" id="login">
        <div class="card">
            <h2>Login Gift</h2>
            <input id="nama" placeholder="Nama">
            <input id="pin" type="password" placeholder="PIN">
            <button onclick="login()">Masuk</button>
            <p id="msg"></p>
        </div>
    </div>

    <!-- Envelope Page -->
    <div class="page" id="envelope">
        <div class="envelope" onclick="openLetter()">💌</div>
        <p>Klik amplop untuk membuka surat</p>
    </div>

    <!-- Letter Page -->
    <div class="page" id="letter">
        <div class="card">
            <h2>Untuk Ayang ❤️</h2>
            <p id="typing"></p>
            <button onclick="go('galleryPage')">Lanjutkan</button>
        </div>
    </div>

    <!-- Gallery Page -->
    <div class="page" id="galleryPage">
        <h2 style="margin-bottom:20px">📸 Our Memories</h2>
        <div class="gallery">
            <div class="polaroid" style="--r:-4" onclick="zoom('img1.jpg')"><img src="img1.jpg"><p>My Favorite Smile</p></div>
            <div class="polaroid" style="--r:3" onclick="zoom('img2.jpg')"><img src="img2.jpg"><p>Our Story</p></div>
            <div class="polaroid" style="--r:-2" onclick="zoom('img3.jpg')"><img src="img3.jpg"><p>Beautiful Day</p></div>
            <div class="polaroid" style="--r:5" onclick="zoom('img4.jpg')"><img src="img4.jpg"><p>Sweet Memory</p></div>
        </div>
        <br><button style="max-width:300px" onclick="go('videoPage')">🎬 Video Kenangan</button>
    </div>

    <!-- Video Page -->
    <div class="page" id="videoPage">
        <h2>Video Kenangan Kita</h2><br>
        <video controls src="https://github.com/user-attachments/assets/9bad4a27-9784-4ce2-a62c-0d2b77d33eb5"></video><br><br>
        <button style="max-width:300px" onclick="go('finalPage')">❤️ Halaman Terakhir</button>
    </div>

    <!-- Final Page -->
    <div class="page" id="finalPage">
        <div class="final">
            <h1 class="glow">Andrea Nadine Thea Melinda ❤️</h1><br>
            <p>
                Terima kasih sudah hadir dalam hidupku.
                Terima kasih untuk setiap tawa, cerita, perhatian, dan semua kenangan yang telah kita lalui bersama.
                Mungkin aku tidak selalu sempurna, tetapi aku akan selalu berusaha menjadi seseorang yang bisa membuatmu merasa dicintai, dihargai, dan ditemani.
            </p>
            <br>
            <h2>I Love You ❤️</h2>
            <br>
            <button style="max-width:320px" onclick="celebrateForever()">🌹 Forever With You</button>
        </div>
    </div>

    <!-- Modal for Image Zoom -->
    <div class="modal" id="modal" onclick="this.style.display='none'">
        <img id="modalImg">
    </div>

    <script>
        // Navigation Function
        function go(id) {
            document.querySelectorAll('.page').forEach(x => x.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        // Login Function
        function login() {
            const n = document.getElementById('nama').value.toLowerCase();
            const p = document.getElementById('pin').value;
            
            if (n.includes('andrea') && p === '161223') {
                go('envelope');
            } else {
                document.getElementById('msg').innerText = 'Nama atau PIN salah';
            }
        }

        // Open Letter with Typing Effect
        function openLetter() {
            go('letter');
            
            const txt = `Hai Ayang ❤️

Aku membuat halaman kecil ini khusus untukmu.

Mungkin ini hanya sebuah website sederhana, tetapi setiap bagian di dalamnya dibuat dengan penuh rasa sayang.

Terima kasih sudah hadir dalam hidupku.
Terima kasih sudah menjadi tempat pulang untuk cerita, tawa, dan keluh kesahku.

Semoga apa pun yang terjadi nanti, kita tetap bisa saling menjaga, saling memahami, dan terus menciptakan kenangan indah bersama.`;
            
            let i = 0;
            const el = document.getElementById('typing');
            el.innerHTML = '';
            
            let t = setInterval(() => {
                el.innerHTML += txt.charAt(i);
                i++;
                if (i >= txt.length) clearInterval(t);
            }, 25);
        }

        // Zoom Image Function
        function zoom(src) {
            document.getElementById('modalImg').src = src;
            document.getElementById('modal').style.display = 'flex';
        }

        // Create Single Heart
        function createHeart() {
            let h = document.createElement('div');
            h.className = 'heart';
            h.innerHTML = '❤️';
            h.style.left = Math.random() * 100 + '%';
            h.style.fontSize = (20 + Math.random() * 30) + 'px';
            h.style.animationDuration = (5 + Math.random() * 5) + 's';
            
            document.getElementById('hearts').appendChild(h);
            
            setTimeout(() => h.remove(), 10000);
        }

        // Create Hearts Continuously
        setInterval(createHeart, 350);

        // Create Firework Particle
        function createFireworkParticle(x, y, color) {
            const particle = document.createElement('div');
            particle.className = 'firework-particle';
            particle.style.left = x + 'px';
            particle.style.top = y + 'px';
            particle.style.backgroundColor = color;
            
            const angle = Math.random() * Math.PI * 2;
            const distance = 50 + Math.random() * 150;
            const tx = Math.cos(angle) * distance;
            const ty = Math.sin(angle) * distance;
            
            particle.style.setProperty('--tx', tx + 'px');
            particle.style.setProperty('--ty', ty + 'px');
            
            const duration = 0.5 + Math.random() * 1.5;
            particle.style.animationDuration = duration + 's';
            
            document.getElementById('hearts').appendChild(particle);
            
            setTimeout(() => particle.remove(), duration * 1000);
        }

        // Create Fireworks Burst
        function createFireworkBurst(x, y) {
            const colors = ['#ff4f9f', '#ff89c7', '#ffb3d9', '#ff1493', '#ff69b4'];
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                setTimeout(() => {
                    const color = colors[Math.floor(Math.random() * colors.length)];
                    createFireworkParticle(x, y, color);
                }, i * 15);
            }
        }

        // Celebrate Forever - Hearts + Fireworks
        function celebrateForever() {
            // Create multiple fireworks from different positions
            const positions = [
                { x: window.innerWidth * 0.2, y: window.innerHeight * 0.3 },
                { x: window.innerWidth * 0.5, y: window.innerHeight * 0.2 },
                { x: window.innerWidth * 0.8, y: window.innerHeight * 0.3 },
                { x: window.innerWidth * 0.3, y: window.innerHeight * 0.5 },
                { x: window.innerWidth * 0.7, y: window.innerHeight * 0.5 }
            ];

            // Launch fireworks in sequence
            positions.forEach((pos, index) => {
                setTimeout(() => {
                    createFireworkBurst(pos.x, pos.y);
                }, index * 200);
            });

            // Launch heart storm
            for (let i = 0; i < 120; i++) {
                setTimeout(createHeart, i * 30);
            }
        }
    </script>
</body>
</html>
