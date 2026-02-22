# PARIDHI-BIRTHDAY-
index.html
style.css
script.js
photo.jpg   (your photo together)
music.mp3   (romantic song)
<!DOCTYPE html>
<html>
<head>
    <title>Happy Birthday Paridhi ❤️</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">
    <h1>Happy Birthday My Princess Paridhi ❤️</h1>
    <h3>Forever Yours, Dev 💕</h3>

    <img src="photo.jpg" class="photo">

    <button onclick="showSurprise()">Click for a Special Surprise 🎁</button>

    <div id="surprise" class="hidden">
        <h2>Paridhi, You Are My Everything 💖</h2>
        <p>
            From the day you came into my life, everything became more beautiful.  
            Your smile is my favorite view, your laugh is my favorite sound.  
            I promise to always stand by your side.  
            Happy Birthday, my love ❤️ – Yours always, Dev.
        </p>
    </div>
</div>

<audio id="bgMusic" autoplay loop>
    <source src="music.mp3" type="audio/mp3">
</audio>

<canvas id="confetti"></canvas>

<script src="script.js"></script>
</body>
</html>
body {
    margin: 0;
    padding: 0;
    background: linear-gradient(to right, #ff6a88, #ff99ac);
    font-family: 'Arial', sans-serif;
    text-align: center;
    color: white;
    overflow-x: hidden;
}

.container {
    padding: 40px;
}

h1 {
    font-size: 40px;
    animation: glow 2s infinite alternate;
}

h3 {
    font-weight: normal;
}

@keyframes glow {
    from { text-shadow: 0 0 10px white; }
    to { text-shadow: 0 0 25px yellow; }
}

.photo {
    width: 260px;
    border-radius: 20px;
    margin: 20px 0;
    box-shadow: 0 0 25px white;
    transition: transform 0.5s;
}

.photo:hover {
    transform: scale(1.05);
}

button {
    padding: 15px 25px;
    font-size: 18px;
    background-color: white;
    color: #ff4b7d;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    background-color: yellow;
}

.hidden {
    display: none;
}

#surprise {
    margin-top: 25px;
    animation: fadeIn 2s;
    font-size: 18px;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

canvas {
    position: fixed;
    top: 0;
    left: 0;
    pointer-events: none;
}
function showSurprise() {
    document.getElementById("surprise").classList.remove("hidden");
    startConfetti();
}

// Simple Confetti
const canvas = document.getElementById("confetti");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let confetti = [];

function startConfetti() {
    for (let i = 0; i < 150; i++) {
        confetti.push({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height,
            r: Math.random() * 6 + 2,
            d: Math.random() * 50
        });
    }
    drawConfetti();
}

function drawConfetti() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = "white";

    confetti.forEach((c) => {
        ctx.beginPath();
        ctx.arc(c.x, c.y, c.r, 0, Math.PI * 2, false);
        ctx.fill();
    });
}
