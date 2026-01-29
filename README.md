<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Flower Garden + Love Story</title>
    <link rel="stylesheet" href="style.css" />
</head>
<body>

<!-- MUSIC PLAYER -->
<audio id="bgMusic" src="love-story.mp3" loop></audio>

<div class="container">
    <h1>🌸 Welcome to the Flower Garden 🌸</h1>
    <p>Enjoy the music and the blossoms 🌷</p>

    <button onclick="toggleMusic()" class="music-btn">Play / Pause Music</button>

    <div class="flowers">
        <img src="images/flower1.png" class="flower" alt="Flower" />
        <img src="images/flower2.png" class="flower" alt="Flower" />
        <img src="images/flower3.png" class="flower" alt="Flower" />
        <img src="images/flower4.png" class="flower" alt="Flower" />
        <img src="images/flower5.png" class="flower" alt="Flower" />
    </div>
</div>

<script>
    const music = document.getElementById("bgMusic");

    // Auto-play music (user gesture required on some browsers)
    window.onload = () => {
        setTimeout(() => {
            music.play().catch(err => {
                console.log("Play was prevented:", err);
            });
        }, 500);
    };

    function toggleMusic() {
        if (music.paused) music.play();
        else music.pause();
    }
</script>

</body>
</html>
