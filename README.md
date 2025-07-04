<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>For My Tanna 💖</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(to right, #ffd9ec, #fff5f8);
      color: #3a3a3a;
      overflow: hidden;
    }
    .container {
      max-width: 800px;
      margin: 60px auto;
      padding: 40px;
      background: #fff0f5;
      border-radius: 25px;
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
      position: relative;
      animation: fadeIn 2s ease;
    }
    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 3em;
      text-align: center;
      margin-bottom: 20px;
      color: #e91e63;
    }
    .letter {
      display: none;
      font-size: 1.2em;
      line-height: 1.8em;
      animation: slideUp 1s ease forwards;
    }
    .letter.active {
      display: block;
    }
    .nav-buttons {
      display: flex;
      justify-content: space-between;
      margin-top: 30px;
    }
    button {
      background: #ff91b6;
      border: none;
      padding: 12px 24px;
      border-radius: 25px;
      color: white;
      font-size: 1em;
      cursor: pointer;
      transition: background 0.3s;
    }
    button:hover {
      background: #ff5e94;
    }
    .floating-hearts {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      pointer-events: none;
      overflow: hidden;
    }
    .heart {
      position: absolute;
      width: 20px; height: 20px;
      background: url('https://i.imgur.com/5cLDeXa.png') no-repeat center/contain;
      animation: float 10s linear infinite;
      opacity: 0.6;
    }
    @keyframes float {
      0% {transform: translateY(100vh) rotate(0); opacity: 0;}
      50% {opacity: 1;}
      100% {transform: translateY(-10vh) rotate(360deg); opacity: 0;}
    }
    @keyframes fadeIn {
      from {opacity: 0; transform: scale(0.95);}
      to {opacity: 1; transform: scale(1);}
    }
    @keyframes slideUp {
      from {opacity: 0; transform: translateY(20px);}
      to {opacity: 1; transform: translateY(0);}
    }
  </style>
</head>
<body>
  <div class="floating-hearts"></div>
  <div class="container">
    <h1>To My Tanna 💕</h1>

    <div class="letter active">
      <p>My sweet Tanna,</p>
      <p>I know we’ve been distant, but not a day goes by without thinking of you. You’re in my breath, my heart, my soul.</p>
    </div>

    <div class="letter">
      <p>Every moment we shared is a treasure. Your laughter, your voice, even your silence—it echoes in my mind every night.</p>
    </div>

    <div class="letter">
      <p>I waited for 3 years because I knew you were worth it. I still believe in us. No distance can erase what I feel for you.</p>
    </div>

    <div class="letter">
      <p>I miss you in ways words can’t describe. I miss your chaos, your calm, your everything. You are home to my heart.</p>
    </div>

    <div class="letter">
      <p>This isn’t just a website, it’s a letter from my soul to yours. Please forgive me, Tanna. Let’s write our next chapter—together.</p>
      <p>Yours forever,<br><strong>Pranu 💗</strong></p>
    </div>

    <div class="nav-buttons">
      <button onclick="prevLetter()">← Previous</button>
      <button onclick="nextLetter()">Next →</button>
    </div>
  </div>

  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_222a99f24e.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <script>
    const letters = document.querySelectorAll('.letter');
    let current = 0;

    function showLetter(index) {
      letters.forEach((l, i) => l.classList.toggle('active', i === index));
    }

    function nextLetter() {
      current = (current + 1) % letters.length;
      showLetter(current);
    }

    function prevLetter() {
      current = (current - 1 + letters.length) % letters.length;
      showLetter(current);
    }

    function createHearts() {
      const container = document.querySelector('.floating-hearts');
      for (let i = 0; i < 30; i++) {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (5 + Math.random() * 5) + 's';
        container.appendChild(heart);
      }
    }
    createHearts();
  </script>
</body>
</html>
