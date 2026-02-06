# san-valentin
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>¿Quieres ser mi San Valentín? 💘</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      color: #eee;
      overflow: hidden;
    }
    .card {
      background: rgba(255,255,255,0.9);
      border-radius: 20px;
      padding: 30px;
      max-width: 420px;
      width: 90%;
      text-align: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.4);
      z-index: 2;
    }
    h1 { font-size: 1.7em; margin-bottom: 10px; color:#333; }
    p { font-size: 1.05em; margin-bottom: 25px; color:#444; }
    .buttons { display:flex; justify-content:center; gap:15px; flex-wrap:wrap; }
    button { padding:12px 20px; border:none; border-radius:30px; font-size:1em; cursor:pointer; transition:transform .2s, box-shadow .2s; }
    button:hover { transform:scale(1.05); box-shadow:0 5px 15px rgba(0,0,0,.2); }
    .yes { background:#ff4d6d; color:white; }
    .no { background:#ddd; color:#555; position:relative; }
    .message { margin-top:25px; font-size:1.2em; display:none; color:#333; }

    /* Estrellas y corazones */
    .float {
      position: absolute;
      bottom: -50px;
      animation: floatUp linear infinite;
      opacity: 0.8;
      z-index: 1;
    }
    @keyframes floatUp {
      from { transform: translateY(0) scale(1); opacity:0; }
      10% { opacity:1; }
      to { transform: translateY(-110vh) scale(1.2); opacity:0; }
    }
  </style>
</head>
<body>
  <audio id="music" loop>
    <source src="https://www.dropbox.com/scl/fi/9xqk4x2v9c8nq0p3n0h7j/I-Wanna-Be-Yours.mp3?raw=1" type="audio/mpeg">
    Tu navegador no soporta audio.
  </audio>
  <div class="card">
    <h1>🌙 ¿Quieres ser mi San Valentín, mi anrrea CR7? 💖</h1>
    <p style="font-size:1em; color:#555;">
      En este mundo tan grande, tú eres mi lugar favorito.
      Cada risa, cada abrazo y cada momento contigo hacen que todo valga la pena ✨
    </p>
    <p>
      Desde el primer día contigo, cada momento se volvió especial.
      No imagino este 14 de febrero sin ti… ✨
    </p>
    <div class="buttons">
      <button class="yes" onclick="playMusic(); sayYes()">Sí, obvio 💕</button>
      <button class="no" onmouseover="moveNo(this)">No 😅</button>
      <button style="background:#6a5acd;color:white;" onclick="playMusic()">▶️ Reproducir música</button>
      <button class="yes" onclick="sayYes()">Sí, obvio 💕</button>
      <button class="no" onmouseover="moveNo(this)">No 😅</button>
    </div>
    <div class="message" id="message">
      💘 Muchas gracias por todas las alegrías, mi niña preciosa.<br />
      Te amo mucho más de lo que te demuestro y a veces te hago pensar :( ❤️
    </div>
  </div>

  <script>
    function playMusic() {
      const music = document.getElementById('music');
      music.play();
    }

    function sayYes() {
      const msg = document.getElementById('message');
      msg.style.display = 'block';
    }

    function moveNo(btn) {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    // Crear estrellas y corazones flotando
    const symbols = ['⭐','✨','💖','💗','💫'];
    function createFloat() {
      const el = document.createElement('div');
      el.className = 'float';
      el.innerText = symbols[Math.floor(Math.random()*symbols.length)];
      el.style.left = Math.random() * 100 + 'vw';
      el.style.fontSize = (Math.random() * 20 + 15) + 'px';
      el.style.animationDuration = (Math.random() * 6 + 6) + 's';
      document.body.appendChild(el);
      setTimeout(() => el.remove(), 12000);
    }
    setInterval(createFloat, 600);
  </script>
</body>
</html>
