<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Will You Be My Valentine?</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #f9c5d1, #fbc2eb);
      font-family: 'Segoe UI', sans-serif;
    }

    .card {
      background: #fff;
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      width: 350px;
      height: 300px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      position: relative;
      overflow: hidden;
    }

    .emoji {
      font-size: 60px;
      margin-bottom: 10px;
    }

    h2 {
      margin-bottom: 30px;
      color: #333;
    }

    .buttons {
      position: relative;
      height: 100px;
    }

    button {
      padding: 12px 24px;
      font-size: 16px;
      border-radius: 25px;
      border: none;
      cursor: pointer;
      position: absolute;
      user-select: none;
    }

    #yesBtn {
      background: #ff4d6d;
      color: white;
      left: 60px;
      bottom: 10px;
    }

    #noBtn {
      background: #e0e0e0;
      left: 180px;
      bottom: 10px;
    }

    .note {
      margin-top: 20px;
      font-size: 14px;
      color: #666;
    }
  </style>
</head>

<body>

  <div class="card">
    <div class="emoji">🐱💖</div>
    <h2>Niranjani will you be my valentine?</h2>

    <div class="buttons">
      <button id="yesBtn" onclick="yesClicked()">No</button>
      <button id="noBtn"
        onmouseenter="startRun()"
        ontouchstart="startRun()"
        onclick="moveNo()">Yes</button>
    </div>

    <div class="note">"No" is scared 😈</div>
  </div>

  <script>
    let runInterval;

    function moveNo() {
      const noBtn = document.getElementById("noBtn");
      const card = document.querySelector(".card");

      const cardRect = card.getBoundingClientRect();
      const btnRect = noBtn.getBoundingClientRect();

      const maxX = cardRect.width - btnRect.width - 20;
      const maxY = cardRect.height - btnRect.height - 120;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    }

    function startRun() {
      clearInterval(runInterval);
      runInterval = setInterval(moveNo, 80); // ⚡ SPEED (lower = faster)
    }

    function yesClicked() {
      document.body.innerHTML = `
        <div style="
          display:flex;
          justify-content:center;
          align-items:center;
          height:100vh;
          background:#ffdee9;
          font-family:Segoe UI;
          text-align:center;
        ">
          <h1>Nakku<br>yes kudukamudiyathae</h1>
        </div>
      `;
    }
  </script>

</body>
</html>
