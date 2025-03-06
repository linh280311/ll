<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chúc mừng 8/3</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
            font-family: Arial, sans-serif;
            text-align: center;
            color: white;
            overflow: hidden;
        }
        h1 {
            margin-top: 50px;
            font-size: 70px;
            animation: fadeIn 3s ease-in-out;
        }
        p {
            margin-top: 20px;
            font-size: 40px;
            font-weight: bold;
            animation: slideUp 3s ease-in-out;
        }
        button {
            position: fixed;
            bottom: 20px;
            right: 20px;
            padding: 12px 24px;
            font-size: 18px;
            font-weight: bold;
            background-color: #ff6b81;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            z-index: 1000;
            opacity: 0.7;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        .falling-heart {
            position: absolute;
            top: -50px;
            color: red;
            font-size: 30px;
            animation: fall linear infinite;
        }
        @keyframes fall {
            from { transform: translateY(-50px); opacity: 1; }
            to { transform: translateY(100vh); opacity: 0; }
        }
    </style>
</head>
<body>
    <h1>Chúc mừng 8/3!</h1>
    <p>chúc toàn thể các bạn nữ lớp 8B cũng như cô giáo chủ nhiệm một ngày 8-3 vui vẻ mạnh khỏe và hạnh phúc!</p>
    <p>Chúc các bạn có một ngày thật đặc biệt và tràn đầy yêu thương! ❤️</p>

    <button id="playButton">Phát nhạc</button>

    <audio id="myAudio" loop>
        <source src="nhac.mp3" type="audio/mpeg">
    </audio>

    <script>
        const audio = document.getElementById('myAudio');
        const playButton = document.getElementById('playButton');

        playButton.addEventListener('click', () => {
            audio.play();
        });

        function createHeart() {
            const heart = document.createElement('div');
            heart.innerHTML = '❤️';
            heart.classList.add('falling-heart');
            heart.style.left = Math.random() * window.innerWidth + 'px';
            heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 300);
    </script>
</body>
</html>
