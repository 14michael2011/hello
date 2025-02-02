<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: pink;
            font-family: Arial, sans-serif;
            overflow: hidden;
            flex-direction: column;
            margin: 0;
            text-align: center;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            width: 80%;
            max-width: 500px;
            position: relative;
            z-index: 2;
        }
        h1 {
            color: red;
            font-size: 1.5em;
            margin-bottom: 20px;
        }
        .buttons {
            margin-top: 20px;
        }
        .btn {
            padding: 12px 25px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            margin: 5px;
        }
        .yes {
            background-color: red;
            color: white;
        }
        .no {
            background-color: gray;
            color: white;
        }
        .pompompurin-image {
            margin-top: 20px;
            width: 100%;
            height: auto;
            max-width: 150px;
        }
        .footer {
            font-size: 14px;
            color: gray;
            margin-top: 20px;
        }
        /* Floating Hearts */
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 30px;
            animation: float 5s linear infinite;
        }
        @keyframes float {
            from {
                transform: translateY(100vh);
                opacity: 1;
            }
            to {
                transform: translateY(-10vh);
                opacity: 0;
            }
        }
        /* Responsive Design */
        @media (max-width: 600px) {
            h1 {
                font-size: 1.3em;
            }
            .btn {
                font-size: 16px;
                padding: 10px 20px;
            }
            .pompompurin-image {
                width: 80%;
                max-width: 120px;
            }
        }
    </style>
</head>
<body>
    <div class="hearts"></div> <!-- Floating Hearts -->
    <div class="container">
        <h1 id="questionText">Will You Be My Valentine?</h1>
        <div class="buttons">
            <button class="btn yes" onclick="acceptLove()">Yes</button>
            <button class="btn no" onclick="changeText()">No</button>
        </div>
        <img class="pompompurin-image" id="pompompurinImg" src="https://media.tenor.com/ZhNxfL0GmoMAAAAj/mocha-bear-hearts.gif" alt="mocha-bear-hearts">
    </div>
    <div class="footer">
        Created by Michael Culla :3
    </div>

    <script>
        let noClickCount = 0;
        const noTexts = ["Are you sure?", "Are you reallllly sure?", "Reallly?", "Theres a message when you say yes"];

        function acceptLove() {
            alert("Hi po Sab. I just want to say po na im sorry for leaving you alone kanina. I didnt wanna make you feel that way and I never want you to feel like im not here for you. This time I promise to always be by your side yk. I love you so much, that I highkey have no words that explain it. You're such an important person in my life, and honestly, the thought of losing you scares me more than anything. I know that I'm not perfect, but I want to do better, to be there for you the way you deserve. Please know that you're never alone. I'm always here, and i'll always choose you. 💖");
            // Change the Pompompurin image
            document.getElementById('pompompurinImg').src = "https://i.pinimg.com/originals/5a/c2/27/5ac2275ba30265fb4053623741bebc22.gif";
        }
        
        function changeText() {
            const questionText = document.getElementById('questionText');
            questionText.innerText = noTexts[noClickCount];
            noClickCount = (noClickCount + 1) % noTexts.length; // Loops back after the last text
        }

        function createHeart() {
            const heart = document.createElement("div");
            heart.innerHTML = "❤️";
            heart.classList.add("heart");
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 3 + 2 + "s";
            document.querySelector(".hearts").appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }

        setInterval(createHeart, 300);
    </script>
</body>
</html>
