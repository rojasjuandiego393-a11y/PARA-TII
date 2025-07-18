<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mi Voleibolista Favorita</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to top right, #ffc0cb, #ffe4e1);
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      font-family: 'Segoe UI', sans-serif;
    }

    h1 {
      font-size: 3rem;
      color: #d63384;
      text-shadow: 2px 2px 4px #00000050;
      animation: latidos 1.5s infinite;
    }

    @keyframes latidos {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }

    button {
      margin-top: 20px;
      padding: 12px 24px;
      font-size: 1.1rem;
      color: white;
      background-color: #d63384;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      transition: background 0.3s ease;
    }

    button:hover {
      background-color: #a61e66;
    }

    iframe {
      display: none;
    }

    .corazon {
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: red;
      transform: rotate(45deg);
      animation: flotar 5s linear infinite;
    }

    .corazon::before,
    .corazon::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: red;
      border-radius: 50%;
    }

    .corazon::before { top: -10px; left: 0; }
    .corazon::after  { left: -10px; top: 0; }

    @keyframes flotar {
      0%   { bottom: 0; opacity: 0; }
      50%  { opacity: 1; }
      100% { bottom: 100%; opacity: 0; }
    }
  </style>
</head>
<body>

  <h1>Mi Voleibolista Favorita</h1>
  <button onclick="reproducirMusica()">🎵 Reproducir música</button>

  <!-- Iframe invisible para música -->
  <iframe id="musica" allow="autoplay"></iframe>

  <script>
    function reproducirMusica() {
      const iframe = document.getElementById('musica');
      iframe.src = "https://www.youtube.com/embed/qMnOQtSyOAE?autoplay=1&loop=1&playlist=qMnOQtSyOAE";
      iframe.style.display = "none"; // Se mantiene oculto
    }

    // Corazones flotantes
    function crearCorazon() {
      const c = document.createElement('div');
      c.classList.add('corazon');
      c.style.left = Math.random() * window.innerWidth + 'px';
      document.body.appendChild(c);
      setTimeout(() => c.remove(), 5000);
    }
    setInterval(crearCorazon, 500);
  </script>

</body>
</html>
