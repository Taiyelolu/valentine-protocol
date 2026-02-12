# valentine-protocol
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine_Protocol_SECURE.exe</title>

<style>
body {
    margin: 0;
    background: black;
    color: #00ff9d;
    font-family: "Courier New", monospace;
    overflow: hidden;
}

.centered {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    flex-direction: column;
    text-align: center;
}

input {
    background: black;
    border: 1px solid #00ff9d;
    color: #00ff9d;
    padding: 10px;
    margin-top: 10px;
    font-family: "Courier New", monospace;
}

button {
    background: transparent;
    border: 1px solid #00ff9d;
    color: #00ff9d;
    padding: 10px 20px;
    margin-top: 15px;
    cursor: pointer;
    font-family: "Courier New", monospace;
}

button:hover {
    background: #00ff9d;
    color: black;
}

.hidden { display: none; }

.terminal {
    padding: 40px;
    max-width: 900px;
    margin: auto;
}

.output {
    margin-top: 20px;
    white-space: pre-line;
    line-height: 1.8;
}

/* Floating hearts */
.heart {
    position: absolute;
    color: #ff4d6d;
    animation: float 6s linear infinite;
    font-size: 20px;
}

@keyframes float {
    from { transform: translateY(100vh); opacity: 1; }
    to { transform: translateY(-10vh); opacity: 0; }
}
</style>
</head>

<body>

<!-- PASSWORD SCREEN -->
<div id="login" class="centered">
    <h2>> Enter Access Code</h2>
    <p>Hint: Our first Valentine’s year 💌</p>
    <input type="password" id="password" placeholder="Enter Code">
    <button onclick="checkPassword()">Decrypt</button>
    <p id="error"></p>
</div>

<!-- MAIN TERMINAL -->
<div id="main" class="hidden terminal">
    <h2>> Access Granted 💚</h2>
    <p>> Users: Taiyelolu ❤️ Joshua</p>
    <p>> Location Sync: Calgary ⇄ Miami</p>
    <p id="countdown"></p>

    <button onclick="runLoveProtocol()">Run Love Protocol</button>
    <button onclick="fixConnection()">Fix Misunderstanding</button>

    <div class="output" id="output"></div>
</div>

<!-- Soft background music (royalty-free sample link) -->
<audio id="bgMusic" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<script>
const correctPassword = "2026"; // change if you want

function checkPassword() {
    const input = document.getElementById("password").value;
    if (input === correctPassword) {
        document.getElementById("login").classList.add("hidden");
        document.getElementById("main").classList.remove("hidden");
        document.getElementById("bgMusic").play();
        startCountdown();
    } else {
        document.getElementById("error").innerText = "Access Denied ❌";
    }
}

function runLoveProtocol() {
    const message = `
> System Status: Connected.

> Miss_You_Level = INFINITY ♾️
> Best_Friend_Status = TRUE
> Love_Variable = CONSTANT

> Error Log:
I don’t like misunderstandings.
Being on not-great terms with my best friend is unacceptable.

> Reminder:
Joshua.exe = Boyfriend + BestFriend + SafePlace.

> Final Output:
I miss you deeply.
I love you endlessly.
I cannot wait to spend our first Valentine’s together.
    `;
    document.getElementById("output").innerText = message;
}

function fixConnection() {
    document.getElementById("output").innerText = `
> Attempting Repair...

> Clearing Misunderstanding Cache...
> Restoring Communication...
> Connection Strength: 100%

Status: Back to laughing, loving, and being best friends 💚
    `;
}

// Countdown to Feb 14, 2026
function startCountdown() {
    const targetDate = new Date("Feb 14, 2026 00:00:00").getTime();
    setInterval(function() {
        const now = new Date().getTime();
        const distance = targetDate - now;

        const days = Math.floor(distance / (1000 * 60 * 60 * 24));
        document.getElementById("countdown").innerText =
            "> Countdown to Valentine’s: " + days + " days remaining 💌";
    }, 1000);
}

// Floating hearts
setInterval(() => {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerText = "♥";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (Math.random() * 20 + 10) + "px";
    heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
}, 500);
</script>

</body>
</html>
