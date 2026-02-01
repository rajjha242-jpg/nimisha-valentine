# nimisha-valentine
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Nimisha ❤️</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Poppins', sans-serif;
      overflow: hidden;
    }
    .card {
      background: white;
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      width: 90%;
      max-width: 400px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
    }
    h1 {
      color: #ff4d6d;
      margin-bottom: 10px;
    }
    p {
      color: #555;
      font-size: 16px;
    }
    .buttons {
      margin-top: 25px;
    }
    button {
      padding: 12px 22px;
      border: none;
      border-radius: 30px;
      font-size: 16px;
      cursor: pointer;
      margin: 10px;
      transition: 0.3s;
    }
    .yes {
      background: #ff4d6d;
      color: white;
    }
    .yes:hover {
      transform: scale(1.1);
    }
    .no {
      background: #ddd;
      position: relative;
    }
    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }
    .heart {
      position: absolute;
      color: #ff4d6d;
      font-size: 20px;
      animation: float 4s linear infinite;
    }
    @keyframes float {
      0% { transform: translateY(100vh); opacity: 1; }
      100% { transform: translateY(-10vh); opacity: 0; }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Nimisha ❤️</h1>
    <p>
      After all these years, you’re still my favorite person,  
      my safest place, and my forever.
    </p>
    <h2>Will you be my Valentine? 🌹</h2>

    <div class="buttons">
      <button class="yes" onclick="yesClicked()">Yes 💖</button>
      <button class="no" onmouseover="moveNo()">No 🙈</button>
    </div>
  </div>

  <div class="hearts" id="hearts"></div>

  <script>
    function yesClicked() {
      document.body.innerHTML = `
        <div class="card">
          <h1>YAY!! 💕</h1>
          <p>
            I knew it 😌❤️  
            Happy Valentine’s Day, Nimisha.
          </p>
        </div>
      `;
      createHearts();
    }

    function moveNo() {
      const btn = document.querySelector('.no');
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    function createHearts() {
      const hearts = document.getElementById('hearts');
      setInterval(() => {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerHTML = '❤️';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
        hearts.appendChild(heart);
        setTimeout(() => heart.remove(), 4000);
      }, 200);
    }
  </script>

</body>
</html>

