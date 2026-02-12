<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Be My Valentine?</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        background: linear-gradient(to bottom right, #ff9a9e, #fecfef);
        font-family: Arial, sans-serif;
        text-align: center;
        overflow: hidden;
    }

    h1 {
        font-size: 2.5rem;
        margin-bottom: 40px;
        color: white;
        text-shadow: 2px 2px 5px rgba(0,0,0,0.2);
    }

    .buttons {
        display: flex;
        gap: 20px;
    }

    button {
        padding: 15px 30px;
        font-size: 1.2rem;
        border: none;
        border-radius: 12px;
        cursor: pointer;
        transition: 0.3s ease;
    }

    #yesBtn {
        background-color: #ff4d6d;
        color: white;
        transform: scale(1);
    }

    #noBtn {
        background-color: white;
        color: #ff4d6d;
    }
</style>
</head>
<body>

<h1 id="question">Will you be my Valentines? ❤️</h1>

<div class="buttons">
    <button id="yesBtn">Yes 💕</button>
    <button id="noBtn">No</button>
</div>

<!-- Audio Files -->
<audio id="noSound" src="no.mp3"></audio>
<audio id="yesSound" src="yes.mp3"></audio>
<audio id="bgMusic" src="music.mp3" loop></audio>

<script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const noSound = document.getElementById("noSound");
    const yesSound = document.getElementById("yesSound");
    const bgMusic = document.getElementById("bgMusic");

    const noTexts = [
        "Are you sure?",
        "You better say yes 😠",
        "Babe pleaseeeee 🥺"
    ];

    let clickCount = 0;
    let yesScale = 1;

    noBtn.addEventListener("click", () => {
        // Play sound effect No
        noSound.currentTime = 0;
        noSound.play();

        // Ganti teks
        noBtn.textContent = noTexts[clickCount % noTexts.length];

        // Perbesar tombol Yes
        yesScale += 0.2;
        yesBtn.style.transform = `scale(${yesScale})`;

        clickCount++;
    });

    yesBtn.addEventListener("click", () => {
        // Play sound Yes
        yesSound.play();

        // Play background music
        bgMusic.play();

        document.getElementById("question").textContent = "YAYYY I LOVE YOU SO MUCH ❤️😍";

        noBtn.style.display = "none";
        yesBtn.style.transform = "scale(1.6)";
    });
</script>

</body>
</html>
