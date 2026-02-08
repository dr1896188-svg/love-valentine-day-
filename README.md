<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Will You Be My Valentine?</title>
<style>
    body {
        font-family: 'Segoe UI', sans-serif;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        text-align: center;
        margin: 0;
        padding: 0;
        color: #fff;
    }

    .page {
        display: none;
        height: 100vh;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .active {
        display: flex;
    }

    input {
        padding: 12px;
        font-size: 18px;
        border-radius: 10px;
        border: none;
        outline: none;
        margin: 10px;
        width: 250px;
        text-align: center;
    }

    button {
        padding: 12px 25px;
        font-size: 18px;
        border-radius: 25px;
        border: none;
        cursor: pointer;
        margin: 10px;
    }

    .next-btn, .yes-btn {
        background: #ff4d6d;
        color: white;
    }

    .no-btn {
        background: #fff;
        color: #ff4d6d;
        position: absolute;
    }

    h1 {
        font-size: 36px;
        margin-bottom: 20px;
    }

    .gifts {
        display: flex;
        gap: 20px;
        margin-top: 30px;
        flex-wrap: wrap;
        justify-content: center;
    }

    .gift {
        background: rgba(255, 255, 255, 0.2);
        border-radius: 25px;
        padding: 25px;
        width: 220px;
        font-size: 20px;
    }

    .gift span {
        font-size: 60px;
        display: block;
        margin-bottom: 15px;
    }
</style>
</head>
<body>

<!-- Page 1 -->
<div class="page active" id="page1">
    <h1>Enter Your Name 💕</h1>
    <input type="text" id="nameInput" placeholder="Your name">
    <button class="next-btn" onclick="goToQuestion()">Next ➡️</button>
</div>

<!-- Page 2 -->
<div class="page" id="page2">
    <h1 id="questionText"></h1>
    <button class="yes-btn" onclick="goToGifts()">Yes 💖</button>
    <button class="no-btn" id="noBtn">No 💔</button>
</div>

<!-- Page 3 -->
<div class="page" id="page3">
    <h1>For You, My Valentine 💝</h1>
    <div class="gifts">
        <div class="gift">
            <span>🧸</span>
            "You are my favorite reason to smile every day."
        </div>
        <div class="gift">
            <span>🧸</span>
            "My heart is happier when it’s with you."
        </div>
        <div class="gift">
            <span>🧸</span>
            "Loving you is the best gift life gave me."
        </div>
    </div>
</div>

<script>
    let name = "";

    function goToQuestion() {
        name = document.getElementById("nameInput").value.trim();
        if (name === "") {
            alert("Please enter your name ❤️");
            return;
        }
        document.getElementById("page1").classList.remove("active");
        document.getElementById("page2").classList.add("active");
        document.getElementById("questionText").innerText =
            name + ", will you be my Valentine? 💘";
    }

    function goToGifts() {
        document.getElementById("page2").classList.remove("active");
        document.getElementById("page3").classList.add("active");
    }

    const noBtn = document.getElementById("noBtn");
    noBtn.addEventListener("mouseover", () => {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    });
</script>

</body>
</html>
