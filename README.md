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
            overflow-y: auto;
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
     /* Letter Card - Lebih Besar */
     letter .card {
     width: min(95%, 700px);
     max-height: 80vh;
     padding: 40px;
     display: flex;
     flex-direction: column;
     overflow-y: auto;
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
            color: pink;
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
            color: pink;
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
            z-index: 1;
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
            word-wrap: break-word;
            text-align: left;
            font-size: clamp(13px, 2vw, 15px);
            flex-grow: 1;
            padding: 10px 0;
            min-height: 100px;
            animation: fadeIn 0.3s ease-in;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        /* Cursor Blink */
        .typing-cursor {
            display: inline-block;
            width: 2px;
            height: 1em;
            background-color: #ff75b5;
            margin-left: 2px;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 49% {
                opacity: 1;
            }
            50%, 100% {
                opacity: 0;
            }
        }

        /* Gallery */
        .gallery {
            display: grid;
            grid-template-columns: 1fr;
            gap: 16px;
            max-width: 100%;
            width: 100%;
        }

        .polaroid {
            background: white;
            padding: 10px;
            border-radius: 6px;
            color: black;
            transform: rotate(calc(var(--r) * 1deg));
            cursor: pointer;
            transition: transform 0.3s ease;
            max-width: 300px;
            margin: 0 auto;
            width: 100%;
        }

        .polaroid:hover {
            transform: rotate(calc(var(--r) * 1deg)) scale(1.05);
        }

        .polaroid img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .polaroid p {
            padding: 8px;
            font-weight: 600;
            font-size: 14px;
        }

        /* Modal */
        .modal {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.85);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 100;
        }

        .modal img {
            max-width: 90%;
            max-height: 90vh;
            border-radius: 16px;
        }

        /* Video */
        video {
            width: min(900px, 95%);
            max-height: 50vh;
            border-radius: 20px;
            box-shadow: 0 0 40px rgba(255, 255, 255, 0.2);
        }

        /* Final Page */
        .final {
            max-width: 800px;
            line-height: 2;
            width: 100%;
        }

        .final p {
            font-size: clamp(14px, 2.5vw, 16px);
            margin: 10px 0;
        }

        /* Responsive */
        @media (min-width: 768px) {
            .gallery {
                grid-template-columns: repeat(2, 1fr);
                max-width: 850px;
            }
            
            .polaroid {
                max-width: 100%;
            }

            .polaroid img {
                height: 250px;
            }
        }

        @media (max-width: 480px) {
            .page {
                padding: 10px;
            }

            .card {
                padding: 20px;
                width: 95%;
            }

            #letter .card {
                width: 95%;
                padding: 20px;
                max-height: 85vh;
            }

            h1 {
                font-size: clamp(1.5rem, 4vw, 2.5rem);
            }

            h2 {
                font-size: clamp(1rem, 3vw, 1.8rem);
            }

            .polaroid img {
                height: 150px;
            }

            .polaroid p {
                font-size: 12px;
                padding: 6px;
            }

            video {
                max-height: 40vh;
            }

            #typing {
                max-height: 250px;
                font-size: 13px;
            }

            .final {
                line-height: 1.6;
            }

            .final p {
                font-size: 13px;
            }
        }
    </style>
</head>
<body>
    <div class="hearts" id="hearts"></div>

    <!-- Intro Page -->
    <div class="page active" id="intro">
        <h1 class="glow">Andrea Nadine ❤️</h1>
        <p style="margin:20px 0">Haii Manisskuu,Login Dulu yaa Sandinya tau kann..🤭</p>
        <button style="max-width:300px" onclick="go('login')">MASUK</button>
    </div>

    <!-- Login Page -->
    <div class="page" id="login">
        <div class="card">
            <h2>Login Gift</h2>
            <input id="nama" placeholder="Nama">
            <input id="pin" type="password" placeholder="PIN">
            <button onclick="login()">Login</button>
            <p id="msg"></p>
        </div>
    </div>

    <!-- Envelope Page -->
    <div class="page" id="envelope">
        <div class="envelope" onclick="openLetter()">💌</div>
        <p>Coba pencet amplopnya, ada surat sedikit dibaca yaa..</p>
    </div>

    <!-- Letter Page -->
    <div class="page" id="letter">
        <div class="card">
            <h2>Untuk Cintakuu 🤍</h2>
            <div id="typing"></div>
            <button onclick="go('galleryPage')">Next</button>
        </div>
    </div>

    <!-- Gallery Page -->
    <div class="page" id="galleryPage">
        <h2 style="margin-bottom:20px">📸 Klik</h2>
        <div class="gallery">
            <div class="polaroid" style="--r:-4" onclick="zoom('img1.jpg')"><img src="https://github.com/user-attachments/assets/9fe61275-7a7c-411e-aac9-a3c4e066c22a"><p>My Princess</p></div>
            <div class="polaroid" style="--r:3" onclick="zoom('img2.jpg')"><img src="https://github.com/user-attachments/assets/14f33268-1e8a-4408-b889-6f9d47c55f22"><p>Our Story</p></div>
            <div class="polaroid" style="--r:-2" onclick="zoom('img3.jpg')"><img src="https://github.com/user-attachments/assets/7be50d7e-1231-4794-89df-8cfe95c96faa"><p>My Beautiful</p></div>
            <div class="polaroid" style="--r:5" onclick="zoom('img4.jpg')"><img src="https://github.com/user-attachments/assets/43c7c3f2-7b10-493c-a73f-9f7ffa5ecec4"><p>Sweet Memory</p></div>
        </div>
        <br><button style="max-width:300px" onclick="go('videoPage')">🎬 Video Kenangan</button>
    </div>

    <!-- Video Page -->
    <div class="page" id="videoPage">
        <h2>Video Kenangan Kita</h2><br>
        <video controls src="https://github.com/user-attachments/assets/9bad4a27-9784-4ce2-a62c-0d2b77d33eb5"></video><br><br>
        <button style="max-width:300px" onclick="go('finalPage')">❤️‍🔥 satu lagi nihh..</button>
    </div>

    <!-- Final Page -->
    <div class="page" id="finalPage">
        <div class="final">
            <h1 class="glow">Andrea Nadine Thea Melinda 🥰</h1><br>
            <p>
                Happy birthday day yaa cintakuu..🥳🥳🎉🎊💕💖
                aku tau aku ga sempurna, tapi aku selalu berusaha jadi seseorang yang bisa kamu andalkan. kalau ayang capek, butuh tempat cerita, atau cuma pengen didenger, aku selalu ada di sini. maa[...]

