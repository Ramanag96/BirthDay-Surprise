# BirthDay-Surprise

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Birthday Surprise 🎉</title>

<style>
    body {
        margin: 0;
        overflow: hidden;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        font-family: 'Arial', sans-serif;
        text-align: center;
        color: white;
    }

    h1 {
        margin-top: 120px;
        font-size: 50px;
        animation: pop 1s ease-in-out infinite alternate;
    }

    p {
        font-size: 22px;
    }

    @keyframes pop {
        from { transform: scale(1); }
        to { transform: scale(1.08); }
    }

    .balloon {
        position: absolute;
        width: 40px;
        height: 55px;
        background: red;
        border-radius: 50%;
        bottom: -100px;
        animation: floatUp 10s infinite ease-in;
    }

    .balloon::after {
        content: "";
        position: absolute;
        width: 2px;
        height: 40px;
        background: white;
        top: 55px;
        left: 50%;
    }

    @keyframes floatUp {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-120vh); opacity: 0; }
    }

    .center-box {
        position: relative;
        z-index: 10;
        top: 20%;
    }
</style>
</head>

<body>

<div class="center-box">
    <h1>🎉 Happy Birthday Akshitha 🎂</h1>
    <p>Wishing you joy, success, and endless happiness ✨</p>
</div>

<!-- Balloons -->
<script>
function createBalloons() {
    for (let i = 0; i < 25; i++) {
        let balloon = document.createElement("div");
        balloon.className = "balloon";

        balloon.style.left = Math.random() * 100 + "vw";
        balloon.style.background = 
            ["#ff4d4d","#4dd2ff","#ffff66","#66ff66","#ff66ff"][Math.floor(Math.random()*5)];

        balloon.style.animationDuration = (6 + Math.random() * 5) + "s";
        document.body.appendChild(balloon);
    }
}
createBalloons();
</script>

<!-- Confetti -->
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<script>
setInterval(() => {
    confetti({
        particleCount: 80,
        spread: 100,
        origin: { y: 0.6 }
    });
}, 1500);
</script>

<!-- Music -->
<audio autoplay loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

</body>
</html>
