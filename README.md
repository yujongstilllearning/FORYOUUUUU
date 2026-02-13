<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ruang Kenangan Cinta</title>
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(to bottom, #f8e8e8, #ffe4e1);
            color: #8b4513;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        .section {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            text-align: center;
        }
        .animate__fadeIn {
            animation: fadeIn 2s;
        }
        .hidden {
            opacity: 0;
            transition: opacity 1s;
        }
        .show {
            opacity: 1;
        }
        .heart {
            font-size: 50px;
            cursor: pointer;
            color: #ff69b4;
        }
        .heart:hover {
            transform: scale(1.2);
        }
        .timeline {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        .moment {
            background: rgba(255, 255, 255, 0.8);
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            cursor: pointer;
        }
        .moment:hover {
            background: #ffe4e1;
        }
        .surprise {
            display: none;
        }
    </style>
</head>
<body>
    <!-- Halaman Pembuka -->
    <div class="section animate__fadeIn">
        <h1>Ada Sesuatu yang Spesial Menunggumu...</h1>
        <p>Klik untuk masuk ke dunia kecil kita. ❤️</p>
        <button id="enterBtn" class="heart">Masuk</button>
    </div>

    <!-- Section Cerita -->
    <div class="section hidden" id="story">
        <h2>Perjalanan Cinta Kita</h2>
        <div class="timeline">
            <div class="moment" onclick="reveal(this)">Awal Kenal: Ingat hari pertama kita bertemu? Kamu pesan kopi pahit, aku latte manis – seperti kita sekarang.</div>
            <div class="moment" onclick="reveal(this)">Momen Pertama: Jalan-jalan hujan, kamu pinjamkan jaketmu. Aku jatuh cinta sejak itu.</div>
            <div class="moment" onclick="reveal(this)">Sekarang: Setiap hari bersamamu adalah petualangan baru. Terima kasih telah membuatku bahagia.</div>
        </div>
    </div>

    <!-- Section Momen -->
    <div class="section hidden" id="moments">
        <h2>Momen Sederhana Kita</h2>
        <div class="moment" onmouseover="showDesc(this)" onmouseout="hideDesc(this)">
            <img src="placeholder.jpg" alt="Momen" style="width:200px;">
            <p class="desc hidden">Nonton film di rumah, kamu selalu pilih komedi. Aku suka tawamu yang keras.</p>
        </div>
        <!-- Tambah lebih banyak -->
    </div>

    <!-- Section Catatan -->
    <div class="section hidden" id="notes">
        <h2>Hal-Hal yang Aku Sukai darimu</h2>
        <p>Aku suka cara kamu tertawa saat leluconku gagal. Kamu selalu ingat detail kecil tentangku. Kamu membuat hidupku lebih berwarna.</p>
    </div>

    <!-- Surprise Section -->
    <div class="section hidden" id="surprise">
        <h2>Surprise! ❤️</h2>
        <p>Aku jatuh cinta padamu setiap hari. Semoga kita terus seperti ini, penuh tawa dan cinta. Terima kasih telah hadir dalam hidupku.</p>
    </div>

    <script>
        document.getElementById('enterBtn').addEventListener('click', () => {
            document.getElementById('story').classList.add('show');
            document.getElementById('story').classList.remove('hidden');
        });

        function reveal(el) {
            el.style.background = '#ff69b4';
        }

        function showDesc(el) {
            el.querySelector('.desc').classList.add('show');
            el.querySelector('.desc').classList.remove('hidden');
        }

        function hideDesc(el) {
            el.querySelector('.desc').classList.add('hidden');
            el.querySelector('.desc').classList.remove('show');
        }

        // Surprise trigger: Scroll to bottom
        window.addEventListener('scroll', () => {
            if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
                document.getElementById('surprise').style.display = 'flex';
                document.getElementById('surprise').classList.add('animate__fadeIn');
            }
        });
    </script>
</body>
</html>
