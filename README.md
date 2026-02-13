[index.html](https://github.com/user-attachments/files/25297397/index.html)
<!DOCTYPE html>
<html>
<head>
    <title>For You ❤️</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>Will you be my Valentine, MYLOVE? 💖</h1>

        <div class="buttons">
            <button id="yesBtn">YES 💕</button>
            <button id="noBtn">NO 😢</button>
        </div>
    </div>

    <audio id="bgMusic" src="music.mp3"></audio>

    <script src="script.js"></script>
</body>
</html>
[style.css](https://github.com/user-attachments/files/25297398/style.css)
body {
    text-align: center;[script.js](https://github.com/user-attachments/files/25297399/script.js)document.addEventListener("DOMContentLoaded", function () {

    let scale = 1;

    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const music = document.getElementById("bgMusic");

    noBtn.addEventListener("click", function () {

        scale += 0.4;

        yesBtn.style.position = "fixed";
        yesBtn.style.top = "50%";
        yesBtn.style.left = "50%";
        yesBtn.style.transform = `translate(-50%, -50%) scale(${scale})`;
        yesBtn.style.zIndex = "1000";

        if (scale > 3) {
            yesBtn.style.position = "fixed";
            yesBtn.style.top = "0";
            yesBtn.style.left = "0";
            yesBtn.style.width = "100vw";
            yesBtn.style.height = "100vh";
            yesBtn.style.transform = "none";
            yesBtn.style.fontSize = "50px";
            yesBtn.style.borderRadius = "0";
            noBtn.style.display = "none";
        }
    });

    yesBtn.addEventListener("click", function () {

        music.play();

        document.body.innerHTML = `
            <div style="
                text-align:center;
                padding-top:50px;
                background:#ffe6f0;
                height:100vh;
                font-family: Arial;">

                <h1 style="color:hotpink; font-size:50px;">
                    YAYYYY 💕<br>You are already mine MERO GUNDU😘 
                </h1>

                <div class="slideshow">
                    <img src="cinema.jpg">
                    <img src="couple.jpg">
                    <img src="best.jpg">
                </div>

            </div>
        `;

        createHearts();
    });

    function createHearts() {
        setInterval(() => {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.fontSize = Math.random() * 20 + 20 + "px";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }, 300);
    }

});


    font-family: Arial, sans-serif;
    background-color: #fff0f5;
    overflow: hidden;
    margin: 0;
    background: url(killer.jpg);
}

.container {
    margin-top: 150px;
}

h1 {
    font-size: 32px;
}

button {
    font-size: 20px;
    padding: 15px 30px;
    margin: 15px;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    transition: 0.3s;
}

#yesBtn {
    background-color: #ff4da6;
    color: white;
}

#noBtn {
    background-color: #999;
    color: white;
}

.heart {
    position: fixed;
    color: red;
    font-size: 20px;
    animation: floatUp 5s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(100vh); opacity: 1; }
    100% { transform: translateY(-10vh); opacity: 0; }
}

.slideshow img {
    width: 250px;
    border-radius: 15px;
    margin: 10px;
}
