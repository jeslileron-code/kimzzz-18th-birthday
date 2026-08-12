# kimzzz-18th-birthday
Happy 18th birthday 

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy 18th Birthday Kimzzz 🎂</title>
<link rel="stylesheet" href="style.css">
</head>

<body>

<canvas id="confetti"></canvas>

<section id="welcome" class="screen active">
    <div class="card">
        <p>✨ A special surprise for...</p>
        <h1>Kimzzz</h1>
        <h2>is turning 18! 🎂</h2>

        <button onclick="startSurprise()">
            Open My Surprise 💌
        </button>
    </div>
</section>

<section id="letterPage" class="screen">
    <div class="card">

        <h2>💌 For Kimzzz</h2>

        <div class="envelope" onclick="openLetter()">
            <div class="flap"></div>
            <div class="heart">💖</div>
        </div>

        <div id="letter" class="letter">
            <h2>Happy 18th Birthday, Kimzzz! 🎂</h2>

            <p>
            Happy 18th birthday, Kimzzz! 🎂 Marami pang kaarawan
            ang dumating sa buhay mo. Sana bigyan ka ng Diyos ng
            mabuting kalusugan—alagaan mo palagi ang sarili mo,
            bespren! Sana magustuhan mo at lubusin ang
            napaka-espesyal na araw na ito. at sana mag tagumpay
            ka sa Buhay para may mag lilibre balang araw and
            maging successful tayo sa course na bsit 💻
            </p>

            <button onclick="showBirthday()">
                Continue ✨
            </button>
        </div>

    </div>
</section>

<section id="birthdayPage" class="screen">

    <div class="card">

        <div class="cake">🎂</div>

        <h1>Happy 18th Birthday!</h1>

        <h2>Kimzzz 💖</h2>

        <p>
            Welcome to your new chapter! ✨
        </p>

        <button onclick="playMusic()">
            🎵 Play Music
        </button>

        <button onclick="showMemory()">
            📸 Our Memory
        </button>

    </div>

</section>

<section id="memoryPage" class="screen">

    <div class="card">

        <h2>📸 One Special Memory</h2>

        <p>Tap the picture para lumaki.</p>

        <img
            src="photos/kimzzz.jpg"
            class="photo"
            onclick="openPhoto()"
        >

        <button onclick="finalSurprise()">
            Final Surprise 🎉
        </button>

    </div>

</section>

<section id="finalPage" class="screen">

    <div class="card">

        <div class="bigEmoji">
            🎈🎂🎈
        </div>

        <h1>Enjoy Your Day!</h1>

        <h2>Kimzzz ❤️</h2>

        <p>
            18 na! Sana maging masaya ka today
            at sa lahat ng susunod na chapters
            ng buhay mo.
        </p>

        <p>
            Sana maging successful tayo sa BSIT. 💻✨
        </p>

        <h3>
            From your bespren 💖
        </h3>

        <button onclick="celebrate()">
            More Confetti 🎊
        </button>

    </div>

</section>

<audio id="music" loop>
    <source src="birthday_music.mp3" type="audio/mpeg">
</audio>

<script src="script.js"></script>

</body>
</html>


* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    font-family: Arial, sans-serif;
    color: white;
    background:
        radial-gradient(circle at top, #49266d, #100522 60%);
    overflow-x: hidden;
}

.screen {
    min-height: 100vh;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 25px;
}

.screen.active {
    display: flex;
}

.card {
    width: min(700px, 95%);
    padding: 35px 25px;
    text-align: center;
    border-radius: 30px;
    background: rgba(255,255,255,0.12);
    backdrop-filter: blur(15px);
    box-shadow: 0 25px 70px rgba(0,0,0,.6);
}

