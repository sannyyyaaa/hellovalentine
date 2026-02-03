<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Will You Be My Forever Valentine?</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;600&family=Poppins:wght@300;400&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #fdeff9, #ec38bc, #7303c0);
      background-size: 300% 300%;
      animation: bgMove 10s ease infinite;
      font-family: 'Poppins', sans-serif;
    }

    @keyframes bgMove {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .card {
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(10px);
      border-radius: 24px;
      padding: 40px 30px;
      width: 320px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.25);
      position: relative;
    }

    .card::before {
      content: '❤';
      position: absolute;
      top: -20px;
      right: -20px;
      font-size: 60px;
      opacity: 0.3;
    }

    h1 {
      font-family: 'Playfair Display', serif;
      color: #b30059;
      font-size: 24px;
      margin-bottom: 10px;
    }

    p {
      font-size: 15px;
      color: #555;
      margin-bottom: 30px;
    }

    .buttons {
      position: relative;
      height: 120px;
    }

    button {
      padding: 12px 26px;
      border: none;
      border-radius: 30px;
      font-size: 15px;
      cursor: pointer;
      transition: all 0.3s ease;
      position: absolute;
    }

    #yesBtn {
      background: linear-gradient(135deg, #ff4d6d, #ff758f);
      color: white;
      left: 50%;
      transform: translateX(-50%);
      bottom: 0;
      box-shadow: 0 10px 20px rgba(255, 77, 109, 0.4);
    }

    #yesBtn:hover {
      transform: translateX(-50%) scale(1.05);
    }

    #noBtn {
      background: #f1f1f1;
      color: #333;
      left: 50%;
      transform: translateX(-50%);
      top: 0;
    }

    .final-message {
      display: none;
      margin-top: 20px;
      font-size: 18px;
      color: #b30059;
      font-family: 'Playfair Display', serif;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Will you be my<br>forever Valentine? 💖</h1>
    <p>Some questions deserve only one answer ✨</p>

    <div class="buttons">
      <button id="noBtn">No 🙈</button>
      <button id="yesBtn" onclick="sayYes()">Yes 💍</button>
    </div>

    <div class="final-message" id="finalMessage">
      Yay! I knew it 💕<br>Forever starts now ✨
    </div>
  </div>

  <script>
    const noBtn = document.getElementById('noBtn');

    setTimeout(() => {
      noBtn.addEventListener('mouseover', moveButton);
      noBtn.addEventListener('click', moveButton);
    }, 4000); // starts moving after 4 seconds

    function moveButton() {
      const card = document.querySelector('.card');
      const maxX = card.offsetWidth - noBtn.offsetWidth - 20;
      const maxY = card.offsetHeight - noBtn.offsetHeight - 40;

      const randomX = Math.random() * maxX;
      const randomY = Math.random() * maxY;

      noBtn.style.left = randomX + 'px';
      noBtn.style.top = randomY + 'px';
    }

    function sayYes() {
      document.querySelector('.buttons').style.display = 'none';
      document.getElementById('finalMessage').style.display = 'block';
    }
  </script>
</body>
</html>
