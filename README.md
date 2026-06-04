<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Sayang! 🤍</title>
    <!-- Google Fonts untuk font aesthetic -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <!-- FontAwesome untuk ikon Spotify -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-color: #fcf6f5;
            --text-color: #4a4a4a;
            --accent-color: #d4a373;
            --card-bg: #ffffff;
        }

        body {
            margin: 0;
            padding: 0;
            background-color: var(--bg-color);
            font-family: 'Poppins', sans-serif;
            color: var(--text-color);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Background Hiasan */
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        /* Container Utama */
        .container {
            max-width: 450px;
            width: 90%;
            background: var(--card-bg);
            padding: 30px;
            margin: 40px 0;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            text-align: center;
            box-sizing: border-box;
        }

        /* Foto Frame */
        .photo-frame {
            width: 100%;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            margin-bottom: 25px;
        }

        .photo-frame img {
            width: 100%;
            display: block;
            object-fit: cover;
        }

        /* Ucapan */
        h1 {
            font-family: 'Caveat', cursive;
            font-size: 2.8rem;
            color: var(--accent-color);
            margin-bottom: 15px;
            margin-top: 0;
        }

        .message {
            font-size: 0.95rem;
            line-height: 1.8;
            text-align: justify;
            margin-bottom: 25px;
            white-space: pre-line; /* Menjaga spasi teks asli */
        }

        .from-tag {
            font-family: 'Caveat', cursive;
            font-size: 1.6rem;
            color: var(--accent-color);
            margin-top: 20px;
            text-align: right;
        }

        /* Spotify Player Box */
        .spotify-player {
            background: #191414;
            color: #ffffff;
            padding: 12px 20px;
            border-radius: 50px;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
            margin-top: 15px;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(25, 20, 20, 0.2);
        }

        .spotify-player:hover {
            transform: scale(1.03);
            background: #1ed760;
        }

        .spotify-player i {
            font-size: 1.5rem;
            color: #1ed760;
            transition: color 0.2s;
        }

        .spotify-player:hover i {
            color: #ffffff;
        }

        .spotify-text {
            font-size: 0.85rem;
            font-weight: 600;
            text-align: left;
        }

        .spotify-text span {
            display: block;
            font-size: 0.7rem;
            font-weight: 400;
            opacity: 0.8;
        }
    </style>
</head>
<body>

    <!-- Animasi Hati Ringan -->
    <div class="hearts" id="heartContainer"></div>

    <div class="container">
        <!-- Frame Foto Pasangan -->
        <div class="photo-frame">
            <img src="wmremove-transformed.png" alt="Our Memories">
        </div>

        <!-- Judul -->
        <h1>Happy Birthday Sayang!! 🤍</h1>

        <!-- Isi Surat -->
        <div class="message">
            selamat bertambah usia, diusia kamu yang bertambah 1 setiap tahunnya aku harap kamu selalu diberi kesehatan, kebahagiaan, keberkahan, serta kelancaran dalam hal apapaun, jadi orang baik dan di kelilingi oleh orang orang baik. Makasi sayang udah hadir di hidup aku walaupun kamu kadang ada nyebelin nya, aku berharap kita bisa bertahan lama yaa, aku harap juga aku bisa nemenin di setiap proses proses kamu walaupun dari jauh hehe... 😁😁 
            
            disini aku juga ga lupa selalu berdoa untuk kebaikan kamu setiap harinya, kalo semesta nanti mengijinkan kita bertemu kita ketemu ya sayang, itu harapan terbesar aku bisa meet sama kamu, jadi pribadi lebih baik di umur kamu yang bertambah ini ya, sayang dan cinta sama aku terus ya.. i love u 🤍🫶🏻
        </div>

        <!-- Pengirim -->
        <div class="from-tag">- from your favorite beautiful girl 🎀</div>

        <hr style="border: none; border-top: 1px solid #eee; margin: 25px 0;">

        <!-- Spotify Link Musik (Count on Me - Bruno Mars) -->
        <a href="https://open.spotify.com/track/1HO06vT8U0asm96asv67as?si=b8e734e5a95f4ad6" target="_blank" class="spotify-player">
            <i class="fab fa-spotify"></i>
            <div class="spotify-text">
                Count on Me
                <span>Bruno Mars • Klik untuk Putar</span>
            </div>
        </a>
    </div>

    <!-- Elemen Audio tersembunyi jika ingin auto-play (kebijakan browser modern memerlukan klik pertama dari user) -->
    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <script>
        // Membuat efek kelopak/hati berjatuhan aesthetic secara acak
        const container = document.getElementById('heartContainer');
        const emojis = ['🤍', '✨', '🌸', '🎀'];
        
        for (let i = 0; i < 20; i++) {
            const heart = document.createElement('div');
            heart.innerText = emojis[Math.floor(Math.random() * emojis.length)];
            heart.style.position = 'absolute';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = Math.random() * 100 + 'vh';
            heart.style.opacity = Math.random() * 0.5 + 0.2;
            heart.style.fontSize = Math.random() * 15 + 10 + 'px';
            container.appendChild(heart);
        }
    </script>
</body>
</html>