h1 {
    font-size: clamp(45px, 12vw, 80px);
    margin: 10px 0;
    background: linear-gradient(90deg,#ff9ed8,#fff,#ffd76a);
    -webkit-background-clip: text;
    color: transparent;
}

h2 {
    font-size: clamp(28px,7vw,45px);
}

p {
    line-height: 1.8;
}

button {
    border: none;
    border-radius: 30px;
    padding: 14px 22px;
    margin: 8px;
    font-weight: bold;
    cursor: pointer;
    color: #261039;
    background: white;
}

button:hover {
    transform: scale(1.05);
}

.envelope {
    width: 280px;
    height: 180px;
    margin: 30px auto;
    background: #e58bc5;
    border-radius: 15px;
    position: relative;
    cursor: pointer;
}

.flap {
    position: absolute;
    width: 100%;
    height: 60%;
    background: #c76baa;
    clip-path: polygon(0 0,100% 0,50% 100%);
}

.heart {
    position: absolute;
    top: 55%;
    left: 50%;
    transform: translate(-50%,-50%);
    font-size: 50px;
}

.letter {
    display: none;
    background: white;
    color: #34233b;
    padding: 25px;
    border-radius: 20px;
    text-align: left;
}

.letter.show {
    display: block;
    animation: appear .8s ease;
}

.cake {
    font-size: 100px;
    animation: bounce 1s infinite alternate;
}

.photo {
    width: min(430px,90vw);
    height: 430px;
    object-fit: cover;
    border-radius: 25px;
    cursor: pointer;
    border: 4px solid rgba(255,255,255,.4);
}

.bigEmoji {
    font-size: 75px;
}

#confetti {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 100;
}

@keyframes bounce {
    from {
        transform: translateY(0);
    }

    to {
        transform: translateY(-15px);
    }
}

@keyframes appear {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

const music = document.getElementById("music");

function changePage(id) {

    document.querySelectorAll(".screen")
        .forEach(page => page.classList.remove("active"));

    document.getElementById(id)
        .classList.add("active");

    window.scrollTo(0,0);
}

function startSurprise() {

    changePage("letterPage");

    playMusic();

    celebrate();
}

function openLetter() {

    document.getElementById("letter")
        .classList.add("show");

    celebrate();
}

function showBirthday() {

    changePage("birthdayPage");

    celebrate();
}

function showMemory() {

    changePage("memoryPage");

    celebrate();
}

function finalSurprise() {

    changePage("finalPage");

    celebrate();
}

function playMusic() {

    music.play().catch(() => {
        console.log("Tap Play Music to start.");
    });
}

function openPhoto() {

    window.open(
        "photos/kimzzz.jpg",
        "_blank"
    );
}


// CONFETTI

const canvas =
    document.getElementById("confetti");

const ctx =
    canvas.getContext("2d");

let pieces = [];

function resizeCanvas() {

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}

resizeCanvas();

window.addEventListener(
    "resize",
    resizeCanvas
);

function celebrate() {

    for(let i = 0; i < 180; i++) {

        pieces.push({

            x: window.innerWidth / 2,

            y: window.innerHeight / 3,

            vx: (Math.random() - .5) * 14,

            vy: -Math.random() * 12,

            size: Math.random() * 8 + 3,

            life: 120 + Math.random() * 100,

            rotation: Math.random() * 6

        });

    }
}

function animateConfetti() {

    ctx.clearRect(
        0,
        0,
        canvas.width,
        canvas.height
    );

    pieces =
        pieces.filter(
            p => p.life-- > 0
        );

    pieces.forEach(p => {

        p.x += p.vx;

        p.y += p.vy;

        p.vy += .18;

        p.rotation += .1;

        ctx.save();

        ctx.translate(
            p.x,
            p.y
        );

        ctx.rotate(
            p.rotation
        );

        ctx.fillStyle =
            ["#ff86c8",
             "#ffd76a",
             "#8de8ff",
             "#ffffff",
             "#b9ff9b"]
            [Math.floor(Math.random()*5)];

        ctx.fillRect(
            -p.size/2,
            -p.size/2,
            p.size,
            p.size * 1.7
        );

        ctx.restore();

    });

    requestAnimationFrame(
        animateConfetti
    );
}

animateConfetti();
