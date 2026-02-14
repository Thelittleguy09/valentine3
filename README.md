<!DOCTYPE html>
<meta charset="UTF-8">
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine Proposal</title>

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {
        background: linear-gradient(135deg, #ffe6f0, #ffd6e7);
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        padding: 20px;
    }

    .card {
        background: white;
        width: 100%;
        max-width: 400px;
        padding: 30px 20px;
        border-radius: 20px;
        text-align: center;
        box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        position: relative;
    }

    h2 {
        font-size: 20px;
        margin-bottom: 25px;
    }

    .buttons {
        display: flex;
        justify-content: center;
        gap: 15px;
        flex-wrap: wrap;
    }

    button {
        padding: 12px 20px;
        border: none;
        border-radius: 25px;
        font-size: 16px;
        cursor: pointer;
        min-width: 100px;
        transition: 0.2s ease;
    }

    #yesBtn {
        background-color: #ff4d6d;
        color: white;
    }

    #yesBtn:hover {
        transform: scale(1.1);
    }

    #noBtn {
        background-color: #ccc;
        position: relative;
    }

    .hidden {
        display: none;
    }

    img {
        width: 100%;
        max-width: 220px;
        margin-top: 20px;
        border-radius: 10px;
    }

    @media (max-width: 400px) {
        h2 {
            font-size: 18px;
        }

        button {
            font-size: 14px;
            padding: 10px 16px;
        }
    }
</style>
</head>

<body>

<div class="card">
    <h2 id="question">Can,Will you be my Valentine? 💖</h2>

    <div class="buttons">
        <button id="yesBtn">Yes</button>
        <button id="noBtn">No</button>
    </div>
<p style="margin-top: 15px; font-size: 14px; color: #777;">
Try clicking No 
 </p> 


    <div id="result" class="hidden">
        <h2>YAY! 🎉</h2>
        <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="celebration gif">
    </div>
</div>

<script>
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const result = document.getElementById("result");
    const question = document.getElementById("question");
    const card = document.querySelector(".card");

    yesBtn.addEventListener("click", () => {
        question.style.display = "none";
        yesBtn.style.display = "none";
        noBtn.style.display = "none";
        result.classList.remove("hidden");
    });

    // Mobile-friendly moving "No" button
    noBtn.addEventListener("touchstart", moveButton);
    noBtn.addEventListener("mouseover", moveButton);

    function moveButton() {
        const cardRect = card.getBoundingClientRect();
        const btnRect = noBtn.getBoundingClientRect();

        const maxX = cardRect.width - btnRect.width - 20;
        const maxY = cardRect.height - btnRect.height - 20;

        const randomX = Math.random() * maxX;
        const randomY = Math.random() * maxY;

        noBtn.style.position = "absolute";
        noBtn.style.left = randomX + "px";
        noBtn.style.top = randomY + "px";
    }
</script>

</body>
</html># valentine3
