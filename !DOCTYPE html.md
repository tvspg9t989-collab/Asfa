<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>Happy Birthday Asfa ❤️</title>  
  
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">  
  
<style>  
body {  
    margin: 0;  
    font-family: 'Poppins', sans-serif;  
    background: linear-gradient(135deg, #ff758c, #ff7eb3);  
    overflow: hidden;  
    color: white;  
    text-align: center;  
}  
  
.container {  
    position: absolute;  
    top: 50%;  
    left: 50%;  
    transform: translate(-50%, -50%);  
    width: 90%;  
}  
  
/* Name animation */  
.name {  
    font-size: 3rem;  
    font-weight: 600;  
    letter-spacing: 2px;  
    animation: glow 2s infinite alternate;  
}  
  
@keyframes glow {  
    from { text-shadow: 0 0 10px white; }  
    to { text-shadow: 0 0 25px #fff, 0 0 40px #ffdde1; }  
}  
  
h2 {  
    margin-top: 10px;  
    font-weight: 300;  
}  
  
/* Typing effect */  
.typing {  
    margin-top: 20px;  
    font-size: 1.2rem;  
    min-height: 60px;  
}  
  
/* Button */  
.btn {  
    margin-top: 25px;  
    padding: 12px 22px;  
    border: none;  
    border-radius: 30px;  
    background: white;  
    color: #ff4f81;  
    font-size: 1rem;  
    cursor: pointer;  
    transition: 0.3s;  
}  
  
.btn:hover {  
    transform: scale(1.1);  
}  
  
/* Hidden message */  
.hidden {  
    display: none;  
    margin-top: 20px;  
    font-size: 1.2rem;  
}  
  
/* Canvas */  
canvas {  
    position: fixed;  
    top: 0;  
    left: 0;  
    pointer-events: none;  
}  
</style>  
</head>  
  
<body>  
  
<canvas id="confetti"></canvas>  
  
<div class="container">  
    <div class="name">Asfa 💖</div>  
    <h2>Happy Birthday 🎉</h2>  
  
    <div class="typing" id="typing"></div>  
  
    <button class="btn" onclick="reveal()">Tap for something special 🎁</button>  
  
    <div class="hidden" id="hiddenMsg">  
        Maybe I don’t say it often…<br>  
        but you really mean a lot to me 💕  
    </div>  
</div>  
  
<!-- Optional Music (replace link if you want) -->  
<audio autoplay loop>  
    <source src="https://www2.cs.uic.edu/~i101/SoundFiles/StarWars60.wav" type="audio/wav">  
</audio>  
  
<script>  
// Typing effect  
const text = "You make ordinary days feel special ✨ And today… is all about you ❤️";  
let i = 0;  
  
function typeEffect() {  
    if (i < text.length) {  
        document.getElementById("typing").innerHTML += text.charAt(i);  
        i++;  
        setTimeout(typeEffect, 40);  
    }  
}  
typeEffect();  
  
// Reveal message  
function reveal() {  
    document.getElementById("hiddenMsg").style.display = "block";  
}  
  
// Confetti  
const canvas = document.getElementById('confetti');  
const ctx = canvas.getContext('2d');  
  
canvas.width = window.innerWidth;  
canvas.height = window.innerHeight;  
  
let pieces = [];  
  
for (let i = 0; i < 120; i++) {  
    pieces.push({  
        x: Math.random() * canvas.width,  
        y: Math.random() * canvas.height,  
        r: Math.random() * 6 + 2,  
        d: Math.random() * 50  
    });  
}  
  
function draw() {  
    ctx.clearRect(0, 0, canvas.width, canvas.height);  
  
    ctx.fillStyle = "white";  
    ctx.beginPath();  
  
    pieces.forEach(p => {  
        ctx.moveTo(p.x, p.y);  
        ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);  
    });  
  
    ctx.fill();  
    update();  
}  
  
function update() {  
    pieces.forEach(p => {  
        p.y += Math.cos(p.d) + 2;  
        p.x += Math.sin(p.d);  
  
        if (p.y > canvas.height) {  
            p.y = 0;  
            p.x = Math.random() * canvas.width;  
        }  
    });  
}  
  
setInterval(draw, 30);  
  
// Resize fix  
window.addEventListener("resize", () => {  
    canvas.width = window.innerWidth;  
    canvas.height = window.innerHeight;  
});  
</script>  
  
</body>  
</html>  