Terima kasih sudah hadir dalam hidupku.
Terima kasih sudah menjadi tempat pulang untuk cerita, tawa, dan keluh kesahku.

Semoga apa pun yang terjadi nanti, kita tetap bisa saling menjaga, saling memahami, dan terus menciptakan kenangan indah bersama.
                I love you so muchh, and i'm thankful every day that you're mine cantikuu
            </p>
            <br>
            <h2>I Love You sayangg💞</h2>
            <br>
            <button style="max-width:320px" onclick="celebrateForever()">🌹 love youu..</button>
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
            
            if ((n.includes('andrea') || n.includes('nadine')) && p === '161223') {
                go('envelope');
            } else {
                document.getElementById('msg').innerText = 'Nama anda atau PIN salah';
            }
        }

        // Open Letter with Typing Effect
        function openLetter() {
            go('letter');
            
            const txt = `Hai Ayang ❤️

Aku membuat halaman kecil ini khusus untukmu.

Mungkin ini hanya sebuah website sederhana, tetapi setiap bagian di dalamnya dibuat dengan penuh rasa sayang.

Untuk Ayangg, Andrea Nadine Thea Melinda 💖

Selamat ulang tahun yang ke-20, Ayangg.

Hari ini adalah hari yang sangat spesial karena hari ini adalah hari lahir seseorang putri kecil yang begitu berarti dalam hidupku. Seseorang yang selama dua tahun terakhir telah mengisi hari-hariku dengan warna dan tawa yang tidak akan pernah aku lupakan.

Di hari ulang tahunmu ini, aku ingin mengucapkan terima kasih untuk semua hal yang sudah kamu berikan kepadaku. Terima kasih karena telah hadir dalam hidupku. Terima kasih karena telah menjadi seseorang yang selalu membuat hari-hariku lebih bermakna.

Aku bersyukur kepada Tuhan karena telah mempertemukanku denganmu. Dari sekian banyak orang di dunia ini, aku merasa beruntung karena bisa mengenalmu, mencintaimu, dan berjalan bersamamu hingga saat ini.

Ayangg, aku berharap di usia yang baru ini kamu selalu diberikan kesehatan, kebahagiaan, kekuatan, dan keberhasilan dalam setiap langkah yang kamu ambil. Semoga semua impian, harapan, dan cita-citamu menjadi kenyataan.

Aku juga ingin kamu tahu bahwa kehadiranmu sangat berarti bagiku. Senyummu, perhatianmu, cara kamu peduli, dan semua hal kecil yang kamu lakukan sering kali menjadi sesuatu yang membuat hariku lebih indah.

Terima kasih karena sudah hadir dalam hidupku selama dua tahun terakhir. Aku bersyukur karena dari sekian banyak kemungkinan di dunia ini, aku dipertemukan dengan seseorang sebaik dan seistimewa dirimu.

Terima kasih karena sudah bertahan bersamaku selama ini. Terima kasih karena sudah menerima segala kekuranganku. Terima kasih karena tetap memilih untuk berjalan bersamaku hingga hari ini.

Dan yang paling penting, terima kasih karena sudah menjadi Andrea Nadine yang aku kenal dan aku sayangi.

Di hari spesialmu ini, aku tidak meminta banyak hal selain melihatmu bahagia. Karena kebahagiaanmu juga menjadi kebahagiaanku.

Sekali lagi, selamat ulang tahun yang ke-20, Ayangg.

Semoga tahun ini menjadi tahun yang penuh kebahagiaan, keberuntungan, dan cerita indah untukmu.

Aku sayang kamu, hari ini, besok, dan selama Tuhan masih mengizinkan aku untuk mencintaimu. 💕

Dengan penuh cinta,

Anggut 🤍

Selamat ulang tahun yang ke-20, Cantikuu🎊🎉🥳🥰💞💖.`;
            
            let i = 0;
            const el = document.getElementById('typing');
            el.innerHTML = '';
            
            // Hitung total durasi berdasarkan panjang teks
            const totalDuration = txt.length * 35; // 35ms per karakter
            
            let t = setInterval(() => {
                if (i < txt.length) {
                    el.innerHTML = txt.substring(0, i + 1) + '<span class="typing-cursor"></span>';
                    // Auto scroll ke bawah
                    const letterCard = document.getElementById('letter').querySelector('.card');
                    letterCard.scrollTop = letterCard.scrollHeight;
                    i++;
                } else {
                    el.innerHTML = txt + '<span class="typing-cursor"></span>';
                    clearInterval(t);
                }
            }, 35);
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
            particle.style.zIndex = 50;
            
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
